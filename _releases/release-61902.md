---
layout: releases
version: 6.19/02
release_date: 2020-06-26
state:

toc: true
toc_sticky: true
sidebar:
  nav: "releases"
---


## Release Notes

The release notes for this release can be found [here](https://root.cern/doc/v619/release-notes.html#release-6.1902).

## Source distribution

| Platform       | Files | Size |
|-----------|-------|-----|
| source | [root_v6.19.02.source.tar.gz](https://root.cern/download/root_v6.19.02.source.tar.gz) | 160M |


## Binary distributions

| Platform       | Files | Size |
|-----------|-------|-----|
| CentOS 7 | [root_v6.19.02.Linux-centos7-x86_64-gcc4.8.tar.gz](https://root.cern/download/root_v6.19.02.Linux-centos7-x86_64-gcc4.8.tar.gz) | 186M |
| Fedora 29 | [root_v6.19.02.Linux-fedora29-x86_64-gcc8.3.tar.gz](https://root.cern/download/root_v6.19.02.Linux-fedora29-x86_64-gcc8.3.tar.gz) | 221M |
| Fedora 30 | [root_v6.19.02.Linux-fedora30-x86_64-gcc9.2.tar.gz](https://root.cern/download/root_v6.19.02.Linux-fedora30-x86_64-gcc9.2.tar.gz) | 225M |
| Ubuntu 14 | [root_v6.19.02.Linux-ubuntu14-x86_64-gcc4.8.tar.gz](https://root.cern/download/root_v6.19.02.Linux-ubuntu14-x86_64-gcc4.8.tar.gz) | 192M |
| Ubuntu 16 | [root_v6.19.02.Linux-ubuntu16-x86_64-gcc5.4.tar.gz](https://root.cern/download/root_v6.19.02.Linux-ubuntu16-x86_64-gcc5.4.tar.gz) | 200M |
| Ubuntu 18 | [root_v6.19.02.Linux-ubuntu18-x86_64-gcc7.4.tar.gz](https://root.cern/download/root_v6.19.02.Linux-ubuntu18-x86_64-gcc7.4.tar.gz) | 219M |
| Ubuntu 19 | [root_v6.19.02.Linux-ubuntu19-x86_64-gcc8.3.tar.gz](https://root.cern/download/root_v6.19.02.Linux-ubuntu19-x86_64-gcc8.3.tar.gz) | 219M |
| macOS 10.13 Xcode 10 | [root_v6.19.02.macosx64-10.13-clang100.pkg](https://root.cern/download/root_v6.19.02.macosx64-10.13-clang100.pkg) | 133M |
| macOS 10.13 Xcode 10 | [root_v6.19.02.macosx64-10.13-clang100.tar.gz](https://root.cern/download/root_v6.19.02.macosx64-10.13-clang100.tar.gz) | 133M |
| macOS 10.14 Xcode 11 | [root_v6.19.02.macosx64-10.14-clang110.pkg](https://root.cern/download/root_v6.19.02.macosx64-10.14-clang110.pkg) | 135M |
| macOS 10.14 Xcode 11 | [root_v6.19.02.macosx64-10.14-clang110.tar.gz](https://root.cern/download/root_v6.19.02.macosx64-10.14-clang110.tar.gz) | 134M |
| macOS 10.15 Xcode 11 | [root_v6.19.02.macosx64-10.15-clang110.pkg](https://root.cern/download/root_v6.19.02.macosx64-10.15-clang110.pkg) | 135M |
| macOS 10.15 Xcode 11 | [root_v6.19.02.macosx64-10.15-clang110.tar.gz](https://root.cern/download/root_v6.19.02.macosx64-10.15-clang110.tar.gz) | 134M |
| **preview** Windows Visual Studio 2019 (debug) | [root_v6.19.02.win32.vc16.debug.exe](https://root.cern/download/root_v6.19.02.win32.vc16.debug.exe) | 155M |
| **preview** Windows Visual Studio 2019 (debug) | [root_v6.19.02.win32.vc16.debug.zip](https://root.cern/download/root_v6.19.02.win32.vc16.debug.zip) | 227M |
| **preview** Windows Visual Studio 2019 | [root_v6.19.02.win32.vc16.exe](https://root.cern/download/root_v6.19.02.win32.vc16.exe) |  85M |
| **preview** Windows Visual Studio 2019 | [root_v6.19.02.win32.vc16.zip](https://root.cern/download/root_v6.19.02.win32.vc16.zip) | 115M |

## Installations in CVMFS

Standalone installations with minimal external dependencies are available at:
~~~
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-centos7-gcc48-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-fedora29-gcc83-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-fedora30-gcc92-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-mac1013-clang100-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-mac1014-clang110-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-mac1015-clang110-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-ubuntu14-gcc48-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-ubuntu16-gcc54-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-ubuntu18-gcc74-opt
/cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-ubuntu19-gcc83-opt
~~~


## Example for setting up ROOT from CVMFS

~~~
. /cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.19.02/x86_64-centos7-gcc48-opt/bin/thisroot.sh
~~~

## Git

The entire ROOT source can be obtained from our public Git repository:

~~~
git clone https://github.com/root-project/root.git
~~~
The release specific tag can be obtained using:
~~~
cd root
git checkout -b v6-19-02 v6-19-02
~~~


## Windows

Windows 10/7/... are supported. We offer two packaging types:

 * **exe**: a regular Windows installer package also setting up the required environment variables. With uninstall via "Control Panel" / "Add or Remove Programs". Simply download and start. You can double-click ROOT to run it; ROOT files get registered with Windows.
 * **tar**: unpack e.g. with [7zip](https://www.7-zip.org). Start ROOT in a Microsoft Visual Studio Prompt (in Start / Programs / Microsoft Visual Studio / Tools). If you installed ROOT to C:\root then call C:\root\bin\thisroot.bat before using ROOT to set up required environment variables.

### Important installation notes

 * You must download the binary built with the exact same version of Visual Studio than the one installed on your system.
 * Do not untar in a directory with a name containing blank characters.
 * Take the release version if performance matters.
 * If you want to debug your code you need the ROOT debug build (you cannot mix release / debug builds due to a Microsoft restriction).