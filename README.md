Japanese follows English.
日本語は，英語に続きます．

# What's this?
A QEMU fork to emulate LEGO Education SPIKE Prime Hub machine model.
This is used to test and debug [SPIKE-RT](https://github.com/spike-rt/spike-rt).

## Installation
### Build from source
Prepare a build environment according to [Hosts/Linux - QEMU](https://wiki.qemu.org/Hosts/Linux).  
An example for Ubuntu:
```bash
sudo apt install build-essential git libglib2.0-dev libfdt-dev libpixman-1-dev zlib1g-dev ninja-build
```

To compile, execute the commands below.
```bash
git clone git@github.com:spike-rt/qemu.git
cd qemu
mkdir build && cd build
../configure --target-list=arm-softmmu
ninja qemu-system-arm
```

By adding `--static` option to the `configure` command, you can build a statically linked binary.  
But some environment may fail to build because static versions of some dependent libraries are not provided.
For example, it seems to be possible to build on Ubuntu 20.04, but not on Ubuntu 22.04.

# これは何？
QEMUにLEGO Education SPIKE Prime Hub のマシンモデルを追加したもの．
SPIKE-RTのテストとデバッグに使用している．

## 導入
### ソースからのビルド
[Hosts/Linux - QEMU](https://wiki.qemu.org/Hosts/Linux) にしたがってビルド環境を構築する．  
Ubuntu の例
```bash
sudo apt install build-essential git libglib2.0-dev libfdt-dev libpixman-1-dev zlib1g-dev ninja-build
```

以下を実行し，コンパイル．
```bash
git clone git@github.com:spike-rt/qemu.git
cd qemu
mkdir build && cd build
../configure --target-list=arm-softmmu
ninja qemu-system-arm
```

なお，`configure`時に，`--static`を指定することで，スタティンクリンクされたバイナリをビルド可能である．  
しかし，環境によっては，依存ライブラリの静的ライブラリが用意されていないためにビルドできないことがある．
例えば，Ubuntu 20.04ではビルド可能だが，Ubuntu 22.04ではビルドできないようである．