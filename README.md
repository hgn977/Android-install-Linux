# 安卓手机安装Linux教程

## 1.安装Termux和Termux:X11

**Termux**：[点击下载](https://github.com/termux/termux-app/releases/download/v0.118.3/termux-app_v0.118.3+github-debug_arm64-v8a.apk)

**Termux:X11**：[点击下载](https://github.com/termux/termux-x11/releases/download/nightly/app-arm64-v8a-debug.apk)

## 2.配置Termux

获取存储权限
```
termux-setup-storage
```

更换清华源
```
termux-change-repo
```

更新软件源
```
pkg update && pkg upgrade -y
```

安装基础软件
```
pkg install x11-repo
```
```
pkg install termux-x11-nightly tur-repo pulseaudio proot-distro wget git
```