# 索引

## Proot-Distro 安装 Trisquel
* [安装环境](#安装trisquel环境)
* [配置国内镜像源](#配置国内镜像源)
* [配置环境](#配置trisquel环境)
* [安装桌面](#安装桌面)
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

## 配置国内镜像源
编辑：
```
nano /etc/apt/sources.list
```
写入：
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
编辑：
```
nano /etc/apt/apt.conf.d/99fast
```
写入：
```
Acquire::Retries "5";
Acquire::http::Timeout "20";
Acquire::https::Timeout "20";

Acquire::http::Pipeline-Depth "0";
Acquire::http::No-Cache "true";

Acquire::Queue-Mode "access";
APT::Get::Assume-Yes "false";
```
编辑：
```
nano /etc/apt/apt.conf.d/99compress
```
写入：
```
Acquire::CompressionTypes::Order:: "gz";
```
更新密钥
```
apt install trisquel-keyring
```
清除缓存
```
apt clean
```
更新源
```
apt update && apt upgrade -y
```

## 配置Trisquel环境

1. 安装基础软件包
```
apt update
```
```
apt install sudo nano adduser -y
```
2. 创建用户
```
adduser demo
```
3. 给用户添加权限
```
nano /etc/sudoers
```
```
demo ALL=(ALL:ALL) ALL
```
4. 设置中文语言
```
dpkg-reconfigure locales
```
* 第一次输入zh_CN.UTF-8 UTF-8对应的编号

* 第二次输入zh_CN.UTF-8对应的编号

编辑：
```
nano /etc/environment
```
写入：
```
LANGUAGE="zh_CN:zh"
LANG="zh_CN.UTF-8"
LC_ALL=zh_CN.UTF-8
```
5. 设置时区
```
dpkg-reconfigure tzdata
```
* 第一次输入Asia对应的编号

* 第二次输入Shanghai对应的编号 查看当前时区

## 安装桌面

### XFCE4桌面
```
apt install xfce4 xfce4-terminal dbus-x11
```
### LXDE桌面
```

```
### MATE桌面
```

```
### KDE桌面
```

```




