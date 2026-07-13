# CMake を使用して bdwgc をビルドする

UNIX および Win32 バイナリ (32 ビットと 64 ビットの両方) は、CMake を使用してビルドできます。
CMake は、[`automake`](autoconf.md) のようなオープンソース ツールです。
メイクファイル。

CMake (v3.14.5 以降) は以下を生成できます。

* ボーランドのメイクファイル
* MSYS メイクファイル
* MinGW メイクファイル
* NMake メイクファイル
* Unix メイクファイル
* Visual Studio 16 2019
* Visual Studio 15 2017
* Visual Studio 14 2015
* Visual Studio 12 2013
* Visual Studio 11 2012
* Visual Studio 10 2010
* Visual Studio 9 2008
*ワトコムWMake


## ビルドプロセス

手順は次のとおりです。

1. cmake をインストールします (例: [cmake.org](https://cmake.org/) から)。

2.`cmake`実行可能ファイルを含むディレクトリを`PATH`環境に追加します
変数;

3. bdwgc ルート ディレクトリから cmake を実行し、`-G`でターゲットを渡します。
オプション - 例:`cmake -G "Visual Studio 9 2008"`と入力し、`gc.sln`を使用します
`gc`ライブラリを構築するために cmake によって生成されたファイル。

注:

*`gccpp`および`gctba`をビルドするには、`-D enable_cplusplus=ON`オプションを指定します
ライブラリ (つまり、bdwgc C++ サポートを提供するもの);

*`-D BUILD_TESTING=OFF`オプションを指定すると、テストのコンパイルがスキップされます。

ビルド ディレクトリから cmake を実行して、ルートの外側にビルドすることもできます。
ソースツリー - 後者へのパスを指定するだけです。例:

```sh
mkdir build
cd build
cmake -G "Visual Studio 9 2008" ..
cmake --build . --config Release
ctest --build-config Release -V
```

Linux のサンプルは次のとおりです (ビルド、テスト、インストール、C++ サポートなし)。

```sh
mkdir build
cd build
cmake ..
cmake --build .
ctest
make install
```


# 入力

cmake への主な入力は、bdwgc ルートにある`CMakeLists.txt`ファイル (スクリプト) です。
ディレクトリ。  ヘルプが必要な場合は、[cmake.org](https://cmake.org/) にアクセスしてください。


# bdwgc をインポートする方法

別のプロジェクトでは、(必要なバージョンの) bdwgc をそのプロジェクトの 1 つとして追加できます。
`CMakeLists.txt`ファイルに次のような依存関係があります。

```cmake
find_package(BDWgc <version> REQUIRED)
add_executable(Foo foo.c)
target_link_libraries(Foo BDWgc::gc)
```

その他のエクスポートされたライブラリは、`cord`、`gccpp`、`gctba`です。
