# Ubuntu 配置项

## 代理

### apt.conf

Acquire::http::Proxy "http://127.0.0.1:1080/";
Acquire::ftp::proxy "ftp://127.0.0.1:1080/";
Acquire::https::proxy "https://127.0.0.1:1080/";

### .bashrc

cd ~
bash -c zsh

### .zhshrc

export http_proxy=http://127.0.0.1:1080;
export https_proxy=http://127.0.0.1:1080;
export ftp_proxy=http://127.0.0.1:1080;

### git

git config --global user.name "waver"
git config --global user.email "jokerwaver@gmail.com"
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy https://127.0.0.1:1080

## 具体应用场景

### Base

```bash
sudo apt install git zsh curl wget vim
```

### 编译 JDK

1. 安装软件

```bash
sudo apt install build-essential libx11-dev libxext-dev libxrender-dev libxtst-dev libxt-dev libcups2-dev libfreetype6-dev libasound2-dev ccache gawk m4 libasound2-dev libxrender-dev xorg-dev xutils-dev binutils libmotif-dev ant mercurial openjdk-8-jdk systemtap-sdt-dev
```

2. 下载 openjdk10 源码

```bash
hg clone http://hg.openjdk.java.net/jdk10/jdk10
```

3. 获取源码

```bash
    cd jdk10/
    bash ./get_source.sh
```

4. 编译源码

```bash
    bash configure --with-debug-level=fastdebug --enable-dtrace --with-jvm-variants=server --with-target-bits=64 --enable-ccache --with-num-cores=8 --with-memory-size=8000  --disable-warnings-as-errors

    make
```
