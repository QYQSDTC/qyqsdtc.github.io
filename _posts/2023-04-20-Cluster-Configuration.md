---
format: post
title: Cluster Configuration
date: 2023/04/20
tags:
  - linux
  - ubuntu
  - cluster
---

# ubuntu 服务器配置指南

本文主要分为两部分：第一部分为普通人员使用手册；第二部分为开发人员管理维护手册。

## 使用手册

### 添加账户

联系管理员（QYQ）添加。

### SSH 远程登录

**注：服务器地址, Hust1(N522):115.156.147.164, Hust2(N521):115.156.146.114。**

Mac 用户可以直接通过 Termnial， Windows 用户通过命令提示符或者其他 shell 终端如 PowerShell 输入

```
ssh gwphysics@HustX # HustX对应的IP
```

进行登录。

![Login]({{site.baseurl}}/assets/img/login.png)

### 创建密钥对实现免密登陆

输入以下命令创建密钥对

```bash
ssh-keygen -t rsa -C "comment"
```

`-t:` 指定密钥类型可以是: RSA, DSA, ECDSA, 默认是 RSA。

`-c:` 一些 comment 让你记住这密钥是啥

![ssh-keygen]({{site.baseurl}}/assets/img/sshkey.png)

产生了名为`pub`和`pub.pub`的两个密钥, `pub`被称为私钥，保存在本地的计算机上，`pub.pub`是公钥可以随意公开，现在我们把公钥上传到服务器的`~/.ssh`文件夹下，如果没有的可以通过`mkdir ~/.ssh`来创建.

```bash
ssh-copy-id -i pub.pub user_name@HustX
```

如果没有`ssh-copy-id`的需要手动把公钥上传到.ssh 文件夹下，在本地计算机下

```bash
scp pub.pub user_name@HustX:~/.ssh
```

进入远程用户

```bash
cat ~/.ssh/pub.pub >> ~/.ssh/authorized_keys
```

输入远程账户密码后就能开心的免密登陆了。到这，你已经能愉快的连接到服务器上玩耍了。

### 保持 SSH 连接

在本地计算机`.ssh`目录下创建`config`文件，输入以下内容

```bash
Host hust2 # 服务器的名字，设置之后以后只用 ssh 服务器名字
	Hostname HustX # server ip
	user username
	ControlMaster auto
	Controlpath /tmp/ssh-%r@%h:%p
	ControlPersist 1h # 1h 内断线重连
	AddKeysToAgent yes
	IdentityFile ~/.ssh/HustX # 私钥路径
	ServerAliveInterval 10
	ServerAliveCountMax 5
```

### 远程 GUI 登陆

现在就可以通过 Windows 的远程桌面连接到服务器上了,ip 地址为服务器的 IP 地址，端口为默认的 3389：

![remotedesk]({{site.baseurl}}/assets/img/remotedesk.png)

连接之后用户名为自己服务器的用户名、密码：

![remotelogin]({{site.baseurl}}/assets/img/remotelogin.png)

即可进入远程的桌面环境。

#### macOS & Ubuntu

macOS 和 Linux 用户也有相对应的软件，如 macOS 上的 Microsoft Remote Desktop，免费而且好用，操作和 Windows 相似。

![RDP]({{site.baseurl}}/assets/img/RDP.png)

### Some Exemple

#### Miniconda 安装以及配置

我已经为大家准备好了 miniconda 的安装文件，可以通过以下命令来执行安装

```bash
cp /home/Miniconda3-py39_4.12.0-Linux-x86_64.sh user_name/ # copy installation shell script to your dir

./Miniconda3-py39_4.12.0-Linux-x86_64.sh # start installation
```

![miniconda]({{site.baseurl}}/assets/img/miniconda.png)

按回车继续，接下来一路回车直到出现 yes or no，然后输入 yes 开始安装。

![miniconda2]({{site.baseurl}}/assets/img/miniconda2.png)

![miniconda3]({{site.baseurl}}/assets/img/miniconda3.png)

到这里就直接回车，miniconda 会安装到你用户名下的 miniconda 文件夹内。

![miniconda4]({{site.baseurl}}/assets/img/miniconda4.png)

这里选择 yes，会在你的`.bashrc`文件夹内增加以下内容来初始化 conda

![miniconda5]({{site.baseurl}}/assets/img/miniconda5.png)

到此为止，一个带有 python3.9 的 conda 环境就配置好了，接下来只要退出账户，再 ssh back 就能进入 conda 环境了。

