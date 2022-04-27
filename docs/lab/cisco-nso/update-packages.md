---
title: nso install packages 

---



!!! Note
    This is a note


Install packages

```
root@nso1:~/nso-5.7/packages/neds# tar -zxvf ~/ncs-5.7-cisco-ios-6.77.10.tar.gz 

root@nso1:~/nso-5.7/packages/neds# tar -zxvf ~/ncs-5.7-cisco-nx-5.22.8.tar.gz 

```


```
admin@ncs# packages reload force

>>> System upgrade is starting.
>>> Sessions in configure mode must exit to operational mode.
>>> No configuration changes can be performed until upgrade has completed.
>>> System upgrade has completed successfully.
reload-result {
    package cisco-ios-cli-6.77
    result true
}
reload-result {
    package cisco-nx-cli-5.22
    result true
}
admin@ncs# 
System message at 2022-04-27 06:33:28...
    Subsystem started: ncs-dp-1-cisco-ios-cli-6.77:IOSDp
admin@ncs# 
System message at 2022-04-27 06:33:28...
    Subsystem started: ncs-dp-2-cisco-nx-cli-5.22:NexusDp
```

