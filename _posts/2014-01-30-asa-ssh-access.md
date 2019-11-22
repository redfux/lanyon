---
layout: post
Title: ASA ssh access
Date: 2014-1-30 14:47 
Tags: csico,asa
Published: true
---


To enable ssh access on Cisco ASA you need three importand things:

1. create a user --> username admin password verysecret privilege 15
2. creat an RAS key pair --> crypto key generate rsa modulus 1024
3. set ssh athenticatin to local --> Aaa authentication ssh console LOCAL

>The first two steps are not new, but the last one was realy new for me. my last ASA installatins don't need this command, but it was my first 9.x installation.... who cares!