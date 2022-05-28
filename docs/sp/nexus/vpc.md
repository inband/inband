# vpc

Vlan is added on one switch but not the other.


```
LAB_NEXUS1(config)# interface port-channel20
LAB_NEXUS1(config-if)# switchport trunk allowed vlan add 170
LAB_NEXUS1(config-if)# 2022 Apr 29 22:55:43 LAB_NEXUS1 last message repeated 1 time
2022 Apr 29 22:55:43 LAB_NEXUS1 %ETHPORT-3-IF_ERROR_VLANS_SUSPENDED: VLANs 170 on Interface port-channel20 are being suspended. (Reason: Vlan is not allowed on Peer-link)
```


Add vlan to other switch (other vpc peer)

```
 2022 Apr 29 22:56:59 LAB_NEXUS1 %ETHPORT-3-IF_ERROR_VLANS_REMOVED: VLANs 170 on Interface port-channel20 are removed from suspended state.
2022 Apr 29 22:56:59 LAB_NEXUS1 %ETHPORT-3-IF_ERROR_VLANS_REMOVED: VLANs 170 on Interface port-channel10 are removed from suspended state.
2022 Apr 29 22:56:59 LAB_NEXUS1 %ETHPORT-3-IF_ERROR_VLANS_SUSPENDED: VLANs 170 on Interface port-channel20 are being suspended. (Reason: Vlan is not allowed on Peer-link)
2022 Apr 29 22:56:59 LAB_NEXUS1 %ETHPORT-3-IF_ERROR_VLANS_REMOVED: VLANs 170 on Interface port-channel20 are removed from suspended state.


```
