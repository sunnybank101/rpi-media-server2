# rpi-media-server2

2020 version of our RPI4 Media Server setup

helper files to get the media server up and running properly

# Base Install

Latest Raspbian Image

sudo apt-get update

sudo apt-get dist-upgrade

sudo apt-get upgrade

# RaspAP
https://github.com/billz/raspap-webgui

# JellyFin
https://jellyfin.org/

# FanShim
https://github.com/pimoroni/fanshim-python

# Samba
sudo apt-get install -y samba samba-common<br>
sudo geany /etc/samba/smb.conf    (see the smb.conf file)<br>
sudo smbpasswd -a pi<br>

# Default drive mount setup - NTFS
sudo apt-get install -y ntfs-3g<br>
sudo mkdir /mnt/MEDIA<br>
sudp chmod 777 /mnt/MEDIA<br>

update fstab and add the line below - to get the drive to automount nicely<br>
sudo geany /etc/fstab<br>
LABEL=MEDIA      /mnt/MEDIA ntfs-3g    permissions,defaults,nofail,x-systemd.device-timeout=30        0       2

The main media drive must be labeled "MEDIA" and formatted NTFS<br>
- movies<br>
- music<br>
- pictures<br>
- shared-disk<br>

# Startup control
download these files to /home/pi
- ledoff.py
- ledon.py


