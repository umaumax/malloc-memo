# malloc memo

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
