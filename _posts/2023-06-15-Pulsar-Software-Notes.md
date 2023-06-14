---
format: post
title: How to make tempo2 work on M series Mac
date: 2023/06/15
tags:
  - pulsar
  - software
  - arm Mac
---
# Tempo2 Installlation Notes
Other pulsar softwares, e.g., *psrchive*, *PINT*, *ENTERPRISE*, etc., can be easily installed and work perfectly using *conda*, but not *Tempo2*. To make *Tempo2* work properly on **M** series Mac, one needs to suffer.
**NOTE: if you are not an expert of Linux/Unix, find an expert.**

## XWINDOW
The first thing to do is to install *xwindow* services. On Mac, you can either install *xwindow*  or *X11* by *Homebrew* by typing `brew install xquartz` or go to [XQuartz](https://www.xquartz.org/) to download the installer.

## PGPLOT
After installing *xwindow* manage system on Mac, we need to configure *PGPLOT* and install it for *Tempo2*. To have *PGPLOT* installed, you might need to install *gcc, libpng, automake, cmake, autoconf, libtool, etc.* first.
Next, get *PGPLOT* using commands below:

```zsh
wget -cNS http://mingus.as.arizona.edu/~bjw/software/pgplot_macosx_conf.tar # get pgplot
tar -xvf pgplot_macosx_conf.tar # untar it
```

After *untar* it, put *sys_macosx* under *pgplot/*, and make a new dir called *pgplot_build*, then *cd* to it and run `../pgplot/makemake ../pgplot macosx gfortran_gcc_64` this will generate a *makefile* in *pgplot_build* folder. Next, we need to edit this *makefile*, change the line `pndriv.o : ./png.h ./pngconf.h ./zlib.h ./zconf.h` to `pndriv.o : /opt/homebrew/Cellar/libpng/1.6.37/include/png.h /opt/homebrew/Cellar/libpng/1.6.37/include/pngconf.h /opt/homebrew/Cellar/zlib/1.2.12/include/zlib.h /opt/homebrew/Cellar/zlib/1.2.12/include/zconf.h` and edit *pngdrive.c* changing `setjmp(png_ptr->jmpbuf)` to `setjmp(png_jmpbuf(png_ptr))`. Now, just need to run `make` and `make libcpgplot.c`. 
After *make*, we need to export this directory to the environment so that *Tempo2* can find *PGPLOT*, `export PGPLOT_DIR=/path/to/pgplot_build`
Enjoy!

## Tempo2
After the installation of *PGPLOT*, we can start installing *Tempo2*. You can download *Tempo2* from [here](https://bitbucket.org/psrsoft/tempo2/src/master/). Then run the commands below:

```zsh
./configure F77=gfortran --prefix=/path/to/tempo2 --disable-local # the prefix is where the executables of tempo2 are installed, the reason for --disable-local is the default local directories are:/usr/local and /opt/local and the MacPort install everything under /opt/local, while Homebrew install under /opt/homebrew, we don't want to mix the things installed with Homebrew and MacPort, therefor --disable-local

make -j 8 && make install && make plugins -j 8 && make plugins-install # -j 8 uses 8 cores to speed up the process.
```

After the *make*, export the *TEMPO2* variable to your environment, so that it can find the plugins.
```zsh
export TEMPO2=/path/to/T2runtime # it usually  stays in the downloaded tempo2 src folder
```

Now, you can use tempo2 on a arm chip Mac, enjoy!