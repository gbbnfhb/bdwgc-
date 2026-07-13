元ネタ:https://github.com/bdwgc/bdwgc  
の日本語訳(機械翻訳)。細かい所がわかりにくいので翻訳にかけてみた  
  
  
  
  
  
  
# ベーム・デマース・ヴァイザー ガベージ コレクター

[![Travis-CI ビルド ステータス](https://app.travis-ci.com/bdwgc/bdwgc.svg?branch=master)](https://app.travis-ci.com/github/bdwgc/bdwgc)
[![AppVeyor CI ビルド ステータス](https://img.shields.io/appveyor/build/bdwgc/bdwgc.svg?branch=master)](https://ci.appveyor.com/project/bdwgc/bdwgc/branch/master)
[![GitHub Actions ビルド ステータス (autotools ビルド) extra)](https://github.com/bdwgc/bdwgc/actions/workflows/autotools-build-extra.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/autotools-build-extra.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (cmake)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-build.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-build.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (cmake) extra)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-build-extra.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-build-extra.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (cmake) cosmo)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-cosmo.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/cmake-cosmo.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (zig build/test)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-build.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-build.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (zig クロスコンパイル) Linux)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-cross-compile.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-cross-compile.yml?query=branch%3Amaster)
[![GitHub Actions ビルド ステータス (zig クロスコンパイル) Linux 以外)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-cross-compile-other.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-cross-compile-other.yml?query=branch%3Amaster)
[![GitHub Actions のビルド ステータス(Makefile.direct)](https://github.com/bdwgc/bdwgc/actions/workflows/make-direct-build.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/make-direct-build.yml?query=branch%3Amaster)
[![GitHub アクションのステータス (cppcheck)](https://github.com/bdwgc/bdwgc/actions/workflows/cppcheck.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/cppcheck.yml?query=branch%3Amaster)
[![GitHub アクションのステータス(clang-format)](https://github.com/bdwgc/bdwgc/actions/workflows/clang-format-check.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/clang-format-check.yml?query=branch%3Amaster)
[![GitHub Actions ステータス (zig 形式)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-format-check.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/zig-format-check.yml?query=branch%3Amaster)
[![GitHub アクションのステータス (CSA チェック)](https://github.com/bdwgc/bdwgc/actions/workflows/csa-check.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/csa-check.yml?query=branch%3Amaster)
[![GitHub アクションのステータス (スペルチェック)](https://github.com/bdwgc/bdwgc/actions/workflows/spell-check.yml/badge.svg?event=push)](https://github.com/bdwgc/bdwgc/actions/workflows/spell-check.yml?query=branch%3Amaster)
[![CodeQL](https://github.com/bdwgc/bdwgc/workflows/CodeQL/badge.svg)](https://github.com/bdwgc/bdwgc/actions/workflows/CodeQL.yml?query=branch%3Amaster)
[![カバレッジ ステータス (Codecov)](https://codecov.io/github/bdwgc/bdwgc/coverage.svg?branch=master)](https://app.codecov.io/github/bdwgc/bdwgc?branch=master)
[![カバレッジ ステータス (カバーオール)](https://coveralls.io/repos/github/bdwgc/bdwgc/badge.svg?branch=master)](https://coveralls.io/github/bdwgc/bdwgc)
[![Coverity Scan ビルド ステータス](https://scan.coverity.com/projects/32099/badge.svg)](https://scan.coverity.com/projects/bdwgc-bdwgc)
[![FOSSA ステータス](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fbdwgc%2Fbdwgc.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fbdwgc%2Fbdwgc?ref=badge_shield)
[![OpenSSF ベスト プラクティス](https://www.bestpractices.dev/projects/6332/badge)](https://www.bestpractices.dev/projects/6332)
[![ヒットオブコード](https://hitsofcode.com/github/bdwgc/bdwgc?branch=master)](https://hitsofcode.com/github/bdwgc/bdwgc/view)
[![GitHub コード サイズ (バイト単位)](https://img.shields.io/github/langages/code-size/bdwgc/bdwgc)](https://shields.io/badges/git-hub-code-size-in-bytes)
[![Github のすべてのリリース](https://img.shields.io/github/downloads/bdwgc/bdwgc/total.svg)](https://shields.io/badges/git-hub-downloads-all-assets-all-releases)
[![パッケージングのステータス](https://repology.org/badge/tiny-repos/boehm-gc.svg)](https://repology.org/project/boehm-gc/versions)

これは保守的なガベージのバージョン 8.3.0 (次のリリース開発) です
C および C++ のコレクター。

ライセンス: [MIT スタイル](LICENSE)


## ダウンロード

より新しい/安定したバージョンは、
[ダウンロード](https://github.com/bdwgc/bdwgc/wiki/Download) ページ、または
[BDWGC サイト](http://www.hboehm.info/gc/)。

また、最新のバグ修正と新機能は、
[開発リポジトリ](https://github.com/bdwgc/bdwgc)。


＃＃ 概要

これは、汎用のガベージ コレクション ストレージとして使用することを目的としています。
アロケータ。  使用されるアルゴリズムについては、以下で説明されています。

* Boehm, H.、M. Weiser、「非協力的な環境におけるガベージ コレクション」
「Environment」、Software Practice & Experience、1988 年 9 月、807 ～ 820 ページ。

* Boehm、H.、A. Demers、および S. Shenker、「Mostly Parallel Garbage Collection」、
プログラミング言語設計に関する ACM SIGPLAN '91 カンファレンスの議事録
および実装、SIGPLAN Notices 26、6 (1991 年 6 月)、157 ～ 164 ページ。

* Boehm, H.、「Space Efficient Conservative Garbage Collection」、議事録
ACM SIGPLAN '91 プログラミング言語設計カンファレンスの
「実装」、SIGPLAN Notices 28、6 (1993 年 6 月)、197 ～ 206 ページ。

* Boehm H.、「ガベージ コレクターのキャッシュ ミスの削減」、Proceedings of the
2000 年メモリ管理に関する国際シンポジウム。

コレクターと最適化コンパイラーの間で考えられる対話は次のとおりです。
で議論されました

* Boehm、H.、D. Chase、「GC セーフな C コンパイルの提案」、
The Journal of C Language Translation 4、2 (1992 年 12 月)。

* Boehm H.、「Simple GC-safe Compilation」、ACM SIGPLAN '96 の議事録
プログラミング言語の設計と実装に関するカンファレンス。

2 番目の参考資料で説明されているコレクターとは異なり、このコレクターは
コレクション全体の間、ミューテーターが停止された状態で動作します。
(デフォルト)、または割り当て中に増分的に。  (後者はサポートされています
最も一般的なプラットフォームでは、または
マルチスレッドのサポートなし。  一部のプラットフォームでは、
マルチプロセッサを使用してガベージ コレクションを高速化します。

コレクターの基礎となるアイデアの多くは以前に検討されています
他人によって。  特に、Xerox PARC で開発されたランタイム システムの一部は、
1980 年代初頭には、スレッド スタックを保守的にスキャンして、可能性のあるものを見つけました。
ポインター (cf. Paul Rovner、「ガベージ コレクションとランタイム タイプの追加について」)
厳密に型指定され、静的にチェックされた同時実行言語へ」 Xerox PARC
CSL 84-7)。  ダグ・マキロイは、よりシンプルで完全に保守的なコレクターを書きました。
バージョン 8 UNIX (tm) の一部でしたが、受け取っていないようです
広く使用されています。

コレクタを [リーク検出器] として使用するための基本的なツール (docs/leak.md)
かなり洗練された文字列パッケージ「cord」も含まれています。
コレクターを利用します。  ([cords.md](docs/cords.md) および
H.-J.ベーム、R. アトキンソン、M. プラス、「ロープ: 弦の代替案」、
ソフトウェアの実践と経験 25、12 (1995 年 12 月)、1315 ～ 1330 ページ。
これは、Xerox Cedar の「rope」パッケージ、または「rope」に非常に似ています。
SGI STL または g++ ディストリビューションのパッケージ。)

コレクターの詳細なドキュメントは、次の場所にあります。
[概要](docs/overview.md)。

コレクターの既知の使用法の一部が GitHub にリストされています。
[既知のクライアント](https://github.com/bdwgc/bdwgc/wiki/Known-clients) ページ。


## 概要説明

これは、ガベージ コレクション ストレージ アロケータです。
C の malloc の代替プラグインとして使用されます。

コレクターはポインターにタグを付ける必要がないため、
アクセスできないすべてのストレージが確実に再利用されるようにします。  しかし、
私たちの経験では、通常、未使用のデータを再利用する方が成功します。
明示的な割り当て解除を使用するほとんどの C プログラムよりもメモリを増やすことができます。  手動とは異なります
リークが発生しても、通常は未回収のメモリ量が残ります。
境界のある。

以下では、「オブジェクト」は割り当てられたメモリ領域として定義されます。
以下に説明するルーチンによって。

収集を目的としていないオブジェクトは、次のいずれかを指す必要があります。
他のそのようなアクセス可能なオブジェクトから、またはレジスタから、
スタック、データ、または静的に割り当てられた bss セグメント。  からのポインタ
スタックまたはレジスタはオブジェクト内の任意の場所を指すことができます。
コレクターが次のようにコンパイルされている場合、ヒープ ポインターにも同じことが当てはまります。
`ALL_INTERIOR_POINTERS`が定義されているか、`GC_all_interior_pointers`が定義されていない
設定されています。これがデフォルトです。

`ALL_INTERIOR_POINTERS`を使用せずにコンパイルすると、偶発的な保持が減る可能性があります
ヒープから先頭へのポインタを要求することにより、ガベージ オブジェクトの数を減らす
オブジェクトの。  しかし、これはもはや重要ではないようです
ほとんどのプログラムで問題が発生し、可能性のある問題のほんの一部を占めます。
アドレス空間。

ポインター認識を変更するルーチンが多数あります。
アルゴリズム。`GC_register_displacement`は特定の内部ポインターを許可します
`ALL_INTERIOR_POINTERS`が定義されていない場合でも認識されます。
`GC_malloc_ignore_off_page`では、中間へのいくつかのポインターが許可されます。
大きなオブジェクトは無視されるため、次のような可能性が大幅に減少します。
大きな物体を誤って保持してしまう。  ほとんどの目的ではそう思われます
`ALL_INTERIOR_POINTERS`でコンパイルして使用するのが最善です
`GC_malloc_ignore_off_page`からコレクタ警告が表示された場合
非常に大きなオブジェクトの割り当て。  詳細については、[こちら](docs/debugging.md) を参照してください。

*警告*: 標準 (システム)`malloc`によって割り当てられたメモリ内のポインター
ガベージ コレクターには認識されません。  したがって、オブジェクトはそのようなものからのみポイントされます
領域が途中で割り当て解除される可能性があります。  したがって、
標準`malloc`は、I/O バッファなどのメモリ領域にのみ使用されます。
ガベージ コレクタブル メモリへのポインタが含まれないことが保証されています。
C言語の自動変数、静的変数、またはレジスタ変数のポインタ、
正しく認識されています。  (`GC_malloc_uncollectable`には
セマンティクスは標準の malloc に似ていますが、次のオブジェクトを割り当てます。
コレクターによって追跡されました。）

*警告*: コレクターは、データ内のポインターを見つける方法を常に知っているわけではありません。
動的ライブラリに関連付けられた領域。  これは簡単に修正できます
オペレーティング システム上でこれらのデータ領域を見つける方法を知っている場合 (「
`GC_add_roots`)。  SunOS、Irix 5.x および 6.x、HP/UX でこれを実行するためのコード
Alpha OSF/1 (Tru64 UNIX)、Linux、および Win32 が含まれており、デフォルトで使用されます。
([README.win32](docs/platforms/README.win32) および
Windows の詳細については [README.win64](docs/platforms/README.win64))。
システムでは、動的ライブラリ データ領域からのポインタが考慮されない場合があります。
コレクタ。  コレクターに依存するプログラムを作成している場合
動的ライブラリのデータ領域をスキャンするには、少なくとも以下を含めることをお勧めします。
`GC_is_visible`を 1 回呼び出すことで、これらの領域が確実に表示されるようになります。
コレクタ。

ガベージ コレクターには共有について通知する必要がないことに注意してください。
読み取り専用データ。  ただし、共有ライブラリメカニズムが導入できる場合は、
ポインターを含む可能性のある不連続なデータ領域にはコレクターが実行します。
知らせる必要がある。

ほとんどの信号の信号処理は収集中に延期される可能性があります。
割り当てプロセスの中断のない部分でも。
標準の ANSI C malloc と同様、デフォルトでは呼び出すのは安全ではありません
シグナル ハンドラーからの malloc (および他の GC ルーチン) を実行しながら、別のシグナル ハンドラーから
malloc 呼び出しが進行中の可能性があります。

アロケータ/コレクタは、スレッドセーフな動作用に構成することもできます。
(完全な信号安全性も達成できますが、2 つのシステムのコストのみがかかります)
malloc ごとに呼び出しが行われますが、これは通常は受け入れられません)。

*警告*: コレクターはスレッドローカル ストレージをスキャンすることを保証しません。
(例:`pthread_getspecific`でアクセスされる種類)。  コレクター
ただし、スレッド スタックをスキャンするため、一般的に最善の解決策は次のとおりです。
スレッドローカルストレージに保存されているすべてのポインタも確実に保存されるようにしてください。
存続期間中、スレッドのスタックに保存されます。
(これはおそらく長年のバグですが、まだ修正されていません。)


## ビルドとインストール

コレクターを構築するには複数の方法があります。

* CMake (推奨される方法です)
* GNU autoconf/automake
* ジグ (実験的)
* MS nmake (直接)
* Makefile.direct
* マニュアル C コンパイル

### CMake

`gc`ライブラリ (および`cord`ライブラリ) を構築して実行する最も簡単な方法
CMake を使用したテスト:

```sh
mkdir build
cd build
cmake ..
cmake --build .
ctest
```

これは、ライブラリを構築する最もクロスプラットフォームな方法です。
詳細については、[cmake.md](docs/cmake.md) を参照してください。

### GNU Autoconf/Automake

コレクターのソース リポジトリには`configure`が含まれていないことに注意してください。
および同様の自動生成ファイル、つまり`autoconf`ベースの完全な手順
ソース リポジトリからのコレクタのビルドは次のようになります。

```sh
./autogen.sh
./configure
make check
```

GNU スタイルのビルド プロセスは、通常のターゲットとオプションを理解します。
`make install`は、`gc`ライブラリと`cord`ライブラリをインストールします。`./configure --help`を試してください
すべての構成オプションを表示します。  現在はできません
この方法でビルド オプションのすべての組み合わせを実行します。

詳細については、[autoconf.md](docs/autoconf.md) を参照してください。

### ジグ

zig を使用したコレクターの構築とテストは簡単です。
最も単純な形式:

```sh
zig build test
```

変数を使用してビルドを構成することができます。
`zig build -Denable_redirect_malloc -Denable_threads=false`.  ジグのオファー
優れたクロスコンパイル機能を備えており、次のように構成できます。

```sh
zig build -Dtarget=riscv64-linux-musl
```

適切な Zig バイナリ パッケージ ファイルは公式からダウンロードできます。
[Zig リリース](https://ziglang.org/download/) ページ。

### MS nmake

Windows では、Microsoft ビルド ツールがインストールされており、適切であると仮定します。
設定が完了すると、ライブラリを構築し、次を使用してテストを実行できます。
`nmake`を直接、例:`nmake -f NT_MAKEFILE check`と入力してください。  しかし、
推奨される方法は、上で説明したように cmake を使用することです。

詳細については、[README.win32](docs/platforms/README.win32) を参照してください。

### Makefile.direct

古いスタイル (クラシック) Makefile ベースのビルド プロセスの場合は、次のように入力します。
`make -f Makefile.direct check`は`gc`、`cord`を自動的にビルドします
ライブラリを編集してから、`gctest`などのいくつかのテストを実行します。  テストは
コレクタ機能のやや表面的なテストです。  失敗が示されています
コア ダンプまたはコレクタが壊れているという旨のメッセージによって。
`gctest`は、2023 年頃のビンテージ 64 ビットで実行するには数十秒かかる場合があります
デスクトップ。  最大約 30 MB のメモリを使用する場合があります。

`Makefile.direct`ファイルはリンクする必要がある`libgc.a`ファイルを生成します
に対して。

### 手動 C コンパイル

最後に、ほとんどのターゲットでは、コレクタを直接構築してテストできます。
このように単一のコンパイラ呼び出しを使用します (サンプルにはマルチスレッドがありません)
サポート）：

```sh
cc -I include -o gctest tests/gctest.c extra/gc.c && ./gctest
```

たとえば、これはデバッグの目的に便利です。

### 設定可能なマクロ

を定義することで、ビルド中にライブラリをより正確に構成できます。
[macros.md](docs/macros.md) ファイルにリストされているマクロ。

ライブラリは、マルチスレッド サポートを有効にして構築されています (つまり、
スレッドセーフ操作)、次の方法で明示的に無効にしない限り、デフォルトで動作します。

*`-Denable_threads=false`オプションは`cmake`または`zig build`に渡されます
*`--disable-threads`オプションが`./configure`に渡されました

コレクタはデフォルト設定ではサイレントに動作します。
問題が発生した場合、これは通常、
`GC_PRINT_STATS`または`GC_PRINT_VERBOSE_STATS`環境変数。  これ
各コレクションについて数行の説明的な出力が生成されます。
(指定された統計にはいくつかの特徴があります。
さまざまな理由で物事がうまくいかないように見えますが、最も顕著なのは
断片化による損失。  これらはおそらく、
あなたのアプリケーション用に作られたプログラム`gctest`です。)

### アトミックオプス

コンパイラを使用すると、`libatomic_ops`の使用 (クローン作成) がオプションになりました。
アトミック組み込み関数をサポートします。  最新のコンパイラのほとんどはこれを実行します。  注目すべき例外
MS コンパイラです (Visual Studio 2022 以降)。

必要に応じて、ほとんどの OS ディストリビューションには`libatomic_ops`パッケージが含まれています。あるいは、
からダウンロードまたはクローンを作成できます
GitHub 上の [libatomic_ops](https://github.com/bdwgc/libatomic_ops) リポジトリ。


## 移植性

コレクターは現在、基本的に変更せずに実行できるように設計されています。
フラットな 32 ビットまたは 64 ビットのアドレス空間を使用するマシン。
これには、大部分のワークステーションと x86 (i386 以降) PC が含まれます。

いくつかのケース (OS/2、Win32 など) では、別の Makefile が提供されます。これらは持っています
別のホスト固有の docs/platforms/README.* ファイル。

動的ライブラリは、SunOS/Solaris でのみ完全にサポートされます。
(そして、そのサポートさえも、最後の Sun 3 リリースでは機能しません)、
Linux、FreeBSD、NetBSD、Irix、HP/UX、Win32 (win32s ではない)、および Tru64 UNIX
DEC AXP マシンと、おそらく上部近くにリストされている他のいくつかのマシン上
dyn_load.c の。  他のマシンでは、次のいずれかを実行することをお勧めします。
次の：

1. 動的ライブラリのサポートを追加します (コードを送信してください)。

2. ライブラリの静的バージョンを使用します。

3. 標準の malloc を使用するように動的ライブラリを調整します。これはまだ
ライブラリにガベージ コレクションされたオブジェクトへのポインターが格納されている場合は危険です。
しかし、ほぼすべての標準インターフェイスはこれを禁止しています。
スタックに割り当てられたオブジェクトへのポインターを正しく使用します。  (`strtok`は
例外。  使用しないでください。)

すべての場合において、ポインタの位置合わせがそれと一致していると仮定します。
標準の C コンパイラによって強制されます。  標準以外のコンパイラを使用する場合
で定義されている位置合わせパラメータを調整する必要がある場合があります。
`include/private/gc_priv.h`ファイル。  これも問題となる可能性があることに注意してください
パックされたレコード/構造体 (ポインタのアライメントが少なくなる場合)。

バイトアドレス指定されていない、または 32 ビットを使用していないマシンへのポート
または 64 ビット アドレスの場合は多大な労力が必要になります。  プレーンな MSDOS への移植
Win16は難しいです。

まだ言及されていないマシン、または標準以外のコンパイラの場合は、
いくつかの移植に関する提案は、[こちら](docs/porting.md) で提供されています。


## アロケータへの C インターフェイス

次のルーチンは、ユーザーが直接呼び出すことを目的としています。
通常は`GC_malloc`のみが必要であることに注意してください。`GC_clear_roots`および
コレクターがトレースする必要がある場合は、`GC_add_roots`呼び出しが必要になる場合があります
標準以外の場所から (例:
コレクタがそれらをまだ理解していないマシン)。
一部のマシンでは、`GC_stackbottom`を適切な値に設定することが望ましい場合があります。
スタックベースの近似図（下）。

クライアント コードには、次のすべてを定義する`gc.h`ファイルが含まれる場合があります。
他にもたくさん。

1.`GC_malloc(bytes)`- 指定されたサイズのオブジェクトを割り当てます。
`malloc`とは異なり、オブジェクトはユーザーに返される前にクリアされます。
`GC_malloc`は、これが必要であると判断した場合にガベージ コレクターを呼び出します。
適切であること。`GC_malloc`は取得できない場合に 0 を返す場合があります
オペレーティング システムから十分なスペースが必要です。  これが最も可能性が高いです
スペース不足の結果。  他に考えられる影響は次のとおりです。
スタック領域の不足により関数呼び出しが失敗するか、
コレクターは内部を維持できないため、他の方法で失敗します。
データ構造、または重要なシステムプロセスが失敗して停止する可能性がある
機械。  これらの可能性のほとんどは、`malloc`とは独立しています。
実装。

2.`GC_malloc_atomic(bytes)`- 指定されたサイズのオブジェクトを割り当てます。
にはポインタが含まれていないことが保証されます。  返されたオブジェクトは
確実にクリアできる。  (いつでも`GC_malloc`に置き換えることができますが、
その結果、収集時間が短縮されます。  コレクターはおそらく実行されます
大きな文字配列などが割り当てられている場合は高速になります。
`GC_malloc_atomic`は静的に割り当てられる場合よりも異なります。)

3.`GC_realloc(object, new_bytes)`および`GC_reallocf(object, new_bytes)`-
オブジェクトのサイズを指定したサイズに変更します。  ポインタを返します
新しいオブジェクトは、
古い物体。  新しいオブジェクトは、古いオブジェクトがアトミックであると見なされます。
1つはそうでした。  新しいオブジェクトが複合オブジェクトで、元のオブジェクトよりも大きい場合
オブジェクトの場合、新しく追加されたバイトはクリアされます。これは非常に可能性が高いです
新しいオブジェクトを割り当てます。

4.`GC_free(object)`、`GC_freezero(object, bytes_to_clear)`- 明示的に
`GC_malloc`または`GC_malloc_atomic`によって返されたオブジェクトの割り当てを解除します。
または友達。  必須ではありませんが、次の場合にコレクションを最小限に抑えるために使用できます。
パフォーマンスが重要です。  おそらくパフォーマンスの低下が発生する可能性があります
非常に小さいオブジェクト (8 バイト以下)。`GC_freezero`は次のことを保証します
オブジェクトは割り当て解除前にゼロで埋められます。

5.`GC_expand_hp(bytes)`- ヒープ サイズを明示的に増やします。  (これは
通常、ガベージ コレクションの再利用に失敗した場合は自動的に実行されます。
十分なメモリ。`GC_expand_hp`を明示的に呼び出すと、
プログラム起動時に不必要に頻繁に収集が行われます。)

6.`GC_malloc_ignore_off_page(bytes)`-`GC_malloc`と同じですが、
クライアントは最初の GC 内のどこかへのポインタを保持することを約束します
ヒープ ブロック (512 .. 4096 バイト以上、環境によってはそれ以上)
ライブ中のオブジェクトの設定)。  (このポインタは、
通常、コンパイラからの干渉を防ぐために`volatile`と宣言されます。
) これは、必要なものを割り当てる場合に推奨される方法です。
100 KB 程度より大きくなる可能性があります。  (`GC_malloc`は次のような結果になる可能性があります
そのようなオブジェクトの回収に失敗した場合。)

7. __​​INLINECODE0__ - からの警告をリダイレクトするために使用できます。
コレクタ。  このような警告が表示されることはまれであり、無視すべきではありません。
コード開発中。

8.`GC_enable_incremental()`- 世代別および増分を有効にします
コレクション。  へのアクセスを提供するマシン上の大規模なヒープに役立ちます。
ページダーティ情報。  一部のダーティ ビット実装が干渉する可能性があります
(アドレス障害を捕捉することにより) デバッグを使用し、制限を設ける
システムコールへのヒープ引数 (システムコール内の書き込みエラーのため)
うまく扱えない可能性があります）。

9.`GC_register_finalizer(object, proc, data, 0, 0)`と友達 - 許可する
ファイナライズコードの登録用。  ユーザー指定の終了コード
(`(*proc)(object, data)`) は、オブジェクトが到達不能になった後に呼び出されます。
より高度な使用法とファイナライゼーションの順序の問題については、を参照してください。
`gc.h`ファイル。

グローバル変数`GC_free_space_divisor`はそこから調整される可能性があります
デフォルト値の 3 を使用すると、使用するスペースが減り、収集時間が長くなります。
逆効果。  1 に設定すると、コレクションはほぼ無効になります。
すべての割り当てによってヒープが単純に拡大されます。

変数`GC_non_gc_bytes`(通常は 0) は、次の値を反映するように変更される場合があります。
上記のルーチンによって割り当てられるべきではないメモリの量。
回収候補として考えられます。  もちろん、不用意に使用すると結果が生じる可能性があります
メモリを過剰に消費します。

定義されたパラメータを使用して追加の調整が可能です
`include/private/gc_priv.h`ファイルの先頭付近。

`GC_malloc`のみを使用する場合は、次のように定義するのが適切かもしれません。
のように：

```c
#define malloc(n) GC_malloc(n)
#define calloc(m, n) GC_malloc((m) * (n))
```

*非常に* 割り当てを大量に消費するコードの小さな部分の場合は、`gc_inline.h`ファイル
`GC_malloc`の代わりに使用できるいくつかの割り当てマクロが含まれています。
友達。

ガベージ コレクター内の外部から見える名前はすべて`GC_`で始まります。
名前の競合を避けるために、次の場合を除き、クライアント コードではこのプレフィックスを避ける必要があります。
ガベージ コレクター ルーチンにアクセスします。

明示的な型情報を使用して割り当てを行うための規定があります。
これが必要になることはほとんどありません。  詳細は`gc_typed.h`ファイルにあります。


## アロケータへの C++ インターフェイス

コレクターへの Ellis-Hull C++ インターフェイスがコレクターに含まれています
分布。  これを使用する場合は、次のように入力します
`./configure --enable-cplusplus && make`(または
`cmake -D enable_cplusplus=ON . && cmake --build .`、または
`make -f Makefile.direct c++`は使用するビルド システムによって異なります)。
これにより、`libgccpp.a`および`libgctba.a`ファイル、またはそれらの共有ライブラリが作成されます
同等のファイル (`libgccpp.so`および`libgctba.so`ファイル)。  とリンクする必要があります
最初の (`gccpp`) または 2 番目の (`gctba`) のいずれかですが、両方ではありません。
の定義については、`gc_cpp.h`ファイルと [こちら](docs/gcinterface.md) を参照してください。
インタフェース。  このインターフェイスは、Ellis-Detlefs C++ ガベージを近似しようとします。
コンパイラを変更しないコレクション提案。

多くの場合、`gc_allocator.h`ファイルと
STL データ構造を構築するためにそこで宣言されたアロケーター。  さもないと
STL データ構造のサブオブジェクトは、システムを使用して割り当てられます。
アロケータ、およびそれらが参照するオブジェクトが途中で収集される可能性があります。


## リークディテクタとして使用

コレクターは、次のような C プログラムのリークを追跡するために使用される場合があります。
`malloc`/`free`で実行することを目的としています (例: 極端なリアルタイム性や
移植性の制約)。  これを行うには、`FIND_LEAK`マクロを定義します (たとえば、
`Makefile.direct`ファイルの`CFLAGS_EXTRA`変数にあります)。  これにより、
コレクターは、いつでも人間が読めるオブジェクトの説明を出力します。
明示的に解放されていない、アクセスできないオブジェクトが見つかりました。
このようなオブジェクトも自動的に回収されます。

すべてのオブジェクトが`GC_DEBUG_MALLOC`で割り当てられている場合 (次のセクションを参照)
その場合、デフォルトでは、人間が読めるオブジェクトの説明には少なくとも以下が含まれます。
ソース ファイルと、リークしたオブジェクトが割り当てられた行番号。
これで十分な場合もあります。  (いくつかのマシンでは、レポートも表示されます)
不可解なスタック トレース。  これが記号的でない場合は、次のように呼び出すこともできます。
プログラム "foo" を呼び出してシンボリック スタック トレースに書き込みます。
__インラインコード0__。  これは adb を呼び出す短いシェル スクリプトです。
プログラム カウンタ値をシンボリック アドレスに拡張します。  大量に供給されていました
スコット・シュワルツ著。）

次のセクションで説明するデバッグ機能では、
リーク発見モードでは効果がわずかに *劣る * 場合があります。
`GC_debug_free`では、実際にはオブジェクトが再利用されます。  (そうでない場合、
オブジェクトは単に無効とマークされているだけです。)また、ほとんどの GC テストは無効ではないことに注意してください。
`FIND_LEAK`モードで有意義に実行されるように設計されています。


## デバッグ機能

ルーチン`GC_debug_malloc`、`GC_debug_malloc_atomic`、`GC_debug_realloc`、
`GC_debug_reallocf`および`GC_debug_free`は、
コレクターは、メモリー上書きエラーに関するヘルプを提供します。
のように。  この方法で割り当てられたオブジェクトには、追加の注釈が付けられます。
情報。  この情報の一部はガベージ コレクション中にチェックされます。
検出された不一致は`stderr`に報告されます。

割り当てられたオブジェクトの末尾を超えて書き込む単純なケースでは、
オブジェクトが明示的に割り当て解除された場合、または
コレクターはオブジェクトが生きている間に呼び出されます。  最初の割り当て解除
オブジェクトを削除すると、オブジェクトに関連付けられたデバッグ情報がクリアされます。
オブジェクトなので、誤って`GC_debug_free`への呼び出しを繰り返すと、
デバッグ情報を持たないオブジェクトの割り当て解除。  のうち
メモリ エラーは、`NULL`を返すだけでなく、`stderr`にも報告されます。

`GC_debug_malloc`ガベージ コレクション中のチェックが有効になっています
この関数の最初の呼び出しで。  これにより、いくつかの結果が得られます
収集中の速度低下。  ヒープチェックを頻繁に行いたい場合は、
これは、`GC_gcollect`を明示的に呼び出すことで実現できます。から
デバッガ。

`GC_debug_malloc`で割り当てられたオブジェクトは`GC_realloc`に渡すべきではありません。
`GC_reallocf`、`GC_free`、`GC_freezero`、およびその逆。  ただし、
`GC_debug_malloc`を使用して一部のオブジェクトのみを割り当て、使用することは許容されます。
他のオブジェクトの場合は`GC_malloc`(2 つのプールが区別されている場合)。
この場合、`GC_malloc`が割り当てられる可能性は非常に低いです。
オブジェクトが上書きされたものと誤認される可能性があります。  これは起こるはずです
確率的には`2**32`に最大 1 つです。  次の場合、この確率はゼロになります。
`GC_debug_malloc`は呼び出されません。

`GC_debug_malloc`、`GC_debug_malloc_atomic`、`GC_debug_realloc`および
`GC_debug_reallocf`は 2 つの追加の末尾引数、文字列と
整数。  これらはアロケータによって解釈されません。  保存されているのは、
オブジェクト (文字列はコピーされません)。  オブジェクトに関するエラーが発生した場合、
検出されると印刷されます。

マクロ`GC_MALLOC`、`GC_MALLOC_ATOMIC`、`GC_REALLOC`、`GC_FREE`、
`GC_REGISTER_FINALIZER`とその友達も提供されます。  これらは同じことを必要とします
引数を対応する (非デバッグ) ルーチンとして扱います。`gc.h`ファイルが
`GC_DEBUG`定義に含まれる場合、これらのデバッグ バージョンを呼び出します。
関数、現在のファイル名と行番号を 2 つとして渡します。
必要に応じて、追加の引数。`gc.h`ファイルが含まれていない場合
`GC_DEBUG`マクロが定義されている場合、これらすべてのマクロは代わりに次のように定義されます。
デバッグ以外の同等のもの。  (`GC_REGISTER_FINALIZER`は必要です。
デバッグ情報を持つオブジェクトへのポインタは、実際には次へのポインタです。
オブジェクトの先頭から 16 バイトの変位、および一部の変換は
終了処理ルーチンが呼び出されるときに必要になります。  詳しい内容については、
ヘッダーに格納されます。`dbg_mlc.h`の`oh`型の定義を参照してください。
ファイル。）


## 増分/世代別コレクション

コレクターは通常、次の期間クライアント コードを中断します。
ガベージ コレクション マーク フェーズ。  インタラクティブな場合、これは受け入れられない可能性があります
大きなヒープを持つプログラムには応答が必要です。  コレクター
「世代別」モードでも実行できます。通常、このモードでは次のことを試みます。
最後のガベージ コレクション以降に割り当てられたオブジェクトのみを収集します。
さらに、このモードでは、ガベージ コレクションはほとんど増分的に実行されます。
多数のそれぞれの要求に応じて実行される少量の作業で、
`GC_malloc`リクエスト。

このモードは、`GC_enable_incremental`の呼び出しによって有効になります。

増分および世代別収集は、コスト削減に効果的です。
コレクターがどのオブジェクトを認識する方法がある場合にのみ一時停止します。
またはページが最近変更されました。  コレクターは 2 つのソースを使用します
情報の:

1. VM システムによって提供される情報。  これは、次のいずれかで提供される場合があります。
いくつかの形式。  Solaris 2.x 環境 (および他の同様の環境でも可能性あり)
システム) ダーティ ページに関する情報は`/proc`ファイルから読み取ることができます
システム。  他のシステム (SunOS 4.x など) では、次のことが可能です。
ヒープを書き込み保護し、その結果生じる障害をキャッチします。  これらのシステムでは
ヒープへの書き込み (`read`以外) をシステム コールで行う必要があります。
クライアント コードによって特別に処理されます。  詳細については、`os_dep.c`を参照してください。

2. プログラマーによって提供される情報。  オブジェクトは汚れていると見なされます
`GC_end_stubborn_change`の呼び出し後、ライブラリが
適当にまとめました。  通常、寿命が短い場合には使用する価値がありません。
オブジェクト。`GC_end_stubborn_change`または
`GC_reachable_here`呼び出しは非常にまれに観察される可能性が高く、
追跡するのが難しい。


## バグ

認識可能なポインタを持たないメモリは再利用されます。
リスト内の前方リンクと後方リンクの排他的論理和では問題は解決されません。

一部の C オプティマイザは、メモリへの最後の隠蔽されていないポインタを失う可能性があります。
賢い最適化の結果としてオブジェクトが生成されます。  これはほぼ
実際には観察されたことはありません。

これはリアルタイム コレクターではありません。  標準構成では、
収集に必要な時間の割合は、全体にわたって一定である必要があります。
ヒープサイズ。  ただし、ヒープが大きくなると、収集の一時停止が増加します。
並列マーキングの場合、プロセッサの数に応じて減少します。
有効になっています。

(2007 年のビンテージ マシンでは、GC 時間は 5 ミリ秒程度になる場合があります)
スキャンして処理する必要があるアクセス可能なメモリの MB あたり。
走行距離は異なる場合があります。) 増分/世代別収集機能
場合によっては役立つかもしれません。


## フィードバック、貢献、質問、通知

バグレポートや新機能のアイデアについては、
[GitHub の問題](https://github.com/bdwgc/bdwgc/issues)。  前に
送信は、他の人によってまだ行われていないことを確認してください。

貢献したい場合は送信してください
GitHub への [プル リクエスト](https://github.com/bdwgc/bdwgc/pulls)。
修正したファイルは投稿前にclang形式で処理してください。

助けが必要な場合は、を使用してください
[スタック オーバーフロー](https://stackoverflow.com/questions/tagged/boehm-gc)。
古い技術的なディスカッションは、`bdwgc`メーリング リスト アーカイブで入手できます。
としてダウンロードできます
[圧縮ファイル](https://github.com/bdwgc/bdwgc/files/1038163/bdwgc-mailing-list-archive-2017_04.tar.gz)
または、[Narkive](http://bdwgc.opendylan.narkive.com) で閲覧してください。

新しいリリースのお知らせを受け取るには、購読してください
[RSS フィード](https://github.com/bdwgc/bdwgc/releases.atom)。
(電子メールで通知を受信するには、次のようなサードパーティの無料サービスを使用します。
【IFTTT RSSフィード】(https://ifttt.com/feed)が設定可能です。)
すべての問題について通知を受け取るには、
[watch](https://github.com/bdwgc/bdwgc/watchers) のプロジェクト
GitHub。


## 著作権と保証、寄稿者

私たちの目的は、無料と両方の bdwgc (libgc) を簡単に使用できるようにすることです。
独自のソフトウェア。  したがって、ベーム・デマース・ヴァイザー保守派のゴミは
動的または静的にリンクされることが予想されるコレクター コード
クライアント アプリケーションは独自のライセンスによってカバーされます。これは、次の場合と同様です。
精神をMITスタイルのものに。

正確なライセンス情報は、[LICENSE](LICENSE) ファイルに記載されています。

すべての貢献者は [AUTHORS](AUTHORS) ファイルにリストされています。
