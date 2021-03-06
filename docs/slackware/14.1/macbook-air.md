# slackware 14.1 macbook air 

## References
* http://www.slackware.com/getslack/
* http://ftp.gtlib.gatech.edu/pub/slackware/
* http://slackbook.org/beta/
* http://docs.slackware.com/
* http://docs.slackware.com/slackware:install
* http://www.linuxquestions.org/questions/slackware-14/installing-slackware-on-a-macbook-pro-925730/
* http://www.syslinux.org/wiki/index.php?title=Doc/isolinux#HYBRID_CD-ROM.2FHARD_DISK_MODE
* https://support.apple.com/en-us/HT204417

### Requirements
* 4GB USB storage device

##### Download a copy of slackware-14.1-install-dvd.iso
* http://mirrors.slackware.com/

*[Starting with the 14.1 release, Slackware ISO images (both the ones available online as well as the discs sent out from the Slackware store) have been processed using isohybrid. This allows them to be written to a USB stick, which can then be booted and used as the install source.](http://docs.slackware.com/slackware:install)*

##### Open the OSX Terminal
* /Applications/Utilities/Terminal

##### Get the current list of disks
```
diskutil list
```

##### Insert the 4GB USB stick

##### Get the current list of disks again 
*Figure out which device node has been assigned to the USB storage device (e.g. /dev/disk2)*
```
diskutil list
```

##### Unmount the USB device (replace N with the disk number from the last command)
```
diskutil unmountDisk /dev/diskN
```

##### Copy the contents of the disk image to the USB device. This will erase any contents of the USB device.
*Using /dev/rdisk instead of /dev/disk may be faster*
```
sudo dd if=/path/to/downloaded.img.dmg of=/dev/rdiskN bs=1m
```
*This takes about 10 minutes with a USB 2.0 device*
```c
/*
2370+0 records in
2370+0 records out
2485125120 bytes transferred in 349.217615 secs (7116265 bytes/sec)
*/
```
##### Get the current list of disks again 
*Note that the partition scheme should have changed.*
```
diskutil list
```
```c
/*
/dev/disk2
   #:           TYPE NAME         SIZE       IDENTIFIER
   0                             *4.0 GB     disk2
*/
```

##### Eject the disk
```
diskutil eject /dev/diskN
```
```c
// Disk /dev/disk2 ejected
```

##### Restart the machine
* Apple > Restart

##### Temporarily change your startup disk with Startup Manager
* Press and hold the Alt/Option key after the startup sound plays and before the Apple icon appears

##### Choose the USB device as the startup device
* The device will probably be labeled Windows



