# Introduction

This is a modified version of the source code present in [Axiak's pyre2](https://github.com/axiak/pyre2).  This can be used to get a compiled version of a python file which uses Google's RE2 library for regex parsing. The DLL which uses Google RE2 needs to be compiled separately. Compilation is done using Visual Studio 2013 on a Windows machine.

## Building PyRE2 

- Download the [pyre2 source](https://github.com/axiak/pyre2)
- Modify include_dirs array in setup.py, and add:
  * the directory where re2.dll is present
  * the directory where the source code for re2 is present
- Run command `python setup.py build`
 This will create a dist folder with the executable re2-0.2.23.win-amd64-py2.7.exe

## Installing PyRE2

- Instead of `python setup.py build`, if `python setup.py install` command is executed, pyre2 will be installed.
- If build has been performed, navigate to the dist folder, and execute re2-0.2.23.win-amd64-py2.7.exe. This will open a user-friendly installer which will install pyre2 to the site-packages folder of your default python distribution.

## Getting PyRE2 binaries for future use

- If build has been performed, there will be a new build folder, which will have the re2.pyd file for different windows architectures.
- If PyRE2 was directly installed, navigate to the site-packages folder of the python distribution where PyRE2 is installed, and copy the following 3 files:
  * re2.pyd
  * re2-0.2.23-py2.7.egg-info
  * re2.dll
  These 3 files can together be copied to the site-packages folder of any python distribution, and the re2 module can then be imported into that python distribution.

## Known Issues

- If build fails because the vcvarsall.bat file for Visual Studio 2008 is used instead of Visual Studio 2013, then edit the environment variable VS90COMNTOOLS, setting it to the same value as that of VS130COMNTOOLS. Then, reopen cmd and run the build command again.