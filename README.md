# ArchLinux helper
> Some tips and tricks while installing ArchLinux.

## 1 . Partitioning disks
> ### cfdisk
> cfdisk is a neat graphical tool for partitioning your disk.<br>
> The way I partition my disk is that I create 3 different types of partitions.<br>
> * 2.5MiB - (partition for grub)
> * 1GiB - (Swap partition)
> * [Rest of the disk] - (System, boot)

## 2 . Enabling types
> ### parted
> parted is used to enable the different types of the partitions.<br>
> First, I run:
	parted /dev/sdx
> Then:<br>
>
	set 1 bios_grub on
>
	set 3 boot on

> This will make it so that the 2.5MiB partition is used for grub and the remaining is used for boot (except for the swap partition).

## 3. Enabling swap
> ### mkswap, swapon
> Next, I enable swap using these commands:
>
	mkswap /dev/sdx2
>	
	swapon /dev/sdx2

## ---------------------------------------

## Internet connection
> If you use ethernet connection, run this command to establish the connection:
>
	systemctl stop dhcpcd@enp0s25.service
	dhcpcd

## Playing games
> If you play games, there is a package you should install that is pretty
> essential for gaming. (graphics)

        pacman -S xorg-xrandr
