---
layout: post
title: PBR
tate:  2013-11-6 22:31
dags: cisco,routing
published: true
---

###HowTo configure PBR on Cisco Catalyst-Switch

a more detailed description (and maybe error correction) will follow.

>1) enable [sdm] [sdm] routing
 
    conf t    
    sdm prefer routing    
    exit    
    wr

>**reboot required!**

    reload

>2) ACL to filter I-Net traffic
 
    ip access-list extended PMM-INET    
     deny   ip 10.10.52.0 0.0.0.255 10.0.0.0 0.255.255.255 log    
     deny   ip 10.10.52.0 0.0.0.255 172.16.0.0 0.15.255.255 log    
     deny   ip 10.10.52.0 0.0.0.255 192.168.0.0 0.0.255.255 log    
     permit ip 10.10.52.0 0.0.0.255 any log    
    exit    


>3) Creat route-map named "PMM":    
>match at ACL "PMM-INET"   
>set Hotspot-GW as next hop

    route-map PMM permit 10    
     match ip address PMM-INET    
     set ip next-hop 10.10.52.5    
    exit    



>4) Bind route-map "PMM" to interface

    interface Vlan52    
     description PMM-TEST-VLAN    
     ip address 10.10.52.1 255.255.255.0    
     ip helper-address 10.10.204.5    
     ip policy route-map PMM    
    exit


[sdm]: https://supportforums.cisco.com/community/netpro/network-infrastructure/routing/blog/2011/03/31/pbr-on-switches-37503560