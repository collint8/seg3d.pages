---
title: Build
category: info
tags: build
---

Table of Contents
=================

* [Installing Seg3D from source](#installing-seg3d-from-source)
  * [Compiler Requirements](#compiler-requirements)
    * [Windows](#windows)
    * [Mac OS X](#mac-os-x)
    * [Linux](#linux)
  * [Dependencies](#dependencies)
    * [Qt](#qt)
      * [Seg3D 2.4 And Newer](#seg3d-24-and-newer)
        * [Mac OS X](#mac-os-x-2)
        * [Linux](#linux-2)
      * [Seg3D 2.0 to 2.3](#seg3d-20-to-23)
        * [Windows](#windows)
        * [Mac OS X](#mac-os-x-1)
        * [Linux](#linux-1)
  * [Compiling Seg3D](#compiling-seg3d)
    * [Optional Image Registration Tools](#optional-image-registration-tools)
* [Seg3D Data](#seg3d-data)
* [Seg3D Support](#seg3d-support)

<!-- Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc) -->

# Installing Seg3D from source

## Compiler Requirements

**At least C++11 64-bit compiler support is required.**

### Windows

The current source code must be compiled with the 64-bit version of Visual Studio 2013.
Visual Studio 2015 support is coming soon.
The code has not been tested under Cygwin or MinGW compilers.

### Mac OS X

The source code base was built with Xcode 5-7 as well as GNU Make and works for both environments on OS X 10.8+.

### Linux

The code base has been tested for use with GCC, and this is the recommended compiler for
linux. **Compiler must support C++11.**

## Dependencies

### Qt

#### Seg3D 2.4 And Newer

Before building Seg3D, please make sure that **Qt 5.5** has been installed on your system.

##### Mac OS X

Qt binaries are available on the Qt website or can be built from source code.
Clang with C++11 support is required.

##### Linux

Qt 5 static libraries are **NOT** supported. If building from source, ensure that the shared library build is enabled.

#### Seg3D 2.0 to 2.3

Before building Seg3D, please make sure that **Qt 4.7-4.8** has been installed on your system.

##### Windows

A Visual Studio binary build is available.
To our knowledge the Windows Visual Studio development libraries are only available in a 32-bit version.
A 64-bit version can be built from the source code download, configuring it as described on the Qt webpage.

##### Mac OS X

Qt binaries are available on the Qt website or can be built from source code.
Clang with C++11 support is required.

##### Linux

Qt is available from most package managers. Look for Qt 4.7-4.8.

### CMake

[CMake](https://cmake.org/) versions 2.8 - 3.4 are supported.


## Compiling Seg3D

Once you have obtained a compatible compiler and installed Qt on your system, you need to 
download and install CMake (http://www.cmake.org) to actually build the software.
CMake is a platform independent configuring system that is used for generating Makefiles,
Visual Studio project files, or Xcode project files.
Once CMake has been installed, run CMake from your build (bin) directory and give a path to the CMake Superbuild directory containing the master CMakeLists.txt file.
For example, on the command line:

```
cd bin
cmake ../Superbuild
```

The console version ``ccmake``, or GUI version can also be used.
You may be prompted to specify your location of the Qt installation.
If you installed Qt in the default location, it should find Qt automatically.
After configuration is done, generate the make files or project files for your favorite
development environment and build.

Following the previous example, the Seg3D application will be built in bin/Seg3D.

A bash build script (build.sh) is also available for Linux and Mac OS X to simplify the process.
Usage information is available using the ***--help*** flag:

```
./build.sh --help
```

### Optional Image Registration Tools

To build the optional [python-based image registrations tools]({{ site.github.url }}/ir-tools.html), the CMake option **BUILD_MOSAIC_TOOLS** must be turned on, either on the command line, or in the console or GUI interfaces.
On the command line:

```
cd bin
cmake -DBUILD_MOSAIC_TOOLS:BOOL=ON ../Superbuild
```

# Seg3D Data

Seg3D sample data (also used in the tutorial) is available [here](https://github.com/CIBC-Internal/Seg3DData/releases).

# Seg3D Support

For questions and issues regarding building the software from source, 
please email our support list: seg3d@sci.utah.edu
