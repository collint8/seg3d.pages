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
these directions: https://pip.pypa.io/en/stable/installing/.  Be sure to use the python included in the Seg3D application.  With OS x versions, it is in `Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/bin`

## Installing numpy, scipy, and other major packages
###
* make sure that pip is installed
* in the terminal:
  * `cd Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/bin`
  * `./python3 -m pip install numpy`
  * make sure that the package is found in `Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python3.4/site-packages`

#### Installing Matlab engine for python in Seg3D
In the terminal:
  * `cd "matlab_root"/extern/engines/python`
  * `Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/bin/python3.4 setup.py build --build-base="builddir" install --prefix="installdir"`
  * make sure that the package (matlab and matlabengineforpython-…) is found in `Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/lib/python3.4/site-packages`

Full instructions are located at http://www.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html
  
# Matlab engine in Seg3D (through Python)

In Seg3D, Matlab code and functions can be run using the matlab
engine for python in the python console or python interface.  To do
so, make sure that the matlab engine is installed (previous
section).  

To run the matlab engine in the python console in Seg3D, the DYLD_LIBRARY_PATH environment variable needs to be set to find python libraries and the matlab engine, as follows

`export DYLD_LIBRARY_PATH="path"/Seg3D2.app/Contents/Frameworks/Python.framework/Versions/Current/lib:"matlab_root"/extern/engines/python/dist/matlab/`

This can be added to the .bashrc file or you could try the /etc/launchd.conf file.

Full documentation found at
http://www.mathworks.com/help/matlab/matlab-engine-for-python.html
