Keyboard Layout
echo keycode 41 = p | loadkeys 
1. One-time: setxkbmap ch
2. SLAX loadkeys ch_DE
3. /etc/conf KEYMAP="sg-latin1.map.gz" or KEYMAP="de_CH-latin1.map.gz"
4. Permanent: sudo nano /etc/X11/xorg.conf
    Option  	"XkbLayout" "ch"
    Option  	"XkbVariant" "de"
    104
5. keys=sg in GRUB
6. Sudo vi /etc/default/keyboard (XLAYOUT ch; XVARIANT de)

Map “section/degree” key to “p”
xmodmap -e "keycode 49 = P"

Autocompletion
Nano ~/.inputrc
"\t": menu-complete
"\e[Z": menu-complete-backward
"\e[1~": beginning-of-line
"\e[4~": end-of-line

Mounting Hard Drive (SDD)
pmount OR mount /dev/sda1 /mnt/sda1
Unmount:
umount /dev/sda1
Mount Windows Drive:
mkdir /mnt/ntfs
mount -t ntfs /dev/sda1 /mnt/ntfs
Auto-Mounted Volumns: /etc/fstab http://www.tuxfiles.org/linuxhelp/fstab.html
Mounting an ISO
dd if=my.iso of=/dev/sdb
http://askubuntu.com/questions/134545/how-to-get-unetbootin-to-recognize-mounted-usb-drive
Fixing a Partition
ntfsfix /dev/sda2
http://itknowledgeexchange.techtarget.com/security-admin/dual-booting-linux-and-windows-7-the-0xc0000225-error/

Free Space
df -h
Partitioning
1. gparted (needs perl)
2. cfdisk /dev/sdb (USB) or cfdisk /dev/sda (SDD)
3. fdisk -l (view existing partitions)

Installing GParted
1. Get perl module from slax site, right click on .sb file and activate
2. Download libsigc from slax site, rightclick and activate
2. Get gtkmm module from slax site, download and activate
3. Download GParted from sourceforge and unpack
3. chmod +x configure then run ./configure
4. 
Formatting:
gparted
mkfs.ext2 /dev/sdb1 (Format USB stick as ext2)

Environment Variables
1. env
2. export

BootLoaders
GRUB
http://old.slax.org/forum.php?action=view&parentID=82779
Download: wget http://ftp.slackware.cz/slackware/slackware-13.37/extra/grub/grub-0.97-i486-9.txz
Unpack and copy into /usr
run grubconfig and choose “simple”
Choose MBR to make GRUB the default boot loader on a drive
menu.1st:
keys=sg (swiss german)

Dual Boot WinXP
http://old.slax.org/forum.php?action=view&parentID=20957

Installing NodeJS (Slax Linux)
http://joyent.com/blog/installing-node-and-npm
1. Install python
1.1. Download node-latest.sb from modules page of slax
1.2. Right click on .sb file and choose “Activate Slax Bundle”
1.3. Check it’s installed with python -V
2. Install Node
2.1. Download wget http://nodejs.org/dist/node-latest.tar.gz
2.2. Right-click and unpack to node-whatever/
2.3. cd node-whatever/ and run make install
2.4 Check NodeJS is installed with node -v
2.3 Check NPM is installed with npm version

Installing Stuff
lzm2dir package.lzm /

SAMBA SMB File Shares
sudo apt-get update
sudo apt-get install samba samba-common-bin
sudo mkdir -m 1777 /data
sudo chown pi:pi /share
sudo nano /etc/samba/smb.conf
[share]
  comment = Data share
  path = /share
  browseable = yes
  read only = no
testparm
sudo service smbd restart

System Information in SysFS
http://landoflinux.com/linux_procfs_sysfs.html 


Auto-Login
sudo leafpad /etc/lightdm/lightdm.conf
sudo leafpad /etc/lxdm/default.conf

// Become Admin and stay Admin...
sudo su

Remap Keyboard Keys
Save the following as ~/.Xmodmap
keycode  33 = degrees section
keycode 49 = p P p P
then run xmodmap ~/.Xmodmap

Power Settings
xset s off
Installing Tarballs
tar -xf file.tar.bz2
cd dir_name
./configure
make
sudo make install
Setting up DEV Environment
sudo apt-get install npm
// Installing Sublime Text (command `subl` to run)
sudo add-apt-repository ppa:webupd8team/sublime-text-2
sudo apt-get update
sudo apt-get install sublime-text
// Installing GIT
sudo apt-get install git

See where “ed” is installed
command -v ed
which ed

FTP 
Install Server
sudo apt-get install filezilla
Install Client
sudo apt-get install vsftpd
Sudo leafpad /etc/fstab and add:
/home/marc/hdd2 /media/marc/System/Marc/Music none bind 0 0

Make <tab> work properly in bash. Add this to ~/.bashrc
# Better tab behaviour
bind TAB:menu-complete

Open Display Settings
lxrandr


# Usability
* `~/.basrc`
* ls should format long and show all: `alias ls='ls -alF'`
* Decent bash completion `. /usr/share/bash-completion/bash_completion`

# Git branch prompt
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```