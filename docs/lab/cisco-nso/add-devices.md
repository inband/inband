---
title: nso add devices

---



!!! Note
    This is a note


Allow ssh-rsa, add username and password

```
admin@ncs# config t
Entering configuration mode terminal
admin@ncs(config)# devices global-settings ssh-algorithms public-key [ ssh-ed25519 ecdsa-sha2-nistp256 ecdsa-sha2-nistp384 ecdsa-sha2-nistp521 rsa-sha2-512 rsa-sha2-256 ssh-rsa ]
admin@ncs(config)# devices authgroups group default umap admin remote-name admin remote-password ******
```

Add device

```
admin@ncs(config)# devices device mel-rr1
admin@ncs(config-device-mel-rr1)# state admin-state unlocked 
admin@ncs(config-device-mel-rr1)# device-type cli ned-id cisco-ios-cli-6.77 
admin@ncs(config-device-mel-rr1)# authgroup default 
admin@ncs(config-device-mel-rr1)# commit
admin@ncs(config-device-mel-rr1)# ssh fetch-host-keys 
result updated
fingerprint {
    algorithm ssh-rsa
    value 98:e9:4c:33:91:1f:ca:f6:53:e6:69:b0:03:24:b1:0d
}
admin@ncs(config-device-mel-rr1)# connect            
result true
info (admin) Connected to mel-rr1 - 192.168.18.30:22

```
