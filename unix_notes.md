#Unix Notes

##Contents
[TOC]

###Basic
- - -
`sudo !!` : run the last command with sudo permission
`w`, `who`, `last hafiz`, `history`
`sudo vim /etc/hostname` : edit the machine hostname
###Group
- - -
`sudo addgroup mafia` : create new group mafia
`sudo chgrp mafia /testfolder/` : give mafia group the ownership over the folder

###Permissions
- - -
`ls -l -d supahands.md` : show file/folder permissions
`-rw-rw-r-- 1 hafiz hafiz 5233 Sep 16 13:40 vim_notes.md`
-`owner`-`group`-`else`--
`r`ead, `w`rite, e`x`ecute | `owner` | `group` |
`0` : no access, `1` : execute only, `4` : read only, `5` : read & execute,
`6` : read & write, `7` : full permission

`sudo chmod 751 /testfolder/` : change folder permission
`id` : see what groups current user is a member of
`sudo usermod -a -G mafia hafiz` : add user(hafiz) to the mafia group
`sudo usermod -G cdrom admin audio hafiz` : remove hafiz from mafia group (exclude the group)
`sudo delgroup mafia` : delete the mafia group
`sudo deluser hafiz` : delete the hafiz user

###Services
- - -
`sudo service --status-all` : show all the services available
`sudo service elasticsearch status` : check the status of elasticsearch process
`sudo service elasticsearch start` : start the elasticsearch process
`sudo service elasticsearch stop` : stop the elasticsearch process
`ps aux` : list all the process that are running
`sudo kill 9385` : kill the process with the id 9385
`sudo kill -9 9385` : kill the process with cruel death
`top` : application to view processes in realtime

###Packages
- - -
`aptitude` : launch aptitude for package management
`sudo aptitude install elasticsearch` : install elasticsearch package
`cat /etc/apt/sources.list` : list all the sources for packages
`dotdeb.org` : co the website!!
`sudo aptitude remove elasticsearch` : remove elasticsearch package
`apt-cache search ruby` : seach ruby related packages that are available
`sudo aptitude upgrade` : upgrade currently installed packages

###Logs
- - -
`sudo ls /var/log/elasticsearch` : list all logs for elasticsearch service
`sudo tail /var/log/elasticsearch/elasticsearch.log` : preview the tail logs
`sudo grep RAID /var/log/syslog` : grep any RAID text in syslog
`sudo ag redis /var/log/syslog` : ack any redis text in syslog

###Grep/Ack
- - -
`grep ssh` : grep text ssh
`ps aux | grep ssh` : run the ps, then pipe the result to grep

###Disk Management
- - -
`df -m` : list all drives with spaces used
`free -m` : check all available memory

###Network
- - -
`sudo netstat -ap` : see the network usages
`sudo ifconfig` : see network config
`sudo vim /etc/network/interfaces` : to set n

###SSH
- - -
`ssh-keygen -t rsa` : generate new rsa key pair
- create new `.ssh/authorized_keys` at other machine to save the rsa key 

`sudo vim /etc/ssh/sshd_config`, set `PasswordAuthentication no` to disable password login