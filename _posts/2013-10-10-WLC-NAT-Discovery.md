---
layout: post
Title: WLC NAT-Discovery for OEAPs
Date:  2013-10-10 23:57 
Tags: cisco,wireless,knowledge
Published: true
---

####Configuring NAT Discovery

>extract from WLC release notes

The following command controls which address(es) are sent in CAPWAP discovery responses when NAT is enabled on the Management Interface:

    config network ap-discovery nat-ip-only {enable | disable}

Where:    
**enable** — Enables use of NAT IP only in Discovery response. This is the default. Use this command if all APs are outside of the NAT gateway.

**disable** — Enables use of both NAT IP and non-NAT IP in discovery response. Use this command if APs are on the inside and outside of the NAT gateway; for example, Local Mode and OfficeExtend APs on the same controller.

>*Note*    
To avoid stranding APs, you must disable AP link-latency (if enabled) before you use the disable option for the config network ap-discovery nat-ip-only command. To disable AP link-latency, use the config ap link-latency disable all command. 