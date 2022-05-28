# ospf mpls ldp


```
syd-p2#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
syd-p2(config)#mpls ldp router-id Lo0
syd-p2(config)#router os
syd-p2(config)#router ospf 1
syd-p2(config-router)#mpls ldp autoconfig area 0
syd-p2(config-router)#
*May  3 02:42:27.119: %LDP-5-NBRCHG: LDP Neighbor 198.18.0.20:0 (1) is UP
*May  3 02:42:27.134: %LDP-5-NBRCHG: LDP Neighbor 198.18.0.23:0 (2) is UP
*May  3 02:42:28.074: %LDP-5-NBRCHG: LDP Neighbor 198.18.0.21:0 (3) is UP

```



```
syd-p2#show mpls ldp discovery 
 Local LDP Identifier:
    198.18.0.22:0
    Discovery Sources:
    Interfaces:
        GigabitEthernet2.212 (ldp): xmit/recv
            LDP Id: 198.18.0.21:0
        GigabitEthernet3.223 (ldp): xmit/recv
            LDP Id: 198.18.0.23:0
        GigabitEthernet4.224 (ldp): xmit
        GigabitEthernet5.202 (ldp): xmit/recv
            LDP Id: 198.18.0.20:0

```
