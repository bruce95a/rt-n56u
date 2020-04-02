# README #

Welcome to the rt-n56u project

This project aims to improve the rt-n56u and other supported devices on the software part, allowing power user to take full control over their hardware.
This project was created in hope to be useful, but comes without warranty or support. Installing it will probably void your warranty. 
Contributors of this project are not responsible for what happens next.

### How do I get set up? ###

* [Get the tools to build the system](https://bitbucket.org/padavan/rt-n56u/wiki/EN/HowToMakeFirmware) or [Download pre-built system image](https://bitbucket.org/padavan/rt-n56u/downloads)
* Feed the device with the system image file (Follow instructions of updating your current system)
* Perform factory reset
* Open web browser to configure the services. Use the URL or IP on the router's back (newifi's default).

### Contribution guidelines ###

* To be completed

***

### Changes I made ###
* Add Chinese dictionary from: https://github.com/gorden5566/padavan
* Defaults are set to newifi mini's default. Include: URL, IP, etc
* SSID: newifi, newifi_5G; password: newifi.com
* User/password: admin/admin
* Timezone is CST-8
* Country code: CN
* Telnet is off on default

### How to change the default value ###
If you want to change these changes metioned above, use the grep util to find the files, then edit the files.
```shell
grep -r "192.168.1.1" /opt/rt-n56u/trunk/user/www
sudo nano ToEdit.file
```
