---
layout: post
Title: HP-Procurve - Mehrere lokale User
Date: 2015-07-13 09:48:25  
Tags: config,hp,switching,aaa
Published: true
---


    aaa authorization group <Gruppe> 1 match-command ssh permit
    aaa authentication local-user <Username>  group <Gruppe>  password plaintext
