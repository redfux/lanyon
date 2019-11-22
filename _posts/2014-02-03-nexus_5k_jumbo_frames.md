---
layout: post
Title: Jumbo Frames @ Cisco Nexus 5k
Date: 2014-2-3 13:44 
Tags: cisco,switching,nexus
Published: true
---


    ena
    conf t

    policy-map type network-qos JUMBO
     class type network-qos class-default
      mtu 9216
     exit
    exit

    system qos
     service-policy type network-qos JUMBO
    exit


Jumbo Frames will be globaly enabled after typing these commands.