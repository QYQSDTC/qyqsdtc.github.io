---
format: post
tag: 
  - Conda
  - M1 Mac
  - Pulsar Software
---



# Installation of Pulsar Softwares on M1 Mac

# Preface and Preparation
由于主流的脉冲星计时软件Tempo2的老旧以及不可移植性，导致想要在最新的M1的Mac电脑上安装很是困难，不过最近我找到了一个workaround：通过Anaconda来配置一个虚拟环境专门用于pulsar softwares的安装和使用。接下来就具体介绍一下如何一步一步配置好这个环境。
# Anaconda or Miniconda
对于conda的选择，我的建议是如果是刚进入编程的新人，那么就选择Anaconda，他会一次性把基本所有常用的包都给你装了（约400个，4GB）。如果是熟悉编程的同学，那么我建议装一个Miniconda就足够了，接下来的包我们按需安装。我选择的是Miniconda，但是里面conda的使用和包的安装这些是共通的。
## Installation of miniconda
首先我们去miniconda的[官网](https://docs.conda.io/en/latest/miniconda.html#:~:text=Miniconda%20is%20a%20free%20minimal,zlib%20and%20a%20few%20others.)选择对应python版本的M1 ARM版本，可以通过终端terminal安装，也可以直接选择pkg下载安装包安装。
![miniconda]({{site.baseurl}}/assets/img/CleanShot%202022-05-17%20at%2011.26.32.png)

## Configure the virtual environment for pulsar softwares
当你装好了miniconda后我们首先得做两件事：
1. 把conda-forge设为首选的channel，conda-forge是一个开源社区，在社区的努力下，维护速度和包的数量要快于和多于官方的channel。通过以下命令把conda-forge加入channel并设为最高优先级：
```bash
conda config --add channels conda-forge # add conda-forge to channels
conda config --set channel_priority strict # make it the highest priority when installing packages
```
2. 在建立虚拟环境的同时启用Rosetta 2转译，理由是PINT，Tempo2等软件在ARM架构下不能达到X86架构下精度，需要用Rosetta 2进行转译，这会导致计算速度极大的降低，但是这是唯一能在M1下安装并使用的方法，希望NANOGrav之后能让PINT适配ARM。
```bash
CONDA_SUBDIR=osx-64 conda create -n psrsoft python   # Create a new environment called psrsoft with intel packages and install python
conda activate psrsoft
python -c "import platform;print(platform.machine())"  # Confirm that the correct values are being used.
conda config --env --set subdir osx-64  # Make sure that conda commands in this environment use intel packages.
```
现在已经配置好了基本的环境，就下来就是安装软件了。
# Install pulsar softwares: Tempo2, psrchive and ENTERPRISE etc.
配置好了环境之后，我们能很简单的用conda来进行常用的脉冲星计时软件的安装了
```bash
conda activate psrsoft # enter psrsoft env
conda install tempo2 psrchive enterprise # one line code can install these pain-in-ass softwares in a snap
```
现在，我们已经装好了这些常用的软件，但是这仅仅只是开始～～～

**注：tempo2的图形界面也就是-glk插件依旧用不了，PINT用TK开发了自己的图形界面，但是我依旧没能成功的运行它。**