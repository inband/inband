---
title: proxmox clone vm

---



!!! Note
    This is a note


Clone vm's

```
# qm clone <vmid> <newid> [OPTIONS]
root@pve:~# qm clone 650 501 --name "mel-p1"
```

Check new vm

```
root@pve:~# cat /etc/pve/nodes/pve/qemu-server/501.conf 
balloon: 0
boot: cdn
bootdisk: virtio0
cores: 2
memory: 4096
name: mel-p1
net0: virtio=EE:88:52:DE:81:CE,bridge=vmbr0,firewall=1,tag=999
numa: 0
serial0: socket
smbios1: uuid=53910165-add3-4068-9262-0eb79abcc331
sockets: 1
virtio0: local-lvm:vm-501-disk-0,size=8G
vmgenid: 3a7beeaf-0dd3-48fd-8657-390e722f1ed3
```


Add additional network interface

```
# qm set 501 -net1 virtio,bridge=vmbr0,firewall=1,tag=312
root@pve:~# qm set 501 -net1 virtio,bridge=vmbr0,firewall=1,tag=312
update VM 501: -net1 virtio,bridge=vmbr0,firewall=1,tag=312
```
