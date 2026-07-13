DEC AXP 情報については、Linux の README.alpha を参照してください。

このファイルは主に Linux/Intel IA-32 に適用されます。  M68K 上の Linux へのポート、
IA-64、SPARC、MIPS、Alpha、PowerPC も統合されています。  彼らは行儀よく振る舞うべきだ
同様に、PowerPC ポートにはインクリメンタル GC サポートがない点が異なります。
Linux スレッドのコードがどの程度機能するかは不明です。
M68K 固有の注意事項については、以下を参照してください。

インクリメンタル GC は通常サポートされています。

動的ライブラリは ELF システムでサポートされています。

コレクターは Linux スレッドで確実に動作するように見えますが、注意してください。
glibc および gdb の古いバージョンの。

ガベージ コレクターは、SIGPWR と SIGXCPU を使用する場合、それを使用します。
Linux スレッド。  これらはクライアント プログラムによって触れられるべきではありません。

スレッドを使用するには、次の要件に従う必要があります。

1) LinuxThreads または NPTL (libc6 に含まれています) を使用する必要があります。

コレクターは、LinuxThreads の実装の詳細の一部に依存します。
パッケージ。  このコードは他のコードでは動作しない可能性があります
pthread 実装 (特に、pthread 実装では *機能しません*)
pthread を使用します)。

2) 「-D GC_THREADS -D _REENTRANT」を指定してコレクターをコンパイルする必要があります。
Makefile.direct ファイル内。

3a) スレッド呼び出しを行うすべてのファイルは GC_THREADS を定義する必要があります。
gc.h を含めます。  後者は、pthread プリミティブの一部を次のように再定義します。
コレクタに必要な情報も提供するマクロ。

3b) (3a) に代わる新しい方法は、コレクターを構築して GC クライアントをコンパイルすることです。
「-D GC_USE_LD_WRAP」を付けて、最終的なプログラムをリンクします

(ld の場合) --wrap dlopen --wrap pthread_create \
--wrap pthread_join --wrap pthread_detach \
--wrap pthread_sigmask --wrap pthread_exit --wrap pthread_cancel

(gcc の場合) -Wl,--wrap -Wl,dlopen -Wl,--wrap -Wl,pthread_create \
-Wl,--wrap -Wl,pthread_join -Wl,--wrap -Wl,pthread_detach \
-Wl,--wrap -Wl,pthread_sigmask -Wl,--wrap -Wl,pthread_exit \
-Wl,--wrap -Wl,pthread_cancel

いずれの場合も、コンパイル時に _REENTRANT を定義する必要があります。

4) dlopen() は、実行中に収集を無効にします。  (実行できません
コレクターはコレクターと同時に見るので、
データ構造。  任意のロックであるため、アロケータ ロックを取得できません。
ユーザー起動コードは dlopen() の一部として実行される場合があります。)
状況によっては、予期しないヒープの増加が発生する可能性があります。

5) GC_THREADS、REDIRECT_MALLOC、インクリメンタルの組み合わせ
コレクションはおそらく完全に信頼できるわけではありませんが、現在は機能しているようです
単純な場合。

6) スレッドローカル ストレージ (TLS) は、
コレクタ。  これはおそらく LinuxThreads のバージョンに依存します。  のために
当面は、スレッドローカルストレージによって参照される収集可能なメモリ
他の場所から参照するか、収集不可能なものとして割り当てる必要があります。
(これは実際には何らかの形で修正されるべきバグです。実際には、
少なくとも Linux 上では、コレクターはおそらく正しく処理します。
TLS の場所が多すぎる場合、dlopen が使用されていない場合。)
