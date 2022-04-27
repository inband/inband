---
title: proxmox notes 

---



!!! Note
    This is a note


Remove vm's

```
root@pve:~# qm list 
      VMID NAME                 STATUS     MEM(MB)    BOOTDISK(GB) PID       
       501 lab-mel-r1           stopped    4096              16.00 0         
       502 lab-mel-r2           stopped    4096              16.00 0         
       503 lab-syd-r1           stopped    4096              16.00 0         
       504 lab-syd-r2           stopped    4096              16.00 0         
       505 lab-bne-r1           stopped    4096              16.00 0         
       506 lab-bne-r2           stopped    4096              16.00 0         
root@pve:~# qm destroy 501
  Logical volume "vm-501-disk-0" successfully removed
root@pve:~# qm destroy 502
  Logical volume "vm-502-disk-0" successfully removed
root@pve:~# qm destroy 503
  Logical volume "vm-503-disk-0" successfully removed
root@pve:~# qm destroy 504
  Logical volume "vm-504-disk-0" successfully removed
^[[Aroot@pve:~# qm destroy 505
  Logical volume "vm-505-disk-0" successfully removed
root@pve:~# qm destroy 506
  Logical volume "vm-506-disk-0" successfully removed
```


