# hit-oslab 环境搭建

哈工大李治军操作系统课程环境搭建

## 安装 ubuntu12.04.5

ubuntu-12.04.5-dvd-amd64.iso

## 安装实验环境

下载 hit-oslab-linux-20110823.tar.gz
`tar hit-oslab-linux-20110823.tar.gz -xvf -C ~/`

## 配置

### bin86

`sudo apt-get install bin86`

### 32位兼容库

`sudo apt-get install libc6-dev-i386`

### C语言编译环境

`sudo apt-get install build-essential`

### 安装 gcc

- 下载 [gcc3.4](http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/)
>
cpp-3.4_3.4.6-6ubuntu3_amd64.deb  
gcc-3.4-base_3.4.6-6ubuntu3_amd64.deb
g++-3.4_3.4.6-6ubuntu3_amd64.deb  
libstdc++6-dev_3.4.6-6ubuntu3_amd64.deb
gcc-3.4_3.4.6-6ubuntu3_amd64.deb

- 安装

```bash
sudo dpkg -i *.deb
```

- 修改默认版本

  - 查看下安装的结果
    `$ ls /usr/bin/gcc* -ll`

    ```bash
    lrwxrwxrwx 1 root root      7 Mar 22 21:08 /usr/bin/gcc -> gcc-4.6
    -rwxr-xr-x 1 root root  85552 Jan  3  2008 /usr/bin/gcc-3.4
    -rwxr-xr-x 1 root root 306200 Apr 15  2012 /usr/bin/gcc-4.8
    -rwxr-xr-x 1 root root  16090 Jan  3  2008 /usr/bin/gccbug-3.4
    ```

    - 配置优先级

    ```bash
    $ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-3.4 40
    $ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.6 30
    ```

    - 配置默认版本
    $ sudo update-alternatives --config gcc

    ```bash
    There are 2 choices for the alternative gcc (providing /usr/bin/gcc).

      Selection    Path              Priority   Status
    ------------------------------------------------------------
    * 0            /usr/bin/gcc-3.4   40        auto mode
      1            /usr/bin/gcc-3.4   40        manual mode
      2            /usr/bin/gcc-4.6   30        manual mode

    Press enter to keep the current choice[*], or type selection number:
    # 这里直接回车或者输入1
    ```

    - 查看gcc版本

    ```bash
    $ gcc -v
    Reading specs from /usr/lib/gcc/i486-linux-gnu/3.4.6/specs
    Configured with: ../src/configure -v --enable-languages=c,c++,f77,pascal --prefix=/usr --libexecdir=/usr/lib --with-gxx-include-dir=/usr/include/c++/3.4 --enable-shared --with-system-zlib --enable-nls --without-included-gettext --program-suffix=-3.4 --enable-__cxa_atexit --enable-clocale=gnu --enable-libstdcxx-debug --with-tune=pentium4 i486-linux-gnu
    Thread model: posix
    gcc version 3.4.6 (Ubuntu 3.4.6-6ubuntu3)
    ```

### 编译内核

```bash
cd ~/workspace/oslab/linux-0.112
make
```

### 安装依赖库

```bash
sudo apt-get install libsm6
sudo apt-get install libsm6:i386
sudo apt-get install libx11-6
sudo apt-get install libx11-6:i386
sudo apt-get install libxpm4:i386
sudo apt-get install libstdc++6:i386
```

## 运行

`./run`

## 调试

- 汇编

`./dbg-asm`
然后 bochs 按 c 运行

- c
  - 一个终端 `./dbg-asm`
  - 一个中断 `./rungdb`
   然后 gdb 调试
