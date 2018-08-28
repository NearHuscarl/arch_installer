# Arch Linux Installer

After installing arch for the first time by manually typing every commands
carefully. I realized that those commands will be forgotten soon enough and I
have to do the hard work again when reinstalling arch. Unfortunately I did not
know shell script very well at that time to automate stuff like that

That's why I wrote this script now. This is the wizard that help installing
arch less painful because I do not reinstall my system regularly, I use arch
for that reason as I don't want to install or update my OS again, just use it
and move on with my life, but if I have to someday then it should not be much
of a chore as right now

This script is heavily inspired from [aui][1], many functions and logic is copied
from there, you should use that one instead as this one is customized to my
machine and setup and not guarantee to work on your computer. [aui][1] is more
customizable, well maintained and have more options than my script anyway

## Detail

I do not suggest using this script, just use [aui][1], if you want to use it
however, please test it with a virtualbox first and read the script carefully

* This script will only run on UEFI systems
* At the beginning you have to choose 4 partitions for: root, home, boot and swap
* After that it will format boot partition as fat32, the rest is ext4
* I currently use KDE so the code installing i3 and xfce4 is not tested yet

## Usage

* Download arch ISO file from [here][2]
* Use [rufus][3] (most stable to me) to make a bootable USB using the arch image
* Reboot to the usb
* Get the script and run it

**Note:** You should install in the correct order from 1-n because I did not
check all cases

```bash
wifi-menu # if you use wifi

pacman -Sy git
git clone https://github.com/NearHuscarl/arch_installer
cd arch_installer
./install
```

* After installing the base system choose finish to reboot. A copy of this repo
is placed in the root directory. Go to there and run the other script

```bash
cd arch_installer
./postinstall
```

## Credit

* [aui][1]

## License

[**BSD 3-Clauses**](../master/LICENSE.md)

[1]: https://github.com/helmuthdu/aui
[2]: https://www.archlinux.org/download/
[3]: https://rufus.akeo.ie/
