---
layout: post
title: 3rd-Party SFPs in Cisco Switches
date: 2019-11-20
tags: lan switching cisco hardware
---

Works with many Cisco CatXXXX-Switch-Series

**CLI**

    service unsupported-transceiver
    no errdisable detect cause gbic-invalid

**Hint - not all SFP+-Moduls will be correct detected** 

Real-Life Szenario:

- Cat2960X detected a 10G-Finistar-SFP as 1G-SFP at Port G1/0/49
- Cat4500X deteced the same SFP+ correctly as unknown 10G-SFP+, but without any output for `show interface transiver`


