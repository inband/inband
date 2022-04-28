---
title: nso config commands

---


```
admin@ncs# config t
Entering configuration mode terminal
admin@ncs(config)# devices device bne-p1 
admin@ncs(config-device-bne-p1)# config
admin@ncs(config-config)# aaa authentication login default local
admin@ncs(config-config)# commit dry-run 
cli {
    local-node {
        data  devices {
                  device bne-p1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
              }
    }
}
admin@ncs(config-config)# commit dry-run outformat native 
native {
    device {
        name bne-p1
        data aaa authentication login default local
    }
}
admin@ncs(config-config)# commit
Commit complete.
```

---

Config across multiple device

```
admin@ncs(config)# devices device *
admin@ncs(config-device-*)# config 
admin@ncs(config-config)# aaa authentication login default local
admin@ncs(config-config)# commit dry-run                        
cli {
    local-node {
        data  devices {
                  device mel-p1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-p2 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-pe1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-pe2 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-p1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-p2 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-pe1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-pe2 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-rr1 {
                      config {
                          aaa {
                              authentication {
             +                    login default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
              }
    }
}
```

---


Create device group

```
admin@ncs(config)# devices device-group all-routers-group device-name [ bne-p1 mel-p1 mel-p2 mel-rr1 mel-pe1 mel-pe2 ]
admin@ncs(config-device-group-all-routers-group)# commit
Commit complete.
admin@ncs(config-device-group-all-routers-group)# do show devices device-group member
NAME               MEMBER                                            
---------------------------------------------------------------------
all-routers-group  [ bne-p1 mel-p1 mel-p2 mel-pe1 mel-pe2 mel-rr1 ]  

admin@ncs(config)# devices device-group all-routers-group device-name [ bne-p1 mel-p1 mel-p2 mel-rr1 mel-pe1 mel-pe2 syd-p1 syd-p2 syd-pe1 syd-pe2 syd-rr1 ] 
admin@ncs(config-device-group-all-routers-group)# commit
Commit complete.

admin@ncs(config-device-group-all-routers-group)# show full-conf | begin all-routers
devices device-group all-routers-group
 device-name [ bne-p1 mel-p1 mel-p2 mel-pe1 mel-pe2 mel-rr1 syd-p1 syd-p2 syd-pe1 syd-pe2 syd-rr1 ]
!

```


---

Devices can be associated with multiple groups

```
admin@ncs(config)# do show devices device-group member 
devices device-group P
 member [ bne-p1 mel-p1 mel-p2 syd-p1 syd-p2 ]
devices device-group all-routers-group
 member [ bne-p1 mel-p1 mel-p2 mel-pe1 mel-pe2 mel-rr1 syd-p1 syd-p2 syd-pe1 syd-pe2 syd-rr1 ]
```



