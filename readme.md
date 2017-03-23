# KiCad-Winbuilder
KiCad-Winbuilder provides the means to build up-to-date KiCad binaries.

## Usage
Using KiCad-Winbuilder is pretty straight forward:
1. Download and install [CMake](https://cmake.org/ "CMake Homepage")
2. `git clone` this repository to a location on your machine
3. Run `make_all.bat` from the freshly cloned git repository

KiCad-Winbuilder may utilize up to 10 Gb while downloading and building the dependencies. Make sure you have enough remaining space on your hard drive.
Depending on your hardware, the first build can take several hours to finish. Following builds will be much quicker though.

## Issues (and workarounds)

MSYS2 issue with Windows 10 TH2, doesn't allow proper fork behaviour.
Newly released version of MSYS2 contains a fix.  However must be manually updated at this time (20160103).

EDIT: This might now be fixed https://lists.launchpad.net/kicad-developers/msg22944.html (20160208).

Procedure:

1. Launch msy2_shell.bat
2. run command 'update-core'
3. exit shell, now the rest of the Winbuilder process will work (although the pacman_initial log file should be removed to re-run the pacman updates)


Windows username has space in it, which will cause issues with build process (related to windres.exe not accepting spaces)

Procedure:

1. Launch msy2_shell.bat
2. run command '/usr/bin/mkpasswd > /etc/passwd'
3. exit msy2_shell.bat
4. open /etc/passwd in text editor and remove spaces from the username and the home directory locations (columns 1 and 5 from memory.. but it should be obvious)
5. save file and close
6. rename user home directory to remove space character
