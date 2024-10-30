# Material for Physiopy's code demo for the ReproNim webinar "Physiopy Community: working towards accessible and reproducible data usage in neuroimaging studies"

In this repository you can find the data and the code to follow Physiopy's code demo, part of the ReproNim monthly webinar (November 1st 2024) _Physiopy Community: working towards accessible and reproducible data usage in neuroimaging studies_

# Laptop setup

To follow this tutorial, you will need a laptop, requiring a little bit of setup beforehand.

## 0. Prerequisites
You will need a laptop with python installed, as well as _pip_. Python version should be 3.7 or above.
You also need to download the files in this repository, either [zipped in a package](https://github.com/me-pic/repronim2024physiopy/archive/refs/heads/master.zip) or by locally cloning the repository (see below).

``` shell
git clone git@github.com:me-pic/repronim2024physiopy.git
```

## 1. Optional - Set up a virtual environment
The best way to ensure the software functioning without changing anything in your system is using a virtual environment.
For that, first install _virtualenv_:

``` shell
pip install -U virtualenv
```
(Note you might need to use _pip3_ instead of _pip_, depending on your OS and setup, to work with python 3)

Then, create and activate the virtual environment - in this case I called it _env_, but you can use a different name:

``` shell
virtualenv env
source env/bin/activate
``` 

Note that the first command above will create a folder where you called it from, and the second command assumes this is the case - if you want you can specify a different path though.

Once you activated the virtual environment, you can proceed with package installation

## 2. Package installation

You will need to install a few python packages. First and foremost, [_wxPython_](). Its installation depends on the OS you are using.
While you can find [detailed instructions here](https://wxpython.org/pages/downloads/), following is the summary.

### Install _wxPython_ on Windows and macOS
``` shell
pip install -U wxPython
```
(Note you might need to use _pip3_ instead of _pip_, depending on your OS and setup, to work with python 3)

### Install _wxPython_ on Linux
Check [this folder](https://extras.wxpython.org/wxPython4/extras/linux/) for the right python package, depending on the version of GTK you are using, as well as your OS, then using the link to the right folder, install _wxPython_ version _4.2.0_, if possible.
In this example, I will assume we're working with GTK3 on Ubuntu 20.04:
``` shell
pip install -U \
    -f https://extras.wxpython.org/wxPython4/extras/linux/gtk3/ubuntu-20.04 \
    wxPython==4.2.0
```
(Note you might need to use _pip3_ instead of _pip_, depending on your OS and setup, to work with python 3)

### Install all other packages
You also need to install _peakdet_ and _phys2denoise_. Optionally, you can also install _ipython_, a nice CLI environment to work with python.

The fastest option is to use the _requirements.txt_ file in this repository:
``` shell
cd repronim2024physiopy
pip install -U -r requirements.txt
```
(Note you might need to use _pip3_ instead of _pip_, depending on your OS and setup, to work with python 3)

Alternatively, you can install directly what you need. Please ensure to install matplotlib version 3.6.3 or below, otherwise you will incur into a deprecation error:
``` shell
pip install -U phys2bids peakdet phys2denoise matplotlib==3.6.3 ipython
```
(Note you might need to use _pip3_ instead of _pip_, depending on your OS and setup, to work with python 3)

## 3. Check the installation
Within the virtual environment, you can either call _pip_ to list your packages (`pip list` or `pip3 list`), or open ipython and import _peakdet_ and _phys2denoise_
```python
import phys2bids
import peakdet
import phys2denoise
```

If you have no issues doing that, you're all good to go!

**Note that peakdet's GUI might not work in GUI-like environments like Jupyter notebooks or Spyder.**

## 4. Check the data

We are providing some data in this repository in the `data` folder. This folder includes `multifreq.acq` file containing raw physiological data, and `heur_tutorial.py`file that would be use for the `phys2bids` part of the tutorial. 

If you have your own data, feel free to _also_ bring it with you!
