# README #

This project aims to change the default values on the rt-n56u project.

### How do I get set up? ###

* [Get the source code](https://bitbucket.org/padavan/rt-n56u)
* Follow the instructions below to change the default values.


***

### How to change the default value ###
If you want to change these changes metioned above, use the grep util to find the files, then edit the files.

```shell
grep -r "192.168.1.1" /opt/rt-n56u/trunk/user/www
sudo nano ToEdit.file
```

***

### Changes default lan IP ###
Change the lan IP in these files:
* /opt/rt-n56u/trunk/user/www/dict/EN.footer
* /opt/rt-n56u/trunk/user/www/dict/*.dict
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/Advanced_APLAN_Content.asp
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/Advanced_LAN_Content.asp
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/Advanced_SettingBackup_Content.asp
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/Advanced_System_Content.asp
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/general.js
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/Restarting.asp

### Changes default lan URL ###
Change "my.router" to something else.
* /opt/rt-n56u/trunk/user/httpd/https-cert.sh
* /opt/rt-n56u/trunk/user/libs/libssl/openssl.cnf
* /opt/rt-n56u/trunk/user/rc/net_wan.c

### Changes default SSID username password timezone etc. ###
* /opt/rt-n56u/trunk/user/shared/defaults.h
Note: When changing SSID, consider to change Advanced_WMode_Content.asp Advanced_WMode2g_Content.asp as well.

### Changes default state ###
Change the values in this file: /opt/rt-n56u/trunk/user/shared/defaults.c
For example
* disable telnet { "telnetd", "0" }
* enable ssh { "sshd_enable", "1" }

### Enable UTF-8 SSID ###
* /opt/rt-n56u/trunk/user/httpd/aspbw.c
* /opt/rt-n56u/trunk/user/httpd/httpd.h
* /opt/rt-n56u/trunk/user/www/n56u_ribbon_fixed/general.js
Follow the changes in https://github.com/hanwckf/rt-n56u/commit/dce45e21b0bed791da96ea3b3630db766111fdcf except for general.js
For general.js, delete function validate_ssidchar or always return true. Add a function that checks the string in utf-8 length.
