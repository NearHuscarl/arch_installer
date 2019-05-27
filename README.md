# Arch Linux Installer

**WARNING** DO NOT USE THIS SCRIPT AS IT'S TAILORED FOR MY PERSONAL USECASE 

## Troubleshoot

### System Info

- OS: Manjaro Linux x86_64 
- Host: HP Pavilion Notebook 
- Kernel: 4.19.45-1-MANJARO 
- Uptime: 1 hour, 22 mins 
- Packages: 1126 (pacman) 
- Shell: bash 5.0.7 
- Resolution: 1366x768 
- DE: Xfce 
- WM: Xfwm4 
- WM Theme: Matcha-dark-azul 
- Theme: Matcha-dark-azul [GTK2], Adwaita [GTK3] 
- Icons: Papirus-Dark-Maia [GTK2], Adwaita [GTK3] 
- Terminal: xfce4-terminal 
- Terminal Font: Monospace 12 
- CPU: Intel i7-6500U (4) @ 3.100GHz 
- GPU: NVIDIA GeForce 940MX 
- GPU: Intel Skylake GT2 [HD Graphics 520] 

### Fix audio crackling on HP machines
- https://wiki.archlinux.org/index.php/ASUS_Zenbook_UX430/UX530#Headphones_audio_is_too_low
- https://bugs.launchpad.net/ubuntu/+source/alsa-driver/+bug/1648183

## Detail

-  This script will only run on UEFI systems
-  At the beginning you have to choose 4 partitions for: root, home, boot and swap
-  After that it will format boot partition as fat32, the rest is ext4
-  I currently use KDE so the code installing i3 and xfce4 is not tested yet

## Usage

-  Download arch ISO file from [here][2]
-  Use [rufus][3] (most stable to me) to make a bootable USB using the arch image
-  Reboot to the usb
-  Get the script and run it

**Note:** You should install in the correct order from 1-n because I did not
check all cases

```bash
wifi-menu # if you use wifi

pacman -Sy git
git clone https://github.com/NearHuscarl/arch_installer
cd arch_installer
./install
```

Without git

```bash
curl -L https://github.com/NearHuscarl/arch_installer/archive/master.tar.gz > arch_installer.tar.gz
tar -xvf arch_installer.tar.gz
cd arch_installer-master
./install
```

-  After installing the base system choose finish to reboot. A copy of this repo
   is placed in the root directory. Go to there and run the other script

```bash
./postinstall
```

## Credit

-  [aui][1]

## License

[**BSD 3-Clauses**](../master/LICENSE.md)

[1]: https://github.com/helmuthdu/aui
[2]: https://www.archlinux.org/download/
[3]: https://rufus.akeo.ie/
