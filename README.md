# malloc memo

* TODO: mallocの対象処理や補足などを付加する
* TODO: versionの項目は必要かどうかを考える
* TODO: 他のmallocを追加する
* TODO: 項目を埋める

malloc table

| malloc name  | author                | apps             | year | version | license                                                                                                      | homepage                                                                                       | github                                                                                                                                                                                                                                                                                                          | paper                                                                                                                                                                                                            | conference                                                                     |
|--------------|-----------------------|------------------|------|---------|--------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| glibc malloc |                       | Ubuntu and so on |      |         | [GNU Lesser General Public License]( https://www.gnu.org/software/libc/manual/pdf/libc.pdf )                 | [The GNU C Library]( https://www.gnu.org/software/libc/libc.html )                             |                                                                                                                                                                                                                                                                                                                 | [libc\.pdf]( https://www.gnu.org/software/libc/manual/pdf/libc.pdf )                                                                                                                                             |                                                                                |
| JEmalloc     | Jason Evans (FreeBSD) | FreeBSD, Firefox | 2006 |         | [?]( https://github.com/jemalloc/jemalloc/blob/dev/COPYING )                                                 | [jemalloc]( http://jemalloc.net/ )                                                             | [jemalloc/jemalloc]( https://github.com/jemalloc/jemalloc )                                                                                                                                                                                                                                                     | [jemalloc\.pdf]( https://www.bsdcan.org/2006/papers/jemalloc.pdf )                                                                                                                                               |                                                                                |
| TCMalloc     | Google                | MongoDB          |      |         | [BSD Licenses]( https://github.com/gperftools/gperftools/blob/master/COPYING )                               | [TCMalloc : Thread\-Caching Malloc]( http://goog-perftools.sourceforge.net/doc/tcmalloc.html ) | [GitHub \- gperftools/gperftools: Main gperftools repository]( https://github.com/gperftools/gperftools )                                                                                                                                                                                                       |                                                                                                                                                                                                                  |                                                                                |
| TBBMalloc    | Intel                 |                  |      |         | [Apache License 2.0]( https://github.com/intel/tbb/blob/tbb_2019/LICENSE )                                   |                                                                                                | [tbb/src/tbbmalloc at tbb\_2019 · intel/tbb]( https://github.com/intel/tbb/tree/tbb_2019/src/tbbmalloc )                                                                                                                                                                                                       | [The Foundations for Scalable Multi\-core Software in Intel® Threading Building Blocks]( https://pdfs.semanticscholar.org/7b55/610961c63b86141f37c68e73e0326fae0693.pdf )                                       |                                                                                |
| snmalloc     | Microsoft             |                  | 2019 |         | [ MIT LICENSE ]( https://github.com/microsoft/snmalloc/blob/master/LICENSE )                                 |                                                                                                | [GitHub \- microsoft/snmalloc: Message passing based allocator]( https://github.com/microsoft/snmalloc )                                                                                                                                                                                                        |                                                                                                                                                                                                                  | ISMM                                                                           |
| mimalloc     | Microsoft             |                  | 2019 |         | [ MIT LICENSE ]( https://github.com/microsoft/mimalloc/blob/master/LICENSE )                                 |                                                                                                | [GitHub \- microsoft/mimalloc: mimalloc is a compact general purpose allocator with excellent performance\.]( https://github.com/microsoft/mimalloc )                                                                                                                                                           | [Mimalloc: Free List Sharding in ActionMicrosoft Technical Report MSR\-TR\-2019\-18, June 2019\.]( https://www.microsoft.com/en-us/research/uploads/prod/2019/06/mimalloc-tr-v1.pdf )                            | Microsoft Technical Report                                                     |
| SuperMalloc  | MIT                   |                  | 2015 |         | [ MIT "expat" license, or the GPLv3 license ]( https://github.com/kuszmaul/SuperMalloc/blob/master/LICENSE ) |                                                                                                | [kuszmaul/SuperMalloc]( https://github.com/kuszmaul/SuperMalloc )                                                                                                                                                                                                                                               | [SuperMalloc: A Super Fast Multithreaded Malloc for 64\-bit Machines]( http://supertech.csail.mit.edu/papers/Kuszmaul15.pdf )                                                                                    | ISMM                                                                           |
| Mesh         |                       |                  | 2019 |         | [Apache License 2.0]( https://github.com/plasma-umass/Mesh/blob/master/LICENSE )                             |                                                                                                | [plasma\-umass/Mesh: A memory allocator that automatically reduces the memory footprint of C/C\+\+ applications\.]( https://github.com/plasma-umass/Mesh )                                                                                                                                                      | [Mesh: Compacting Memory Management for C/C\+\+ Applications]( https://arxiv.org/pdf/1902.04738.pdf )                                                                                                            | PLDI                                                                           |
| Hoard        |                       |                  | 2000 |         | [Apache License 2.0]( https://github.com/emeryberger/Hoard/blob/master/LICENSE )                             | [Hoard]( http://hoard.org/ )                                                                   | [emeryberger/Hoard: The Hoard Memory Allocator: A Fast, Scalable, and Memory\-efficient Malloc for Linux, Windows, and Mac\.]( https://github.com/emeryberger/Hoard )                                                                                                                                           | [berger\-asplos2000\.pdf]( https://people.cs.umass.edu/~emery/pubs/berger-asplos2000.pdf )                                                                                                                       | Architectural Support for Programming Languages and Operating Systems (ASPLOS) |
| ptmalloc     |                       |                  |      |         | [Wolfram Gloger's malloc homepage]( http://www.malloc.de/en/ )                                               |                                                                                                | [Wolfram Gloger's malloc homepage]( http://www.malloc.de/en/ )                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                  |                                                                                |
| scalloc      |                       |                  | 2015 |         |                                                                                                              |                                                                                                |                                                                                                                                                                                                                                                                                                                 | [Fast, Multicore\-Scalable, Low\-Fragmentation Memory Allocation through Large Virtual Memory and Global Data Structures]( http://cs.uni-salzburg.at/~ck/content/publications/conferences/OOPSLA15-Scalloc.pdf ) | Object Oriented Programming Systems Languages and Applications (OOPSLA)        |
| rpmalloc     |                       |                  |      |         | [public domain or MIT LICENSE]( https://github.com/mjansson/rpmalloc/blob/develop/LICENSE )                  |                                                                                                | [mjansson/rpmalloc: Public domain cross platform lock free thread caching 16\-byte aligned memory allocator implemented in C]( https://github.com/mjansson/rpmalloc )                                                                                                                                           |                                                                                                                                                                                                                  |                                                                                |
| SSMalloc     |                       |                  | 2012 |         |                                                                                                              |                                                                                                |                                                                                                                                                                                                                                                                                                                 | [SSMalloc: A Low-latency, Locality-conscious Memory Allocator with Stable Performance Scalability]( https://ipads.se.sjtu.edu.cn/_media/publications/ssmalloc-apsys2012.pdf )                                    | Asia-Pacific Workshop on Systems (APSys)                                       |
| SFMalloc     |                       |                  | 2011 |         |                                                                                                              |                                                                                                |                                                                                                                                                                                                                                                                                                                 | [SFMalloc: A Lock\-Free and Mostly Synchronization\-Free Dynamic Memory Allocator for Manycores \- IEEE Conference Publication]( https://ieeexplore.ieee.org/abstract/document/6113834 )                         | Parallel Architectures and Compilation Techniques(PACT)                        |
| Streamflow   |                       |                  | 2006 |         |                                                                                                              |                                                                                                |                                                                                                                                                                                                                                                                                                                 | [Scalable locality-conscious multithreaded memory allocation]( http://people.cs.vt.edu/~scschnei/papers/ismm06.pdf )                                                                                             | ISMM                                                                           |
| nedmalloc    |                       |                  |      |         |                                                                                                              | [ned Productions \- nedmalloc]( https://www.nedprod.com/programs/portable/nedmalloc/ )         | [ned14/nedmalloc: An EXTREMELY FAST portable thread caching malloc implementation written in C for multiple threads without lock contention based on dlmalloc\. Optimised for x86 and x64\. Compatible with C\+\+\. Can patch itself into existing binaries on Windows\.]( https://github.com/ned14/nedmalloc ) |                                                                                                                                                                                                                  |                                                                                |
| ltalloc      |                       |                  |      |         |                                                                                                              |                                                                                                |[r\-lyeh\-archived/ltalloc: LightweighT Almost Lock\-Less Oriented for C\+\+ programs memory allocator]( https://github.com/r-lyeh-archived/ltalloc )|                                                                                                                                                                                                                  |                                                                                |

----

## snmalloc
[microsoft/snmalloc: Message passing based allocator]( https://github.com/microsoft/snmalloc )

### how to get
```
git clone https://github.com/microsoft/snmalloc
cd snmalloc/
```

### how to build
```
mkdir build
cd build
cmake -G Ninja .. -DCMAKE_BUILD_TYPE=Release
ninja
```

### how to run
```
# on linux
LD_PRELOAD=./libsnmallocshim.so bash
# on darwin
DYLD_FORCE_FLAT_NAMESPACE=1 DYLD_INSERT_LIBRARIES=./libsnmallocshim.dylib bash
```

### NOTE
* darwinでは下記のエラーが出現する
```
[1]    32972 abort      DYLD_FORCE_FLAT_NAMESPACE=1 DYLD_INSERT_LIBRARIES=./libsnmallocshim.dylib cur
```

しかし，README.mdの記述としては，macOSでも動作するような記述あり

Ubuntu16.04のdefaultのcmakeのversion(3.5.1)では下記のエラーが出現する
```
CMake 3.8 or higher is required.  You are running version 3.5.1
```

回避方法として，[Releases · Kitware/CMake]( https://github.com/Kitware/CMake/releases )から該当するversionのcmakeのバイナリをダウンロードして使用する
```
wget https://github.com/Kitware/CMake/releases/download/v3.15.2/cmake-3.15.2-Linux-x86_64.tar.gz
tar xvf cmake-3.15.2-Linux-x86_64.tar.gz

./cmake-3.15.2-Linux-x86_64/bin/cmake -G Ninja .. -DCMAKE_BUILD_TYPE=Release
ninja
```

しかし，ビルド時にパースエラーとなった

### links
* [論文「snmalloc: A Message Passing Allocator」\(ISMM 2019\)]( https://nhiroki.jp/2019/07/08/paper-snmalloc-a-message-passing-allocator )

----

## Mesh
[plasma\-umass/Mesh: A memory allocator that automatically reduces the memory footprint of C/C\+\+ applications\.]( https://github.com/plasma-umass/Mesh )

### how to get
```
git clone --recurse-submodules https://github.com/plasma-umass/mesh
cd mesh
```

### how to build
```
./configure; make; sudo make install
```

### how to run
```
# on linux
LD_PRELOAD=./libmesh.so bash
# on darwin
DYLD_FORCE_FLAT_NAMESPACE=1 DYLD_INSERT_LIBRARIES=./libmesh.dylib bash
```

### NOTE
> Mesh runs on Linux; macOS support should be considered alpha-quality, and Windows is a work-in-progress.

* macOSにおいて，`sigaction`や`pthread_create`あたりでビルドエラーが出現する
* Ubuntu16.04において， `pthread`でビルドエラー

### links
* [論文「MESH: Compacting Memory Management for C/C\+\+ Applications」\(PLDI 2019\)]( https://nhiroki.jp/2019/02/26/paper-mesh-compacting-memory-management )

----

## mimalloc
[microsoft/mimalloc: mimalloc is a compact general purpose allocator with excellent performance\.]( https://github.com/microsoft/mimalloc )

### how to get
```
git clone https://github.com/microsoft/mimalloc
cd mimalloc
```

### how to build
```
mkdir -p out/release
cd out/release
cmake ../..
make
```

### how to run
```
# on linux
LD_PRELOAD=./libmimalloc.so bash
# on darwin
DYLD_FORCE_FLAT_NAMESPACE=1 DYLD_INSERT_LIBRARIES=./libmimalloc.dylib bash
```

### NOTE
* darwinでは下記のエラーが出現する
```
[1]    34977 abort      DYLD_FORCE_FLAT_NAMESPACE=1 DYLD_INSERT_LIBRARIES=./libmimalloc.dylib bash
```

しかし，README.mdの記述としては，macOSでも動作するような記述あり

* Ubuntu16.04にて，ビルドと動作ともにOK

### links
* [Microsoft、高性能メモリアロケータ「mimalloc」公開 \| マイナビニュース]( https://news.mynavi.jp/article/20190625-847906/ )
* [mimalloc のメモリ管理 \- Qiita]( https://qiita.com/methane/items/e88901b7392c10cee2c9 )
* [mimalloc を Python で使う \- Qiita]( https://qiita.com/methane/items/3214e7a7413785acd43d )
* [\#tech "Mimalloc: Free List Sharding in Action"を読んだ \- Kotet's Personal Blog]( https://blog.kotet.jp/2019/06/mimalloc/ )
