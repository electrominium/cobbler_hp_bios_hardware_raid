# cobbler_hp_hardware_raid

**Cobbler snippet to create hardware raid configurations on HP Proliant servers in BIOS**

The snippet can be used to create various hardware raid configuartions on **HP Proliant** servers in its BIOS even before the OS is installed.

Before you use this snippet, download the **hp_kickstart_tools.tar.gz** which contains the hpssacli tool _(2.40-13.0)_ to create the raid configurations and host it on your cobbler or web server, from where it can downloaded. You can also create the **hp_kickstart_tools.tar.gz** file by installing the hpssacli rpm on a Centos system and tar up /opt/hp

The snippet does the following:
  1) It downloads the hp_kickstart_tools.tar.gz file and then untars the files
  2) It will check for total number of disks, total number of sata disks and total number of SSD disks, storing the values in respective variables
  3) It will then go ahead delete the existing logical disks to start from a clean slate
  4) The first "if condition" configures SSD disks
  5) The second "if condition" configures any sata disks
  5) Based on the number of disks in a system, we have different raid configurations
