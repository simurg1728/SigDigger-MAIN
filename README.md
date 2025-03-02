# STATUS
The source code can be compiled. And, launch in debug mode. HackRF and RTL-SDR USB is succesfully connected. HOWEVER, there is a head corruption in run-time which leads crash in release mode. I couldn't find the exact cause. I am suspicious of binary incompatibility or a bug related with the use of SoapySDR.

# SigDigger developer friendly Windows Project
This project aims to provide a easy-to-build Qt project on Windows using Qt Creator SUBDIR template. All the projects are compiled from the sigdigger-main.pro project file.
* Third party libraries are mostly taken from Radioconda 2024.05.29. I didn't use Radioconda's path since other libraries such as pthread.h conflicts with MinGW

# Highlights

* QMake files added for sigutils, suscan (suscan-thin-client, suscan.status, suscli are NOT compiled).
* Some source files are renamed in suscan for name related conflict in Windows.
* Windows related modifications are kept minimum in SuWidgets QMake files.
* Windows dependencies, including the binaries, are added in a project named libthirdparty.

# TODO
* Debug the heap corruption on SDR connections.
* Write test for `suscli_devserv_permission_match(const char *expr)` in suscan
* Add unit tests with Google test
* Add other optional dependencies to libthirdparty
* Use the dependency scripts already written

# Build

Download the projects with:
```
git clone --recursive https://github.com/simurg1728/SigDigger-MAIN.git
```
or
```
git clone https://github.com/simurg1728/SigDigger-MAIN.git
git submodule init
git submodule update
```

* MinGW 8.1.0 and Qt  5.15.2 is used with Qt Creator IDE.
* Open sigdigger-main.pro in Qt Creator
* Set shadow build path to "build". Otherwise linking commands in the pro files must be updated.
* Build

Copy followings before launching the application in the Qt Creator
* sndfile.dll to build/SigDigger
* libthirdparty/SoapySDR-win64/lib/SoapySDR/modules0.8 folder to build/SigDigger/debug and build/SigDigger/release (Or set SOAPY_SDR_PLUGIN_PATH environment variable to modules0.8 location)
