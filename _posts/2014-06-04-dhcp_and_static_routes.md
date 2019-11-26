---
layout: post
title: Static Routes via DHCP
tate: 2014-06-04 10:23
dags: cisco,routing,tricky knoledge
published: true
---


### Example for publishing static routes via DHCP.

DHCP Option 121 = publish classless Routen via DHCP 

##### Example Route
route 172.20.0.0 255.255.0.0 172.20.1.1

notation for optin 121: [subnet bits].[subnet w/o. host part] [gw-IP]
 
=> 16.172.20 172.20.1.1

##### convert Dez to Hex:

Dez:	16.172.20 172.20.1.1

Hex:	ac.14.10 ac.14.01.01

=>hex syntax for Cisco IOS: 10ac.14ac.1401.01 

##### Example DHCP-Pool for Cisco IOS
    ip dhcp pool FlexPod-MGMT
       network 172.20.1.0 255.255.255.0
       domain-name demo.lan
       dns-server 172.20.10.10
       option 121 hex 10ac.14ac.1401.01
       lease 0 4

Link to [Cisco Support Forum entry] [1]

IETF link for [RFC3442] [2]



[1]: https://supportforums.cisco.com/discussion/11339881/cisco-ios-dhcp-server-classless-static-routes-dhcp-clients

[2]: http://tools.ietf.org/html/rfc3442