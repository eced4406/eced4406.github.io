---
layout: default
title: 0x000 - Introduction
parent: Labs
nav_order: 0
has_children: true
has_toc: true
permalink: /labs/0x000-introduction
---
# 0x000 - Introduction

## Set up Raspberry Pi Pico
These instructions have been adapted from the Digikey instructions.[^1]
These instructions are also available in video form.[^2]

### Install Visual Studio Code (vscode)
The installer for vscode can be download from the visual studio website.[^3]

### Install Build Tools
The instructions for installing the build tools vary depending on the operating system of your computer. 
For linux distributions like debian and ubuntu, a simple setup script will install all the necessary tools. 
For macOS, there is a homebrew package to install the required build tools
For Windows, the setup process is a bit more complicated.

#### Linux
Run the following commands to download and execute the pico setup script:

```bash
# download setup script
wget https://raw.githubusercontent.com/raspberrypi/pico-setup/master/pico_setup.sh
# change mode of setup script to be executable
chmod +x pico_setup.sh
# execute the setup script
./pico_setup.sh
# reboot computer
sudo reboot
```

#### macOS
Run the following commands to install homebrew, the `cmake` tool, add the `ArmMbed` homebrew repository, and install the `arm-none-eabi-gcc` toolchain:
```bash
# install homebrew if you do not already have it installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# install the cmake tool
brew install cmake
# add the ArmMbed tap repository
brew tap ArmMbed/homebrew-formulae
# install the arm-none-eabi-gcc toolchain
brew install arm-none-eabi-gcc 
```

#### Windows
There are two methods for installing the build tools on windows:
1. Using `MinGW`
2. Using `Build Tools for Visual Studio` (6GB) and running vscode through the `Developer Command Prompt`

The instructions here have been adapted from the guide written by Shawn Hymel for using MinGW.[^4]

