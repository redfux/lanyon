---
layout: post
Title: Certificate and Cisco WLC
Date:  2013-10-11 12:58 
Tags: wireless,cisco,knowledge
Published: true
---

**!!!only with openssl version  [0.9.8x] [winopenssl]!!!**

    OpenSSL> req -new -newkey rsa:2048 -nodes -keyout wlckey.pem -out wlcreq.pem [-config openssl_XX.cfg]

    OpenSSL> pkcs12 -export -in [name from CA signed request].cer -inkey wlckey.pem -out CA.p12 -clcerts -passin pass:WLC_secret -passout pass:WLC_secret
    OpenSSL> pkcs12 -in CA.p12 -out wlcfinal.pem -passin pass:WLC_secret -passout pass:WLC_secret


[winopenssl]: http://gnuwin32.sourceforge.net/packages/openssl.htm
