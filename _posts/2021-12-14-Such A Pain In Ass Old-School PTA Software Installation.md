---
format: post
tags:
  - ENTERPRISE
  - Python
---



# Such A Pain In Ass: Old-School PTA Software Installation

It's such a pain in ass to install old PTA softwares in modern Mac!!

## ENTERPRISE

In order to install the [ENTERPRISE (Enhanced Numerical Toolbox Enabling a Robust PulsaR Inference SuitE)](https://github.com/nanograv/enterprise), I suffered a lot.

### Pre-requisites 

`autoconf`,`automake`,`libstempo`,`suite-sparse`, `scikit-sparse`,`mpi4py`,`acor` 

In order to make ENTERPRISE run, we need to install these packages first.

For `autoconf,automake,suite-sparse and mpi4py` we can simply use MacPorts to handle

```bash
sudo port install autoconf automake suitesparse, mpi4py
```

For `scikit-sparse` we need to use **pip** 

```bash
pip install -U scikit-sparse
```

For `libstempo` follow the instruction on [GitHub](https://github.com/vallis/libstempo#pip-install), but need to download the *install_tempo2.sh* to rather than use `curl` to run this shell script due to the permission problem. Once the shell script is downloaded, **cd** to the dir where the installation script stays, then

```bash
sudo ./install_tempo2.sh /opt/local
```

After installation finished, set up **TEMPO2** env variable in .zshrc

```bash
export TEMPO2="/opt/local/share/tempo2"
```

For `acor` we need to clone irs repo on [GitHub](https://github.com/dfm/acor) and install manually by running

```bash
cd acor
python setup.py install
```

Now, we are ready to install ENTERPRISE and its extensions, just follow the intro on GitHub and it will go smoothly. 