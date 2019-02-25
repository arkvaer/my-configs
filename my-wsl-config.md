# 代理

## apt.conf

Acquire::http::Proxy "http://127.0.0.1:1080/";
Acquire::ftp::proxy "ftp://127.0.0.1:1080/";
Acquire::https::proxy "https://127.0.0.1:1080/";

## .bashrc

bash -c zsh

## .zhshrc

cd ~
export http_proxy=http://127.0.0.1:1080;
export https_proxy=http://127.0.0.1:1080;
export ftp_proxy=http://127.0.0.1:1080;

## git

git config --global user.name "waver"
git config --global user.email "jokerwaver@gmail.com"
git config --global https.proxy http://127.0.0.1:1080
git config --global https.proxy https://127.0.0.1:1080
