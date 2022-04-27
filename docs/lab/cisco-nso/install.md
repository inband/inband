---
title: nso install notes 

---



!!! Note
    This is a note


Install Cisco NSO

```

apt update
apt install vim
apt install default-jdk
apt install ant
apt install libxml2-utils 
sh nso-5.7.1.linux.x86_64.signed.bin
sh nso-5.7.1.linux.x86_64.installer.bin --local-install ~/nso-5.7
sh ncs-5.7-cisco-ios-6.77.10.signed.bin
sh ncs-5.7-cisco-nx-5.22.8.signed.bin
cd nso-5.7/packages/neds/
tar -zxvf ~/ncs-5.7-cisco-ios-6.77.10.tar.gz 
tar -zxvf ~/ncs-5.7-cisco-nx-5.22.8.tar.gz 
ncs-setup --package ~/nso-5.7/packages/neds/cisco-ios-cli-6.77/ --package ~/nso-5.7/packages/neds/cisco-nx-cli-5.22/ --dest nso-instance
cd nso-instance/
source $HOME/nso-5.7/ncsrc
ncs --status

```

Run NSO

```
root@nso1:~/nso-instance# ncs
root@nso1:~/nso-instance# ncs --status
```

Connect to NSO

```
root@nso1:~/nso-instance# ncs_cli -u admin -C

admin connected from 192.168.20.10 using ssh on nso1
admin@ncs#
```
