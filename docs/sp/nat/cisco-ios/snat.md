---
title: snat (cisco-iosxe)

---

**Create snat one-to-one**

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
	 ip address 3.230.48.232 255.255.255.254
	 ip nat outside
	!
	ip nat inside source static 10.12.1.2 3.230.48.232 vrf INTERNET
	!

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
