---
title: nso show commands

---





Show devices brief

```
admin@ncs# show devices brief                       
NAME     ADDRESS        DESCRIPTION  NED ID              
-------------------------------------------------------
mel-p1   192.168.18.31  -            cisco-ios-cli-6.77  
mel-p2   192.168.18.32  -            cisco-ios-cli-6.77  
mel-pe1  192.168.18.33  -            cisco-ios-cli-6.77  
mel-pe2  192.168.18.34  -            cisco-ios-cli-6.77  
mel-rr1  192.168.18.30  -            cisco-ios-cli-6.77  
syd-p1   192.168.18.21  -            cisco-ios-cli-6.77  
syd-p2   192.168.18.22  -            cisco-ios-cli-6.77  
syd-pe1  192.168.18.23  -            cisco-ios-cli-6.77  
syd-pe2  192.168.18.24  -            cisco-ios-cli-6.77  
syd-rr1  192.168.18.20  -            cisco-ios-cli-6.77 


```

---

Show full-configuration for device (in exec mode)

!!! Note
    This command does not auto-complete


```
admin@ncs(config-device-bne-p1)# pwd           
Current submode path:
  devices device bne-p1
admin@ncs(config-device-bne-p1)# show full-conf
```

---

Show interfaces

```
admin@ncs# show running-config devices device bne-p1 config interface 
devices device bne-p1
 config
  interface GigabitEthernet1
...
```

---

Show specific interface and display format as JSON.

```
admin@ncs# show running-config devices device bne-p1 config interface GigabitEthernet 1 | display json 
{
  "data": {
    "tailf-ncs:devices": {
      "device": [
        {
          "name": "bne-p1",
          "config": {
            "tailf-ned-cisco-ios:interface": {
              "GigabitEthernet": [
                {
                  "name": "1",
                  "negotiation": {
                    "auto": true
                  },
                  "mop": {
                    "xenabled": false,
                    "sysid": false
                  },
                  "vrf": {
                    "forwarding": "LAB_MGMT"
                  },
                  "ip": {
                    "address": {
                      "primary": {
                        "address": "192.168.18.71",
                        "mask": "255.255.254.0"
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      ]
    }


```

