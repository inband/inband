---
title: nso config template

---


Note

!!! Note
    This is a note


```
admin@ncs(config)# devices template aaa-template ned-id cisco-ios-cli-6.77 
admin@ncs(config-template-aaa-template)# commit dry-run 
cli {
    local-node {
        data  devices {
                  template aaa-template {
             +        ned-id cisco-ios-cli-6.77 {
             +        }
                  }
              }
    }
}
admin@ncs(config-ned-id-cisco-ios-cli-6.77)# config 
admin@ncs(config-config)# aaa authentication login default local 
admin@ncs(config-login-default)# exit                                  
admin@ncs(config-config)# aaa authorization exec default local 
admin@ncs(config-exec-default)# exit
admin@ncs(config-config)# exit
admin@ncs(config-ned-id-cisco-ios-cli-6.77)# exit
admin@ncs(config-template-aaa-template)# commit dry-run 
cli {
    local-node {
        data  devices {
                  template aaa-template {
             +        ned-id cisco-ios-cli-6.77 {
             +            config {
             +                aaa {
             +                    authentication {
             +                        login default {
             +                            local;
             +                        }
             +                    }
             +                    authorization {
             +                        exec default {
             +                            local;
             +                        }
             +                    }
             +                }
             +            }
             +        }
                  }
              }
    }
}
admin@ncs(config-template-aaa-template)# commit
Commit complete.

```

---


Apply template


```
admin@ncs(config)# devices device-group all-routers-group apply-template template-name aaa-template 
apply-template-result {
    device bne-p1
    result ok
}
apply-template-result {
    device mel-p1
    result ok
}
apply-template-result {
    device mel-p2
    result ok
}
apply-template-result {
    device mel-pe1
    result ok
}
apply-template-result {
    device mel-pe2
    result ok
}
apply-template-result {
    device mel-rr1
    result ok
}
apply-template-result {
    device syd-p1
    result ok
}
apply-template-result {
    device syd-p2
    result ok
}
apply-template-result {
    device syd-pe1
    result ok
}
apply-template-result {
    device syd-pe2
    result ok
}
apply-template-result {
    device syd-rr1
    result ok
}
admin@ncs(config)# commit dry-run 
cli {
    local-node {
        data  devices {
                  device bne-p1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-p1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-p2 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-pe1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device mel-pe2 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-p1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-p2 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-pe1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-pe2 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
             +                        local;
             +                    }
                              }
                          }
                      }
                  }
                  device syd-rr1 {
                      config {
                          aaa {
                              authorization {
             +                    exec default {
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
