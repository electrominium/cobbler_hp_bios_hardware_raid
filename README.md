# cobbler_hp_hardware_raid
Cobbler snippet to create hardware raid configurations on HP Proliant servers in BIOS 

The snippet can be used to create various hardware raid configuartions on HP Proliant servers in its BIOS even before the OS is installed.

Before you use this snippet, download the **hp_kickstart_tools.tar.gz** which contains the hpssacli tool (2.40-13.0) to create the raid configurations and host it on your cobbler or web server, from where it can downloaded. You can also create the **hp_kickstart_tools.tar.gz** file by installing the hpssacli rpm on a Centos system and tar up /opt/hp

The snippet does the following:
  #) It downloads the hp_kickstart_tools.tar.gz file and then untars the files
  #) It will check for total number of disks, total number of sata disks and total number of SSD disks, storing the values in respective variables
  #) It will then go ahead delete the existing logical disks to start from a clean slate
  #) The first "if condition" configures SSD disks
  #) The second "if condition" configures any sata disks
  #) Based on the number of disks in a system, we have different raid configurations
