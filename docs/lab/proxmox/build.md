---
title: lab build - proxmox 

---



!!! Note
    This is a note


Clone vm's

```
qm clone 650 500 --name "mel-rr1"
qm set 500 -net1 virtio,bridge=vmbr0,firewall=1,tag=301
qm set 500 -net2 virtio,bridge=vmbr0,firewall=1,tag=302


qm clone 650 501 --name "mel-p1"
qm set 501 -net1 virtio,bridge=vmbr0,firewall=1,tag=312
qm set 501 -net2 virtio,bridge=vmbr0,firewall=1,tag=313
qm set 501 -net3 virtio,bridge=vmbr0,firewall=1,tag=314
qm set 501 -net4 virtio,bridge=vmbr0,firewall=1,tag=301
qm set 501 -net5 virtio,bridge=vmbr0,firewall=1,tag=2311
qm set 501 -net6 virtio,bridge=vmbr0,firewall=1,tag=3811

qm clone 650 502 --name "mel-p2"
qm set 502 -net1 virtio,bridge=vmbr0,firewall=1,tag=312
qm set 502 -net2 virtio,bridge=vmbr0,firewall=1,tag=323
qm set 502 -net3 virtio,bridge=vmbr0,firewall=1,tag=324
qm set 502 -net4 virtio,bridge=vmbr0,firewall=1,tag=302
qm set 502 -net5 virtio,bridge=vmbr0,firewall=1,tag=2322
qm set 502 -net6 virtio,bridge=vmbr0,firewall=1,tag=3822

qm clone 650 503 --name "mel-pe1"
qm set 503 -net1 virtio,bridge=vmbr0,firewall=1,tag=313
qm set 503 -net2 virtio,bridge=vmbr0,firewall=1,tag=323
qm set 503 -net3 virtio,bridge=vmbr0,firewall=1,tag=334

qm clone 650 504 --name "mel-pe2"
qm set 504 -net1 virtio,bridge=vmbr0,firewall=1,tag=314
qm set 504 -net2 virtio,bridge=vmbr0,firewall=1,tag=324
qm set 504 -net3 virtio,bridge=vmbr0,firewall=1,tag=334


qm clone 650 510 --name "syd-rr1"
qm set 510 -net1 virtio,bridge=vmbr0,firewall=1,tag=201
qm set 510 -net2 virtio,bridge=vmbr0,firewall=1,tag=202


qm clone 650 511 --name "syd-p1"
qm set 511 -net1 virtio,bridge=vmbr0,firewall=1,tag=212
qm set 511 -net2 virtio,bridge=vmbr0,firewall=1,tag=213
qm set 511 -net3 virtio,bridge=vmbr0,firewall=1,tag=214
qm set 511 -net4 virtio,bridge=vmbr0,firewall=1,tag=201
qm set 511 -net5 virtio,bridge=vmbr0,firewall=1,tag=2311
qm set 511 -net6 virtio,bridge=vmbr0,firewall=1,tag=2711

qm clone 650 512 --name "syd-p2"
qm set 512 -net1 virtio,bridge=vmbr0,firewall=1,tag=212
qm set 512 -net2 virtio,bridge=vmbr0,firewall=1,tag=223
qm set 512 -net3 virtio,bridge=vmbr0,firewall=1,tag=224
qm set 512 -net4 virtio,bridge=vmbr0,firewall=1,tag=202
qm set 512 -net5 virtio,bridge=vmbr0,firewall=1,tag=2322
qm set 512 -net6 virtio,bridge=vmbr0,firewall=1,tag=2722

qm clone 650 513 --name "syd-pe1"
qm set 513 -net1 virtio,bridge=vmbr0,firewall=1,tag=213
qm set 513 -net2 virtio,bridge=vmbr0,firewall=1,tag=223
qm set 513 -net3 virtio,bridge=vmbr0,firewall=1,tag=234

qm clone 650 514 --name "syd-pe2"
qm set 514 -net1 virtio,bridge=vmbr0,firewall=1,tag=214
qm set 514 -net2 virtio,bridge=vmbr0,firewall=1,tag=224
qm set 514 -net3 virtio,bridge=vmbr0,firewall=1,tag=234

qm clone 650 521 --name "bne-p1"
qm set 521 -net1 virtio,bridge=vmbr0,firewall=1,tag=712
qm set 521 -net2 virtio,bridge=vmbr0,firewall=1,tag=713
qm set 521 -net3 virtio,bridge=vmbr0,firewall=1,tag=714
qm set 521 -net4 virtio,bridge=vmbr0,firewall=1,tag=2711

qm clone 650 522 --name "bne-p2"
qm set 522 -net1 virtio,bridge=vmbr0,firewall=1,tag=712
qm set 522 -net2 virtio,bridge=vmbr0,firewall=1,tag=723
qm set 522 -net3 virtio,bridge=vmbr0,firewall=1,tag=724
qm set 522 -net4 virtio,bridge=vmbr0,firewall=1,tag=2722

qm clone 650 523 --name "bne-pe1"
qm set 523 -net1 virtio,bridge=vmbr0,firewall=1,tag=713
qm set 523 -net2 virtio,bridge=vmbr0,firewall=1,tag=723
qm set 523 -net3 virtio,bridge=vmbr0,firewall=1,tag=734

qm clone 650 524 --name "bne-pe2"
qm set 524 -net1 virtio,bridge=vmbr0,firewall=1,tag=714
qm set 524 -net2 virtio,bridge=vmbr0,firewall=1,tag=724
qm set 524 -net3 virtio,bridge=vmbr0,firewall=1,tag=734

qm clone 650 531 --name "per-p1"
qm set 531 -net1 virtio,bridge=vmbr0,firewall=1,tag=812
qm set 531 -net2 virtio,bridge=vmbr0,firewall=1,tag=813
qm set 531 -net3 virtio,bridge=vmbr0,firewall=1,tag=814
qm set 531 -net4 virtio,bridge=vmbr0,firewall=1,tag=3811

qm clone 650 532 --name "per-p2"
qm set 532 -net1 virtio,bridge=vmbr0,firewall=1,tag=812
qm set 532 -net2 virtio,bridge=vmbr0,firewall=1,tag=823
qm set 532 -net3 virtio,bridge=vmbr0,firewall=1,tag=824
qm set 532 -net4 virtio,bridge=vmbr0,firewall=1,tag=3822

qm clone 650 533 --name "per-pe1"
qm set 533 -net1 virtio,bridge=vmbr0,firewall=1,tag=813
qm set 533 -net2 virtio,bridge=vmbr0,firewall=1,tag=823
qm set 533 -net3 virtio,bridge=vmbr0,firewall=1,tag=834

qm clone 650 534 --name "per-pe2"
qm set 534 -net1 virtio,bridge=vmbr0,firewall=1,tag=814
qm set 534 -net2 virtio,bridge=vmbr0,firewall=1,tag=824
qm set 534 -net3 virtio,bridge=vmbr0,firewall=1,tag=834






end


```

