---
layout: post
tags: asa,knowledge,cisco
title: ASA-ROMMON - tftp-Download
date: 2013-09-11 11:10 
---

If for any reason the software image on your Cisco ASA appliance is corrupted and the device does not boot to normal operating mode, then you can load a new image using ROMMON (ROM monitor mode) and TFTP. Follow the steps below to get into ROMMON mode and then assign all necessary settings for uploading the new image file:

Step1: Connect to the ASA firewall using a console cable.

Step2: Power off the appliance and then power it on.

Step3: When the appliance starts, press the Escape key on your keyboard to force the appliance to enter ROMMON mode.

Step4: In ROMMON mode, configure all necessary settings for connecting to the TFTP server to load the new image. You need to connect a PC with TFTP server on a firewall port (e.g Ethernet0/0). Then enter the following commands on the ASA.

	ADDRESS=192.168.1.10
	SERVER=192.168.1.1
	GATEWAY=192.168.1.1
	IMAGE=asa800-232-k8.bin
	PORT=Ethernet0/0
 

The above configuration will assign an IP address of 192.168.1.10 to interface Ethernet0/0 of the firewall appliance. It will also tell the firewall that the TFTP SERVER is at address 192.168.1.1 and the image to load is asa800-232-k8.bin

Step5: Execute the TFTP upload from the ASA using:

	tftp

The above instructs the firewall to start uploading the image file from TFTP.

After the firewall reboots, login and check that the new image has been installed (show version)