![miniconda6]({{site.baseurl}}/assets/img/miniconda6.png)

#### 添加 conda-forge 源

在安装其他包之前建议进行以下 conda 配置

```bash
# Add Conda-forge as default channel
conda config --add channels conda-forge
conda config --set channel_priority strict
```

接下来就能愉快的`conda install`了

![condainstall]({{site.baseurl}}/assets/img/condainstall.png)

这里它提示我有更新版本的 conda 了，等会儿安装完了更新一下。

#### Conda 常用命令

```bash
# update conda itself
conda update -n base -c defaults conda

# update all installed packages
conda update --all

# update specific package
conda update package_name

# create virtual enviroment
conda create -n env_name python==3.9 # create an enviroment with env_name and python3.9 installed

# activate and deactivate enviroment
conda activate env_name
conda deactivate env_name

# install and uninstall packages
conda install/uninstall package_name
```

#### Run Jupiter Notebook from Server

配置好环境之后，我们就可以进行一些应用了，最常用的就是在服务器打开 jupyter 然后坐在宿舍里喝着可乐 happy coding。

为了能够在本地打开服务器端的 jupyter notebook 我们需要在 ssh 的时候进行端口映射，添加`LocalForward` 命令

```bash
Host hust2
	Hostname HustX # HustX ip
	user username
	LocalForward 17190 localhost:7190 # 把本地17190端口映射到服务器端的7190端口
	ControlMaster auto
	Controlpath /tmp/ssh-%r@%h:%p
	#	ControlPersist 10m
	AddKeysToAgent yes
	IdentityFile ~/.ssh/hust2
	ServerAliveInterval 10
	ServerAliveCountMax 5
```

在服务端执行 jupyter notebook 指令并指定端口为 7190

```bash
jupyter notebook --port 7190
```

![jupyter1]({{site.baseurl}}/assets/img/jupyter1.png)

复制链接到本地浏览器并把端口改为 17190

![jupyter2]({{site.baseurl}}/assets/img/jupyter2.png)

Beng! Here you go. Happy coding.

## 管理以及维护

### 远程添加账户

输入以下命令创建用户

```bash
sudo useradd -s /bin/bash -m -d /home/user_name -G Group user_name
```

`-s: /path/to/shell` 新用户用什么 shell 登陆

`-d:` 指定新用户 home 目录

`-m:` 创建 home 目录

`-G:` 给用户指定群组，如果需要超级管理员权限把 Group 换成`sudo`，如不需要超级用户权限删除`-G Group`。

到此一个用户名为 user_name 的用户就创建好了，可以通过以下命令给用户设置密码：

```bash
sudo passwd user_name
```

如果用户已经存在，想要添加`sudo`权限可以用以下命令

```bash
sudo usermod -aG sudo user_name
```

`-aG:`添加组

### xrdp server config

安装 xrdp

```bash
sudo apt install xrdp
```

安装完成之后在系统中启用开机自动启动

```bash
sudo systemctl enable xrdp
```

然后需要吧 xrdp 用户组添加到组`ssl-cert`

```bash
sudo adduser xrdp ssl-cert
```

接下来为了解决远程连接上之后桌面只有一个背景的 bug 需要在`/etc/xrdp/startwm.sh`中添加一些变量

```bash
#!/bin/sh
# xrdp X session start script (c) 2015, 2017 mirabilos
# published under The MirOS Licence

export DESKTOP_SESSION=ubuntu
export GNOME_SHELL_SESSION_MODE=ubuntu
export XDG_CURRENT_DESKTOP=ubuntu:GNOME

# 原来的一些东西
```

这样 xrdp 远程桌面服务器就配置好了，重启 xrdp 服务

```bash
sudo service xrdp restart
```

最后需要对 xrdp 的端口开放防火墙

```bash
sudo ufw allow 3389 # 对所有ip开放

sudo ufw allow from 192.168.0.1/8 to any port 3389 # 允许一个网段内的ip
```

### Clash for Windows on Linux

这个配置比较简单，直接去[clash for windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)的 GitHub 仓库下载 Linux 版本的压缩包。

```bash
# 解压缩tar.gz格式的文件
tar -xzvf filename.tar.gz

# 然后直接运行解压出来的CFW文件
./cfw
```

#### 配置 Web-UI 以方便的进行远程管理

TBD

### 防止服务器休眠

```bash
# 禁用系统休眠
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target

# 查看状态
sudo systemctl status sleep.target suspend.target hibernate.target hybrid-sleep.target
```
