# 索引

## Proot-Distro 安装 Trisquel
* [安装环境](#安装trisquel环境)
* [配置环境](#配置trisquel环境)
* 安装桌面
* VNC远程连接桌面
* Termux：X11显示桌面

<br>

---
---

<br>

## 安装Trisquel环境

1. 安装 proot-distro
```
pkg update
```
```
pkg install proot-distro
```
2. 安装 Trisquel
```
proot-distro install trisquel
```
3. 登录 Trisquel
```
proot-distro install trisquel
```

## 配置Trisquel环境
编辑
```
sudo nano /etc/apt/sources.list
```
```
# Trisquel 11 Aramo — USTC mirror

deb https://mirrors.ustc.edu.cn/trisquel/ aramo main
deb https://mirrors.ustc.edu.cn/trisquel/ aramo-updates main
deb https://mirrors.ustc.edu.cn/trisquel/ aramo-security main

# Source packages
deb-src https://mirrors.ustc.edu.cn/trisquel/ aramo main
deb-src https://mirrors.ustc.edu.cn/trisquel/ aramo-updates main
deb-src https://mirrors.ustc.edu.cn/trisquel/ aramo-security main
```
```
sudo nano /etc/apt/apt.conf.d/99fast
```
```
Acquire::Retries "5";
Acquire::http::Timeout "20";
Acquire::https::Timeout "20";

Acquire::http::Pipeline-Depth "0";
Acquire::http::No-Cache "true";

Acquire::Queue-Mode "access";
APT::Get::Assume-Yes "false";
```
```
sudo nano /etc/apt/apt.conf.d/99compress
```
```
Acquire::CompressionTypes::Order:: "gz";
```
```
sudo apt install trisquel-keyring
```
```
sudo apt clean
```
```
sudo apt update
```




