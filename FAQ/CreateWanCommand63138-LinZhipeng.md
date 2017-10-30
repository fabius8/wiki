```
[root@AONT: /]# xtmctl conn --add 1.8.35 aal5 llcsnap_eth 0 1 1
[root@AONT: /]# xtmctl conn --createnetdev 1.8.35 atm0
[root@AONT: /]# xtmctl conn --addq 1.8.35 0 wrr 1
[root@AONT: /]# xtmctl operate conn --state 1.8.35 enable
[root@AONT: /]# xtmctl operate intf --state 1 enable
[root@AONT: /]# xtmctl operate intf --state 2 enable
[root@AONT: /]# ifconfig atm0 up


vlanctl --if-suffix . --if-create atm0 100 --if atm0 --routed --mcast

vlanctl --if atm0 --rx --tags 1 --filter-vid 100 0 --pop-tag --set-rxif atm0.100 --rule-append

vlanctl --if atm0 --rx --tags 2 --filter-vid 100 0 --pop-tag --set-rxif atm0.100 --rule-append

vlanctl --if atm0 --tx --tags 0 --filter-txif atm0.100 --push-tag --set-vid 100 0 --set-pbits 2 0 --rule-append

vlanctl --if atm0 --tx --tags 0 --filter-txif atm0.100 --push-tag --set-vid 100 0 --set-pbits 2 0 --rule-append

ifconfig atm0.100 up
brctl addif br0 atm0.100



PTM/ATM Command(Add/delete/Switch)
1. PTM(存在）-->删除PTM--->增加PTM-----|流OK，PPPoE OK|
xtmctl operate conn --deletenetdev 1.1
xtmctl operate conn --delete 1.1

xtmctl operate conn --add 1.1
xtmctl operate conn --addq 1.1 1 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 2 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 3 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 4 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 5 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 6 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 7 wrr 32 0 0 0
xtmctl operate conn --createnetdev 1.1 ptm0
xtmctl operate conn --state 1.1 enable
xtmctl operate intf --state 0x01 enable
ifconfig ptm0 down && ifconfig ptm0 up


2.PTM（存在）->删除PTM-->增加ATM（增加ATM 0）------|流能通，PPPoE OK,PPPPoA(有data cell发出）|
xtmctl operate conn --deletenetdev 1.1
xtmctl operate conn --delete 1.1

xdslctl start

xtmctl operate conn --add 1.8.35 aal5 llcsnap_eth 0 1 1
xtmctl operate conn --createnetdev 1.8.35 atm0
xtmctl operate conn --addq 1.8.35 0 wrr 1
xtmctl operate conn --state 1.8.35 enable
xtmctl operate intf --state 1 enable
xtmctl operate intf --state 2 enable
ifconfig atm0 down && ifconfig atm0 up

配置atm0.100 vlan，然后通过网页配置bridge-transparent模式.

3.ATM（存在）->删除ATM->增加ATM(增加ATM 0）------|流通,PPPoE OK, PPPoA(data cell 发出）|
xtmctl operate conn --deletenetdev 1.8.35
xtmctl operate conn --delete 1.8.35

xdslctl start

xtmctl operate conn --add 1.8.35 aal5 llcsnap_eth 0 1 1
xtmctl operate conn --createnetdev 1.8.35 atm0
xtmctl operate conn --addq 1.8.35 0 wrr 1
xtmctl operate conn --state 1.8.35 enable
xtmctl operate intf --state 1 enable
xtmctl operate intf --state 2 enable
ifconfig atm0 down && ifconfig atm0 up

配置vlan atm0.100
网页设置bridge模式

4.ATM(存在）->删除ATM->增加PTM（增加PTM 0）-----|流通，PPPoE OK|
xtmctl operate conn --deletenetdev 1.8.35
xtmctl operate conn --delete 1.8.35

xdslctl start(重启dsl连接）

xtmctl operate conn --add 1.1
xtmctl operate conn --addq 1.1 1 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 2 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 3 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 4 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 5 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 6 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 7 wrr 32 0 0 0
xtmctl operate conn --createnetdev 1.1 ptm0
xtmctl operate conn --state 1.1 enable
xtmctl operate intf --state 0x01 enable
ifconfig ptm0 down && ifconfig ptm0 up

5.ATM（不存在）&&PTM（不存在）-->增加ATM----------|流通，PPPoE OK,PPPoA(data cell已发出）

xtmctl operate conn --add 1.8.35 aal5 llcsnap_eth 0 1 1
xtmctl operate conn --createnetdev 1.8.35 atm0
xtmctl operate conn --addq 1.8.35 0 wrr 1
xtmctl operate conn --state 1.8.35 enable
xtmctl operate intf --state 1 enable
xtmctl operate intf --state 2 enable
ifconfig atm0 down && ifconfig atm0 up

xdslctl start---需要重启xdsl 来保证link状态挂钩到atm口


6.ATM（不存在）&&PTM（不存在）-->增加PTM---------------|流通，PPPoE OK!|


xtmctl operate conn --add 1.1
xtmctl operate conn --addq 1.1 1 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 2 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 3 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 4 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 5 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 6 wrr 32 0 0 0
xtmctl operate conn --addq 1.1 7 wrr 32 0 0 0
xtmctl operate conn --createnetdev 1.1 ptm0
xtmctl operate conn --state 1.1 enable
xtmctl operate intf --state 0x01 enable
ifconfig ptm0 down && ifconfig ptm0 up

xdslctl start---需要重启xdsl 来保证link状态挂钩到ptm口


[root@AONT: /]# xtmctl operate intf --stats
atm/ptm interface statistics for port 0
in octets                   110629285
out octets                  1742650
in packets                  825200
out packets                 8945
in OAM cells                0
out OAM cells               0
in ASM cells                0
out ASM cells               0
in packet errors            0
in cell errors              0

Port 1 is down
Port 2 is down
Port 3 is down


route模式配置
cfgcli -s InternetGatewayDevice.WANDevice.1.WANConnectionDevice.1.WANIPConnection.1.AddressingType Static
cfgcli -s InternetGatewayDevice.WANDevice.1.WANConnectionDevice.1.WANIPConnection.1.ExternalIPAddress 192.85.1.9

cfgcli -s InternetGatewayDevice.WANDevice.1.WANConnectionDevice.1.WANIPConnection.1.SubnetMask 255.255.255.0
cfgcli -s InternetGatewayDevice.WANDevice.1.WANConnectionDevice.1.WANIPConnection.1.DefaultGateway 192.85.1.8
```