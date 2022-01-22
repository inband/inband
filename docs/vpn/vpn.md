Virtual Private Network (VPN) is a fairly loose term which encompasses different methods of transporting traffic "seperately".  There are many types of VPNs.  The key term is virtual - this refers to building a network using logical/encapsulated seperation.  Many VPNs are only private by their seperation - they may not be considered secure.

Some of the differnet technologies used to create VPNs.


* L2TPv2, L2TPv3
* PPTP
* MPLS (LDP, RSVP-TE, FRR)
* MPLS Layer 3 - VPNv4, VPNv6 (BGP)
* MPLS Layer 2 - AToM
* IPsec (Site-to-site, client-server)
* GRE
* VRF, VRF-lite, VLANs(802.1q/802.1ad), PPP, PPPoE, IP-in-IP
* DMVPN
* OpenVPN
* SSL/TLS


These technologies require an overhead - usually in the form of a header - to achieve seperation.  Many technologies can be combined to achieve desired outcome.

A VLAN might require a smallish 4-Byte header whereas a full-featured IPsec tunnel a much larger header/s and is likely to operate over a VLAN.
