# Bulbasaur home server 

This repo contains information about the setup of my home server called Bulbasaur.

## Perfect media server

Following the instructions in the ["Perfect Media Server"](https://perfectmediaserver.com/) website, I installed Ubuntu Destop on an old PC, pooled multiple hard disk drives into one mount point using mergerfs and exposed it to my local network using Samba. The system is now running 24/7 as a NAS server.

## Backing up phone with Syncthing

[Syncthing](https://syncthing.net/) is used to backup data on my phone. [This video](https://www.youtube.com/watch?v=O5O4ajGWZz8) and [this video](https://www.youtube.com/watch?v=J1bCWv14zYg) are useful tutorials for setting it up bare metal. See my ``README.md`` in ``./syncthing`` for more info on how I run it in a docker container.

Syncthing has an Android app which I've downloaded and configured to send data from my phone's camera, downloads, screenshots and messsenging app's media directories when it's on my home WiFi *and* is charging. This means the data sync will happen once a day, usually overnight. 

Syncthing on the server is running as a Docker container and configured to sync the files from my phone to my mergerfs mount point, specifically under ``/mnt/storage/Devices/Phone/...``. I've also configured it with Simple File Versioning, keeping 1 previous version of the file if it is deleted or modified. This means that I can delete files on my phone and the server would still have a copy of the file. This is useful to save some storage space on your phone..

Additionally, because the purpose is for backup, the phone's data is configured to "Send Only", and the server is setup to "Recieve Only" (as opposed to "Send and Receive" if the device's files were truely sync'ed up). This ensures data only travels in one direction.

## Pihole with Unbound DNS

The server is also running Pihole with Unbound DNS in a docker container. 

See the ``README.md`` in ``./pihole-unbound`` for more info. 
