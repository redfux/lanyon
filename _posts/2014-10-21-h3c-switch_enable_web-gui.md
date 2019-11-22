---
layout: post
Title: Config Example for enabling Web-GUI on HP A-Series Switches(aka H3C/3Com)
Date: 2014-10-22 09:45
Tags: hp,switching,tricky knoledge
Published: true
---


Yes I know configure Switches via Web-GUI is not the proffesional way, but in my opinion the H3C CLI is from Hell...


    #
     ip http enable 
    #
     web idle-timeout 999
    #
    radius scheme system
     primary authentication 127.0.0.1 1645
     primary accounting 127.0.0.1 1646
     user-name-format without-domain
    #
    domain system 
     access-limit disable
     state active 
     idle-cut disable 
     self-service-url disable 
    #
    user-group system
     group-attribute allow-guest
    #
    local-user manager
     password cipher XXXXXXXXXXXXXXXXXXXXXXXX
     authorization-attribute level 3
     service-type ssh telnet terminal
     service-type ftp
     service-type web
    #
    user-profile manager
    #
    user-interface aux 0 1
    user-interface vty 0 15
     authentication-mode scheme
     user privilege level 3