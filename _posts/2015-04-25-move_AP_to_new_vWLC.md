---
layout: post
Title: Move APs to a new vWLC
Date:  2015-04-25 11:47
Tags: cisco,wlan,knowledge
Published: true
---

%CAPWAP-1-SSC_CERT_AUTH_FAILED: Failed to authorize controller, SSC certificate validation failed

Diese Fehlermeldung kann man erhalten, wenn man einen AP von einem vWLC zu einem anderen verschieben möchte (z.B. bei Neuinstallation). In diesem Fall kann man die CAPWAP-Einstellungen des APs mit folgendem Befehl löschen:

    clear capwap private-config

Anschließend muss der AP gebootet werden

>Tipp:
Wird der reboot über die cli des Aps mittel `reload` ausgelöst, verliert der AP sämmtliche Einstelungen (außer den IP-Einstellungen).
Wird er hingegen vom alten WLC aus über die Web-GUI gebuutet ("Reset AP"-Button) startet er zwar neu, und verbindet sich auch mit dem neunen vWLC, behält aber sämtliche Konfigurationen (Name, AP-Gruppen, AP-Mode, etc.).

Quelle:

- [www.madari.co.il] [1]
- [Cisco Supporrt Forum] [2]


[1]:[http://www.madari.co.il/2015/01/problem-capwap-1-ssccertauthfailed.html]
[2]:[https://supportforums.cisco.com/discussion/11839336/other-ap-not-joining-vwlc]
