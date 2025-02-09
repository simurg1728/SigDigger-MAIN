# SigDigger Windows Friendly Development Project
* This project aims to provide a Windows friendly development environment using Qt.
* This repo is not ready yet.

# TODO
* Add Windows Volk binaries in libthirdparty
* Update git attributes for tracking binary files in right way.
* QMake for suscan
* QMake for SuWidgets
* Remove the binaries in the libthirdparty and create a script to download it
* Write test for `suscli_devserv_permission_match(const char *expr)` in suscan
* There is a linking issue with Volk and MinGW

# Changelog
* QMake files added for sigutils
* QMake files added for suscan (only the library not other libraries or executables)
* json-c is added to libthirdparty
* Some source files in the suscan is renamed

# Build

Qt Creator is used for building all projects
* sigdigger-main.pro in Qt Creator
* Set shadows build paths to "build"
* Build!
