---
title: snat and route-map (cisco-iosxe)

---

**Alter snat based on destination **

=== "nat-gateway"

	```
	hostname nat-gateway
	!
	vrf definition INTERNET
	 rd 2:2
	 !
	 address-family ipv4
	 exit-address-family
	!         
	interface GigabitEthernet3
	 no ip address
	 negotiation auto
	 no mop enabled
	 no mop sysid
	!         
	interface GigabitEthernet3.1012
	 encapsulation dot1Q 1012
	 vrf forwarding INTERNET
	 ip address 10.12.1.1 255.255.255.0
	 ip nat inside
	!
	interface GigabitEthernet4
	 no ip address
	 negotiation auto
	 no mop enabled
	 no mop sysid
	!
	interface GigabitEthernet4.1023
	 encapsulation dot1Q 1023
	 vrf forwarding INTERNET
	 ip address 198.18.23.1 255.255.255.252 secondary
	 ip address 3.230.48.232 255.255.255.254
	 ip nat outside
	!
	ip nat inside source static 10.12.1.2 3.230.48.232 vrf INTERNET route-map RM_DEFAULT
	ip nat inside source static 10.12.1.2 198.18.23.1 vrf INTERNET route-map RM_GOOGLE
	ip route vrf INTERNET 0.0.0.0 0.0.0.0 3.230.48.233
	!
	ip access-list extended ACL_DEFAULT
	 deny   ip 10.12.1.0 0.0.0.255 8.8.8.0 0.0.0.255
	 deny   ip 10.12.1.0 0.0.0.255 8.8.4.0 0.0.0.255
	 permit ip any any
	ip access-list extended ACL_GOOGLE
	 permit ip 10.12.1.0 0.0.0.255 8.8.8.0 0.0.0.255
	 permit ip 10.12.1.0 0.0.0.255 8.8.4.0 0.0.0.255
	!
	!
	route-map RM_DEFAULT permit 10 
	 match ip address ACL_DEFAULT
	 set ip next-hop 3.230.48.233
	!
	route-map RM_GOOGLE permit 10 
	 match ip address ACL_GOOGLE
	 set ip next-hop 198.18.23.2

	```

=== "cpe1"

	```
	hostname "cpe1"
	!
	interface GigabitEthernet3
	 no ip address
	 negotiation auto
	 no mop enabled
	 no mop sysid
	!
	interface GigabitEthernet3.1012
	 encapsulation dot1Q 1012
	 ip address 10.12.1.2 255.255.255.0
	!
	ip route 0.0.0.0 0.0.0.0 GigabitEthernet3.1012 10.12.1.1
	!

	```



=== "internet"

	```
	hostname internet
	!
	vrf definition INTERNET
	 rd 3:3
	 !
	 address-family ipv4
	 exit-address-family
	!  
	interface Loopback1111
	 vrf forwarding INTERNET
	 ip address 1.1.1.1 255.255.255.255
	!
	interface Loopback8844
	 vrf forwarding INTERNET
	 ip address 8.8.4.4 255.255.255.255
	!
	interface Loopback8888
	 vrf forwarding INTERNET
	 ip address 8.8.8.8 255.255.255.255
	!
	interface GigabitEthernet3
	 no ip address
	 negotiation auto
	 no mop enabled
	 no mop sysid
	!
	interface GigabitEthernet3.1023
	 encapsulation dot1Q 1023
	 vrf forwarding INTERNET
	 ip address 198.18.23.2 255.255.255.252 secondary
	 ip address 3.230.48.233 255.255.255.254
	 ip nat outside
	!


	```
