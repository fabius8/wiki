# system
```
configure system id jielin-GAN-NGPON2
admin sntp system-time 2017-06-06:9:30:00 
configure system security profile admin terminal-timeout 0
configure system max-lt-link-speed link-speed forty-gb
configure system security profile admin slot-numbering type-based
admin save
```
# NT admin
```
configure service vpls 4000 customer 1 create
configure service vpls 4000 shutdown 
configure service vpls 4000 stp shutdown 
configure service vpls 4000 sap nt-b:xfp:3:4000 create 
configure service vpls 4000 sap nt-b:xfp:4:4000 create 
configure service vpls 4000 sap lt:1/1/2:4000 create 
configure service vpls 4000 sap lt:1/1/3:4000 create 
configure service vpls 4000 no shutdown
exit all 
configure service ies 2 customer 1 create
configure service ies 2 interface "telnet" create
configure service ies 2 interface "telnet " address 135.252.227.18/22
configure service ies 2 interface "telnet " sap nt:vp:1:4091 create
configure service ies 2 no shutdown
exit all
configure port nt-b:eth:1 
ethernet mode access 
ethernet encap-type dot1q 
no shutdown 
exit all
configure equipment slot  nt-a planned-type fant-f
configure port nt-a:eth:1 
ethernet mode access 
ethernet encap-type dot1q 
no shutdown 
exit all 
configure router static-route 0.0.0.0/0 next-hop 135.252.227.1
exit all
admin save
```
# Enable uplink port
```
configure port nt-b:xfp:1 ethernet autonegotiate
configure port nt-b:xfp:1 no shutdown

configure port nt-b:xfp:2 ethernet autonegotiate
configure port nt-b:xfp:2 no shutdown
configure port nt-b:xfp:3 ethernet autonegotiate
configure port nt-b:xfp:3 no shutdown
configure port nt-b:xfp:4 ethernet autonegotiate
configure port nt-b:xfp:4 no shutdown

configure port nt-a:xfp:1 ethernet autonegotiate
configure port nt-a:xfp:1 no shutdown

configure port nt-a:xfp:2 ethernet autonegotiate
configure port nt-a:xfp:2 no shutdown
configure port nt-a:xfp:3 ethernet autonegotiate
configure port nt-a:xfp:3 no shutdown
configure port nt-a:xfp:4 ethernet autonegotiate
configure port nt-a:xfp:4 no shutdown
```
# Need Logot
```
logout
```
# Enable the lt
```
configure equipment slot lt:1/1/3 planned-type nglt-a unlock
configure interface port pon:1/1/3/[1...8] admin-up
```