1. Directory Setup.
Create the following folders:
```
C:\VSARM\armcc
C:\VSARM\lib
C:\VSARM\mingw
C:\VSARM\sdk
```
2. Install GNU Arm Embedded Toolchain. 
Download the latest windows installer.[^5]
Run the installer and change the install destination folder to `C:\VSARM\armcc\<version>`. 
Note, the version will be automatically entered when using the `Browse...` function and selecting `C:\VSARM\armcc\`.

3. Install MinGW-w64 GCC Tools.
Download the latest `i686-posix-sjlj` file.[^6]
Decompress the file and move the contents to `C:\VSARM\mingw`.
In the end, the folder `C:\VSARM\mingw\mingw32` should exist.
Open `Command Prompt` and run the following command to create a useful alias:
```bash
echo mingw32-make %* > C:\VSARM\mingw\mingw32\bin\make.bat
```

3. Install CMake.
Download the latest windows installer.[^7]
Run the installer and ensure `Add CMake to the system PATH for all users` is checked in the install options.

4. Install Python.
Download python installer (version 3.9 is recommended).[^8]
Run the installer and ensure `Add Python 3.9 to PATH.` is checked.
At the end of the installation, select the option to disable the `MAX_PATH` length limit.

5. Install git.
Download the latest windows installer.[^9]

6. Update Environment Variables.
Using windows search, search for `env` and click on `Edit the system environment variables`.
Click on `Environment Variables...`
Under the first section (User variables for \<username\>) click `New...` and create the following entry:  
Variable name: `PICO_SDK_PATH`  
Variable value: `C:\VSARM\sdk\pico\pico-sdk`  
Click OK to add the entry.

Under the first section (User variables for \<username\>) click `New...` and create the following entry:  
Variable name: `PICO_TOOLCHAIN_PATH`  
Variable value: `C:\VSARM\armcc\<version>\bin\arm-none-eabi-gcc.exe`  
Click OK to add the entry.


Under the second section (System variables) select `Path` and then `Edit...`
Add/ensure the following entries are listed:
```
C:\Program Files\CMake\bin
C:\Program Files\Git\cmd
C:\VSARM\armcc\<version>\bin
C:\VSARM\mingw\mingw32\bin
```
Click OK on the 3 open windows: Edit environment variable, Environment Variables, and System Properties to save your changes and close the windows.

1. Download Pico SDK and Examples.
Create the following folder: `C:\VSARM\sdk\pico`.
Open Git Bash and run the following commands:
```bash
# add make alias
echo "alias make=mingw32-make.exe" >> ~/.bashrc
source ~/.bashrc
# change directory to the pico folder
cd /c/VSARM/sdk/pico 
# obtain the pico sdk using git
git clone -b master https://github.com/raspberrypi/pico-sdk.git 
# change directory to the just cloned sdk
cd pico-sdk
# update and obtain all the submodules of the sdk 
git submodule update --init 
# change directory back to the main pico folder
cd .. 
# obtain the example pico projects 
git clone -b master https://github.com/raspberrypi/pico-examples.git
```

1. Test Environment.
Open Command Prompt and run the following commands to ensure your environment is set up correctly:
```bash
# try running gcc, should output: "gcc: fatal error: no input files"
gcc
# try running mingw32-make, should output: "mingw32-make: *** No targets specified and no makefile found.  Stop."
mingw32-make
# should output: C:\VSARM\sdk\pico\pico-sdk
echo %PICO_SDK_PATH%
```

### Configure Visual Studio Code (vscode)
Open Visual Studio Code and open the `Extensions` menu (four square icon) on the left. Search for and install `C/C++ Extension Pack`. Also search for and install `CMake Tools`. In the extensions list, click the gear at the bottom right of `CMake Tools` and click `Extension Settings` to configure it. Scroll down to the `Cmake: Generator` setting and enter the following value depending on your operating system:

Linux: `Unix Makefiles`  
macOS: `Unix Makefiles`  
Windows (MinGW): `MinGW Makefiles`

On the bottom bar, click `No active kit` to set the kit, select `GCC <version> arm-none-eabi`. Note, if this kit does not show up, you may need to specify it in the extension settings. If this is the case, click the gear at the bottom left of vscode, click settings and search for kits. Under `Cmake: Additional Kits` enter the following:

```
C:\VSARM\armcc\<version>\bin\arm-none-eabi-gcc\arm-none-eabi-gcc.exe
C:\VSARM\armcc\<version>\bin\arm-none-eabi-gcc\arm-none-eabi-g++.exe
```

Then, click `No active kit` and select `[Scan for kits]`. Select the `GCC <version> arm-none-eabi` kit.


[^1]: [https://www.digikey.ca/en/maker/projects/raspberry-pi-pico-and-rp2040-cc-part-1-blink-and-vs-code/7102fb8bca95452e9df6150f39ae8422](https://www.digikey.ca/en/maker/projects/raspberry-pi-pico-and-rp2040-cc-part-1-blink-and-vs-code/7102fb8bca95452e9df6150f39ae8422)
[^2]: [https://www.youtube.com/watch?v=B5rQSoOmR5w](https://www.youtube.com/watch?v=B5rQSoOmR5w)
[^3]: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
[^4]: [https://shawnhymel.com/2096/how-to-set-up-raspberry-pi-pico-c-c-toolchain-on-windows-with-vs-code/](https://shawnhymel.com/2096/how-to-set-up-raspberry-pi-pico-c-c-toolchain-on-windows-with-vs-code/)
[^5]: [https://developer.arm.com/downloads/-/gnu-rm](https://developer.arm.com/downloads/-/gnu-rm)
[^6]: [https://sourceforge.net/projects/mingw-w64/files/](https://sourceforge.net/projects/mingw-w64/files/)
[^7]: [https://cmake.org/download/](https://cmake.org/download/)
[^8]: [https://www.python.org/downloads/](https://www.python.org/downloads/)
[^9]: [https://git-scm.com/download/win](https://git-scm.com/download/win)
