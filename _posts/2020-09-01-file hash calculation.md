---
layout: post
Title: Hash calculation
Date: 2020-09-01 11:00 
Tags: knowledge,hash,windows,linux
---

# Hashwert von Files berechnen

## unter Windows mit cmd:

    certutil -hashfile [FILENAME] [MD5|MD2|MD4|SHA1|SHA256|SHA384|SHA512]


Bsp:

    certutil -hashfile Switche.txt SHA1
    SHA1-Hash von Switche.txt:
    e901fe79766fa5646cadcf1399738c1332381219
    CertUtil: -hashfile-Befehl wurde erfolgreich ausgeführt.
    
## unter Windows mit PowerShell:
    Get-FileHash .\[FILENAME] -Algorithm [MD5|SHA1|SHA256|SHA384|SHA512]
    
Bsp:

    Get-FileHash .\Switche.txt -Algorithm SHA1

    Algorithm       Hash                                       Path
    ---------       ----                                       ----
    SHA1            E901FE79766FA5646CADCF1399738C1332381219   C:\Temp\Switche.txt


geht auch mit mehreren Dateien gleichzeitig:

    Get-FileHash .\*.txt -Algorithm SHA1
    
## unter Linux

    md5sum [FILENAME]
    sha1um [FILENAME]
    sha256sum [FILENAME]
    sha384sum [FILENAME]
    sha512sum [FILENAME]
