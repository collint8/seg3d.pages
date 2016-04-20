---
title: Python Packages and Matlab
category: info
tags: python
---

# Installing packages
* If there is an installation of the packages with other python builds on the machine, the system path can be used to use those packages.  

There are many ways to install packages in python. pip is an easy way that is usually included with python.

## Installing pip
If pip is not installed for the Seg3D installation of python, follow
these directions: https://pip.pypa.io/en/stable/installing/.  Be sure to use the python in `"seg3d_root"/bin/Externals/Install/Python_external/bin/`

## Installing numpy, scipy, and other major packages
* make sure that pip is installed
* in the terminal:
  * `cd "seg3d_root"/bin/Externals/Install/Python_external/bin/`
  * `./python3 -m pip install numpy`

### Installing Matlab engine for python in Seg3D
In the terminal:
  * `cd "matlab_root"/extern/engines/python`
  * `"seg3d_root"/bin/Externals/Install/Python_external/bin/python3.4 setup.py build --build-base="builddir" install --prefix="installdir"`

Full instructions are located at http://www.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html
  
# Matlab engine in Seg3D (through Python)

In Seg3D, Matlab code and functions can be run using the matlab
engine for python in the python console or python interface.  To do
so, make sure that the matlab engine is installed (previous
section). Full documentation found at
http://www.mathworks.com/help/matlab/matlab-engine-for-python.html
