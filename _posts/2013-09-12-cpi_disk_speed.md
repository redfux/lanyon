---
layout: post
Title: CPI Disk IOPS-Test
Date: 2013-9-12 10:20 
Tags: prime,cisco,knowledge,links
---

To check the disk IO speed you will have to access the underlying shell.

Execute following commands to access the underlying shell:

	Root_enable
>this will allow you to set password for root access

	Root
>enter the password which you set above

	date;dd if=/dev/zero of=disk1.img bs=1024k count=3000;
>this command will give you the disk IO speed.
 
Recommended value for the IOPS (Input/Output Operations Per Second) is 200 MB/s.    
[CPI Deployment Guide] [1]

####Update:  "ncs run test iops" will be introduced in PI2.0.

[1]: http://www.cisco.com/en/US/prod/collateral/netmgtsw/ps6504/ps6528/ps12239/deployment_guide_c07-721232.html#wp9000587