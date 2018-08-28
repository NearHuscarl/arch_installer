## Minimum commands to install arch

Assuming:
root partition: /dev/sda1
swap partition: /dev/sda2
boot partition: /dev/sda3

```
ping google.com
lsblk
cfdisk # gpt

mkfs.ext4 /dev/sda1
mkfs.ext4 /dev/sda2

mkswap /dev/sda2
swapon /dev/sda2

mount /dev/sda1 /mnt
mount /dev/sda3 /mnt/boot
pacstrap /mnt base base-devel

genfstab /mnt >> /mnt/etc/fstab

#### ARCH-CHROOT
arch-chroot /mnt

nano /etc/locale.gen # uncomment en_US.UTF-8 UTF-8
locale-gen
# in /etc/locale.conf type LANG=en_US.UTF-8
ln -sf /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime
hwclock --systohc --utc # or --localtime

passwd
echo "$HOSTNAME" >> /etc/hostname

systemctl enable dhcpcd

pacman -S grub os-prober
grub-install
grub-mkconfig -o /boot/grub/grub.cfg

#### -----------

exit
umount /mnt
reboot
```
