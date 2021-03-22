# Bulbasaur home server 

This repo contains information about the setup of my home server called Bulbasaur.

## Perfect media server

Following the instructions in [this "Perfect Media Server" guide](https://perfectmediaserver.com/), I installed Ubuntu Destop on an old PC, pooled multiple hard disk drives into one mount point using mergerfs and exposed it to my local network using Samba. The system is now running 24/7 as a NAS server.

## Backing up phone with Syncthing

I use Syncthing to backup data on my phone. 

Syncthing has an Android app which I've downloaded and configured to send data from my phone's camera, downloads, screenshots and messsenging app's media directories when it's on my home WiFi *and* is charging. This means the data sync will happen once a day, usually overnight. 

Syncthing on the server is running as a Docker container and configured to sync files in my mergerfs mountpoint, under ``/mnt/storage/Devices/Phone/...``. I've also configured it with Simple File Versioning, keeping 1 copy. This means that when the phone deletes files, the server would create a previous version of the file before deleting. This is useful as I can delete files on my phone to save memory and still have a copy in the server.

Additionally, because the purpose is for backup, the phone's data is configured to "Send Only", and the server is setup to "Recieve Only" (as opposed to "Send and Receive" if the device's files were truely sync'ed up). This ensures data only travels in one direction.


## Dump of notes

https://ubuntu.com/tutorials/install-and-configure-samba#4-setting-up-user-accounts-and-connecting-to-share

Permission issue with Samba: https://unix.stackexchange.com/questions/206309/how-to-create-a-samba-share-that-is-writable-from-windows-without-777-permission

New hard disc drive burn-in script: https://github.com/Spearfoot/disk-burnin-and-testing

TMUX cheatsheet: https://gist.github.com/MohamedAlaa/2961058

Installing Syncthing bare metal on Ubuntu following instructions here https://syncthing.net/downloads/ and https://wiki.learnlinux.tv/index.php/Syncing_your_Files_Across_ALL_your_Computers_via_Syncthing#Add_systemd_unit and https://forum.manjaro.org/t/syncthing-systemd-service-will-not-start/54607/4



