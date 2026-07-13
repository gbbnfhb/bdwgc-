[インターフェイスの概要](gcinterface.md) | [チュートリアル スライド](http://www.hboehm.info/gc/04tutorial.pdf) | [FAQ](faq.md) | [例](simple_example.md) | [ダウンロード](https://github.com/bdwgc/bdwgc/wiki/Download)
---|---|---|---|---

# C および C++ 用のガベージ コレクター

* プラットフォーム
* コレクターの詳細
* さらに読む
※BDWGCサイトでの情報提供
* ドキュメントファイル
* 詳しい背景情報
*連絡先と新しいリリースのお知らせ

[ これは、以前のページの更新版です。
`www.hpl.hp.com/personal/Hans_Boehm/gc/`、その前に
`http://reality.sgi.com/boehm/gc.html`とその前
__インラインコード0__。 ]

の
[ベーム](http://www.hboehm.info)-[デマース](http://www.cs.cornell.edu/annual_report/00-01/bios.htm#demers)-[ヴァイザー](https://en.wikipedia.org/wiki/Mark_Weiser)
保守的なガベージ コレクター (**BDWGC**) はガベージ コレクションとして使用できます
C`malloc`または C++`new`の置き換え。メモリを割り当てることができます
基本的には通常どおり、明示的にメモリの割り当てを解除する必要はありません。
もう役に立たない。コレクターは次の場合に自動的にメモリをリサイクルします。
それ以外の方法ではアクセスできないと判断します。簡単な例
そのような使用法は [ここ](simple_example.md) にあります。

コレクターは多くのプログラミング言語実装でも使用されます。
C を中間コードとして使用するか、より簡単に実行したい場合
C ライブラリとの相互運用、または単純なコレクターを好む
インタフェース。インターフェイスの詳細については、を参照してください。
[ここ](gcinterface.md)。

あるいは、ガベージ コレクターを [リーク ディテクタ](leak.md) として使用することもできます。
ただし、それが主な目的ではありません。

通常、複数のバージョンが提供されています
[ダウンロード](https://github.com/bdwgc/bdwgc/wiki/Download): プレビュー、安定版、
遺産。通常は、「最新の安定した」リリースとしてマークされたものを使用する必要があります。
プレビュー バージョンには追加機能やプラットフォーム サポートが含まれている場合がありますが、
十分にテストされていない可能性があります。各バージョンの変更点一覧
[releases](https://github.com/bdwgc/bdwgc/releases) ページで指定されています。
開発バージョン (スナップショット) は、の master ブランチで入手できます。
GitHub 上の [bdwgc git](https://github.com/bdwgc/bdwgc) リポジトリ。

C および C++ における保守的なガベージ コレクションの賛否両論は次のとおりです。
[ここ](http://www.hboehm.info/gc/issues.html) で簡単に説明しました。

ガベージ コレクター コードの著作権は次のとおりです。
[ハンス-J.ベーム](http://www.hboehm.info)、アラン J. デマーズ、
[ゼロックス株式会社](https://ja.wikipedia.org/wiki/Xerox)、
[シリコン グラフィックス](https://en.wikipedia.org/wiki/Silicon_Graphics)、
[Hewlett-Packard Company](http://www.hp.com/)、
[Ivan Maidanski](https://github.com/ivmai)、および一部は他の人によるものです。
最小限の制限の下で、料金を支払うことなく使用およびコピーすることができます。
詳細については、ディストリビューション内の LICENSE ファイルを参照してください。
**現状のまま提供され、明示的または黙示的な保証は一切ありません。
いかなる使用も自己責任で行ってください。**

経験的に、このコレクターはほとんどの未変更の C プログラムで動作します。
`malloc`と`calloc`を`GC_malloc`呼び出しに置き換え、`realloc`を置き換えます。
`GC_realloc`呼び出し (および`reallocf`と`GC_reallocf`) を使用し、削除します
`free`が呼び出されます。例外について議論します
[こちら](http://www.hboehm.info/gc/issues.html)。

## プラットフォーム

コレクターは完全に移植可能ではありませんが、ディストリビューションにはポートが含まれています
ほとんどの標準的な PC および UNIX/Linux プラットフォームに対応します。コレクターは機能するはずです
Linux、Android、BSD バリアント、OS/2、Windows (Win32 および Win64)、macOS、
iOS、HP/UX、Solaris、Tru64 (OSF/1)、Irix、Symbian およびその他のオペレーティング システム。
一部のプラットフォームは他のプラットフォームよりも洗練されています (サポートが強化されています)。

Irix`pthreads`、Linux スレッド、Windows スレッド、Solaris スレッド (`pthreads`)
のみ)、HP/UX 11`pthreads`、Tru64`pthreads`、および Darwin スレッドがサポートされています。

ライブラリを移植する方法については、[こちら](porting.md) も参照してください。
新しいプラットフォーム。

## コレクターの詳細

コレクターは [マークスイープ](http://www.hboehm.info/gc/complexity.html) を使用します。
アルゴリズム。運用中に増分および世代別の収集を提供します。
適切な種類の仮想メモリ サポートを提供するシステム。 (現在はこれ
SunOS 4.x および 5.x、IRIX、Tru64 UNIX、Linux、および Windows が含まれます。
) [ファイナライゼーション](finalization.md) コードを呼び出すことができます。
オブジェクトが収集されたとき。型情報を利用できる
そのような情報が提供されている場合にポインタを見つけるために使用されますが、通常はこれが使用されます。
そのような情報なしで。次の`README`および`gc.h`ファイルを参照してください。
詳細については配布をご覧ください。

実装の概要については、[こちら](gcdescr.md) を参照してください。

ガベージ コレクターのディストリビューションには、C 文字列 (`cord.h`ファイル) パッケージが含まれています
これにより、長い文字列に対する高速な連結と部分文字列操作が可能になります。
全体を表すシンプルな`curses`ベースおよび Windows ベースのエディター
コード形式のファイルがサンプルアプリケーションとして含まれています。  [cords.md](cords.md) を参照してください。
詳細についてはファイルを参照してください。

非増分コレクタのパフォーマンスは、通常、次のものと競合します。
`malloc`/`free`の実装。スペースと時間の両方のオーバーヘッドが発生する可能性があります。
`malloc`/`free`用に書かれたプログラムではわずかに高いだけです (Detlefs を参照)
ドッサーとゾーンの
[大規模な C および C++ プログラムのメモリ割り当てコスト](https://www.semanticscholar.org/paper/Memory-allocation-costs-in-large-C-and-C%2B%2B-programs-Detlefs-Dosser/49b2b2cec4ce52493c031d964fb3be31d1e02b77))。
主に非常に小さなオブジェクトを割り当てるプログラムの場合、コレクターは次のようになります。
もっと早く;主に大きなオブジェクトを割り当てるプログラムの場合は遅くなります。
コレクターがマルチスレッド環境で使用され、次のように構成されている場合
スレッドローカル割り当ての場合、場合によってはパフォーマンスを大幅に上回る可能性があります
`malloc`/`free`時間内の割り当て。

また、多くの場合、追加のオーバーヘッドは、
例によって補償されます。プログラムを作成して調整するとコピーが減少する
ゴミ収集用に。

## さらに読む

**以下に、ガベージ コレクション全般に​​関する情報を示します。**

ポール・ウィルソンの
[ガベージ コレクション ftp アーカイブ](ftp://ftp.cs.utexas.edu/pub/garbage)
そして
[GC 調査](https://ftpmirror.infania.net/sites/ftp.leo.org/history/doc/programming/gcsurvey.ps.Z)。

レイブンブルック
[メモリ管理リファレンス](http://www.memorymanagement.org/)。

David Chase の [GC FAQ](http://www.iecc.com/gclist/GC-faq.html)。

リチャード・ジョーンズ
【ガベージコレクションページ】(https://www.cs.kent.ac.uk/people/staff/rej/gc.html)
および彼の[本](http://www.cs.kent.ac.uk/people/staff/rej/gcbook/gcbook.html)
ページに記載されています。

**以下の論文では、私たちが使用するコレクター アルゴリズムと
より高いレベルでの基本的な設計上の決定:**

(下位レベルの詳細の一部は、[ここ](gcdescr.md) で参照できます。)

前者は著作権上の理由から電子的には入手できません。
他のほとんどは ACM の著作権の対象となります。

Boehm, H.、動的メモリ割り当てとガベージ コレクション、
_Computers in Physics 9_、3、1995 年 5 月/6 月、297 ～ 303 ページ。これは指示されています
メモリ割り当てに慣れていない洗練された聴衆に対して
問題。アルゴリズムの詳細は実装のものとは異なります。そこには
これは編集者への関連レターであり、次号での軽微な修正です。

ベーム、H.、M. ワイザー、
[非協力的な環境でのガベージ コレクション](http://www.hboehm.info/spe_gc_paper/)、
_Software Practice and Experience_、1988 年 9 月、807 ～ 820 ページ。

ベーム、H.、A. デマース、S. シェンカー、
[ほぼ並列のガベージ コレクション](http://www.hboehm.info/gc/papers/pldi91.ps.Z)、
プログラミング言語設計に関する ACM SIGPLAN '91 カンファレンスの議事録
および実装、_SIGPLAN Notices 26_、6 (1991 年 6 月)、157 ～ 164 ページ。

ベーム、H.、
[スペース効率の良い保守的なガベージ コレクション](http://www.hboehm.info/gc/papers/pldi93.ps.Z)、
プログラミング言語設計に関する ACM SIGPLAN '93 カンファレンスの議事録
および実装、_SIGPLAN Notices 28_、6 (1993 年 6 月)、197 ～ 206 ページ。

Boehm, H.、ガベージ コレクターのキャッシュ ミスの削減、
2000 年のメモリ管理に関する国際シンポジウムの議事録。
[正式版](https://dl.acm.org/doi/10.1145/362422.362438)。
コレクターに組み込まれたプリフェッチ戦略について説明します。
いくつかのプラットフォーム。 _mark-sweet_ コレクターのスイープ フェーズが必要な理由を説明します。
実際には別個のフェーズであるべきではありません。

M. Serrano、H. Boehm、スキーム プログラムのメモリ割り当てについて、
_第 5 回 ACM SIGPLAN 機能に関する国際会議の議事録
「プログラミング_」、2000 年、カナダ、モントリオール、245 ～ 256 ページ。
[正式版](https://dl.acm.org/doi/10.1145/357766.351264)。
コレクタのデバッグ機能についての説明が含まれています。
記憶保持の原因を特定します。

ベーム、H.、
[高速マルチプロセッサ メモリ割り当てとガベージ コレクション](https://www.researchgate.net/publication/242553754_Fast_multiprocessor_memory_allocation_and_garbage_collection)。
並列収集アルゴリズムについて説明し、いくつかのパフォーマンスを示します。
結果。

Boehm, H.、保守的なガベージ コレクターの境界スペース使用法、
_2002 年 ACM SIGPLAN-SIGACT 原則シンポジウムの議事録
プログラミング言語_、2002 年 1 月、93-100 ページ。
[正式版](https://dl.acm.org/doi/10.1145/565816.503282)。
より確実性を高めるためのコレクター機能についての説明が含まれています。
無制限のヒープ増加の可能性をテストします。

**次の文書では、必要な言語とコンパイラの制限について説明しています。
保守的なガベージ コレクションの安全性を保証するため:**

2 番目の論文の作成を許可してくれた John Levine と JCLT に感謝します。
電子的に入手可能であり、最終バージョンの PostScript も提供されます。

ベーム、H.、
[シンプルなガベージ コレクターの安全性](http://www.hboehm.info/gc/papers/pldi96.ps.gz)、
プログラミング言語設計に関する ACM SIGPLAN '96 カンファレンスの議事録
そして実装。

ベーム、H.、D. チェイス、
[ガベージコレクタセーフな C コンパイルの提案](http://www.hboehm.info/gc/papers/boecha.ps.gz)、
_Journal of C Language Translation 4_、2 (1992 年 12 月)、126-141 ページ。

**その他の関連情報:**

デトレフ家、ドッサー家、ゾーン家
[大規模な C および C++ プログラムにおけるメモリ割り当てコスト](https://www.semanticscholar.org/paper/Memory-allocation-costs-in-large-C-and-C%2B%2B-programs-Detlefs-Dosser/49b2b2cec4ce52493c031d964fb3be31d1e02b77)。
これはベーム・デマース・ヴァイザーコレクターの性能比較です。
`malloc`/`free`用に作成されたプログラムを使用して、`malloc`/`free`に変換します。

ジョエル・バートレットの
[主に C++ 用の保守的なガベージ コレクターをコピーしています](https://ftp.zx.net.nz/pub/archive/ftp.digital.com/pub/DEC/WRL/research-reports/WRL-TN-12.ps)。

ジョン・エリスとデヴィッド・デトレフス
[「C++ の安全で効率的なガベージ コレクション」](https://dl.acm.org/doi/10.5555/1267974.1267983)
提案。

[ヘンリー・ベイカーの研究論文アーカイブ](https://web.archive.org/web/20200212080133/http://home.pipeline.com/~hbaker1/)。

ハンス・ベームのスライド
[割り当てと GC の神話](http://www.hboehm.info/gc/myths.ps) について説明します。

## BDWGC サイトで提供される情報

[既知の BDWGC ユーザー](https://github.com/bdwgc/bdwgc/wiki/Known-clients) リスト。

ISMM 2004 のチュートリアル スライド:
[ベーム・デマース・ワイザー保守派ガベージコレクター](http://www.hboehm.info/gc/04tutorial.pdf)。

[FAQ(よくある質問)一覧](faq.md)。

ディストリビューションを含む [ディレクトリ](http://www.hboehm.info/gc/gc_source/)
すべてのガベージ コレクター リリースのファイル。  重複します
GitHub の [ダウンロード](https://github.com/bdwgc/bdwgc/wiki/Download) ページ。

## ドキュメント ファイル

以下のドキュメントは一般にプラットフォーム固有ではありません。

[コレクターの構築方法と使用方法の簡単な図](simple_example.md)。

[ガベージ コレクターへの代替インターフェイスの説明](gcinterface.md)。

[ガベージ コレクターをリーク検出器として使用する方法](leak.md)。

[ガベージ コレクションされたアプリケーションのデバッグに関するヒント](debugging.md)。

[ガベージ コレクターの実装の概要](gcdescr.md)。

[高速ポインター ルックアップに使用されるデータ構造](tree.md)。

[マルチプロセッサに対するコレクタのスケーラビリティ](scale.md)。

[autoconf/configure を使用したライブラリのビルド手順](autoconf.md)。

[cmake を使用したライブラリのビルド手順](cmake.md)。

[実行時のコレクターの動作に影響を与える環境変数のリスト](environment.md)。

[コレクターに影響を与えるコンパイル時マクロのリスト](macros.md)。

[ファイナライズ機能の詳細](finalization.md)。

[ライブラリを新しいプラットフォームに移植する方法に関する説明](porting.md)。

[GC 上に構築されたコード ライブラリの説明](cords.md)。

## 詳しい背景情報

[保守的なガベージ コレクターのスペース使用量の制限を確立する試み](http://www.hboehm.info/gc/bounds.html)。

[マークスイープとガベージコレクタのコピーとその複雑さ](http://www.hboehm.info/gc/complexity.html)。

[「なぜ保守的なガベージコレクターなのか?」](http://www.hboehm.info/gc/conservative.html)
(他のものと比較した、保守的なガベージ コレクターの長所と短所
コレクター）。

[保守的なガベージ コレクションの長所と短所](http://www.hboehm.info/gc/issues.html)
(ガベージ コレクションと手動メモリ管理に関連する問題
C/C++)。

の例
[高価な明示的な割り当て解除](http://www.hboehm.info/gc/example.html)
この場合、ガベージ コレクションにより実装が大幅に高速化されます。
同期の減少の結果です。

ディスカッションするスライド セット
[非移動ガベージ コレクターのパフォーマンス](http://www.hboehm.info/gc/nonmoving/)。

ディスカッションするスライド セット
[「デストラクター、ファイナライザー、および同期」](http://www.hboehm.info/popl03/web/)、
POPL 2003 (および対応する
[論文](https://dl.acm.org/doi/10.1145/604131.604153))。

[Java/Scheme/C/C++ ガベージ コレクション ベンチマーク](http://www.hboehm.info/gc/gc_bench/)。

講演用のスライド
[メモリ割り当てに関する神話](http://www.hboehm.info/gc/myths.ps)。

OOPSLA 98 のスライド
[ガベージコレクショントーク](http://www.hboehm.info/gc/gctalk.ps)。

その他の [関連論文](http://www.hboehm.info/gc/papers/)。

## 連絡先と新しいリリースのお知らせ

GitHub と Stack Overflow は、コミュニケーションのための主要な 2 つの場所です。

技術的な質問 (方法、仕組みなど) を投稿する必要があります。
[Stack Overflow](https://stackoverflow.com/questions/tagged/boehm-gc) に送信
_boehm-gc_ タグ。

貢献するには、コードを最新のものにリベースしてください
[マスター](https://github.com/bdwgc/bdwgc/tree/master/) を送信してください
GitHub への [プル リクエスト](https://github.com/bdwgc/bdwgc/pulls)。

バグを報告したり、新しい機能を提案 (リクエスト) するには、
[GitHub の問題](https://github.com/bdwgc/bdwgc/issues)。必ずご確認ください
まだ他の人から報告されていません。

リリースごとに通知を受け取るには、購読してください
[RSS フィードをリリース](https://github.com/bdwgc/bdwgc/releases.atom)。
すべての問題とプルリクエストに関する通知が利用可能です
プロジェクトを[監視](https://github.com/bdwgc/bdwgc/watchers)することで。

メーリング リスト (bdwgc-announce@lists.opendylan.org、bdwgc@lists.opendylan.org、
以前の gc-announce@linux.hpl.hp.com と gc@linux.hpl.hp.com) は、
現時点で使用されています。コンテンツは利用可能です
で
[bdwgc-announce](https://github.com/bdwgc/bdwgc/files/1037650/bdwgc-announce-mailing-list-archive-2014_02.tar.gz)
そして
[bdwgc](https://github.com/bdwgc/bdwgc/files/1038163/bdwgc-mailing-list-archive-2017_04.tar.gz)
それぞれアーカイブファイル。 gc リスト アーカイブも読み取ることができます
[Narkive](http://bdwgc.opendylan.narkive.com) で。

コレクターに関する事前の議論は GCC Java メーリングで行われています。
このリストのアーカイブは [ここ](http://gcc.gnu.org/ml/java/) にあります。
[gclist@iecc.com](http://lists.tunes.org/mailman/listinfo/gclist) で。
