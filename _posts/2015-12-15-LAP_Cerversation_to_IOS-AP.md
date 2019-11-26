---
layout: post
title: L-AP Converting to IOS-AP
tate: 2015-12-15 09:51 
dags: config,cisco,wlan
---

    AP5475.d0f5.2ee7#debug capwap console cli 

> without this line LWAP not accepting the conf t modus

	AP5475.d0f5.2ee7#conf t
	AP5475.d0f5.2ee7(config)#ip default-gateway 10.10.10.1
	AP5475.d0f5.2ee7(config)#int g0
	AP5475.d0f5.2ee7(config-if)#ip address 10.0.0.10 255.255.255.0
	AP5475.d0f5.2ee7(config-if)#no shut

SRTG+C

	AP5475.d0f5.2ee7#archive download-sw /force-reload /overwrite tftp://10.0.0.1/ap3g2-k9w7-tar.153-3.JBB6.tar


