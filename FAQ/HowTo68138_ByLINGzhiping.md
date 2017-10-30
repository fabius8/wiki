本文件适用于G010FA DPU/OLT 7360设备。有疑问或需要更多信息，可以咨询
R&D Dingfang Yang 小组，/Yang Qingqing/LING zhipeng/Zhang Weidong/Yongheng Ma等等
或PT：LIU Zhiqiang A/GE Shangbin 
Version: 2015-02-11_01 
Version: 2015-05-07_01

注册ONT和创建Qos/VLAN/bridge port过程与其它UNI 相同。

* 注册ONT
```
configure equipment ont interface 1/1/2/3/99 sernum ALCL:48484848 sw-ver-pland  disabled
configure equipment ont interface 1/1/2/3/99 admin-state up 
```
* 创建XDSL SLOT
注意XDSL 的slot 号必须为8。
```
configure equipment ont slot 1/1/2/3/99/8 planned-card-type vdsl2 plndnumdataports 1 plndnumvoiceports 0 admin-state up
configure interface port uni:1/1/2/3/99/8/1 admin-up
```
* Ether slot 号为1, Ether UNI for debug purpose
```
configure equipment ont slot 1/1/2/3/99/1 planned-card-type 10_100base plndnumdataports 1 plndnumvoiceports 0 admin-state up
configure interface port uni:1/1/2/3/99/1/1 admin-up
```

* 创建 qos/VLAN/bridge port 
```
configure qos interface 1/1/2/3/99/8/1 upstream-queue 0 bandwidth-profile name:1000M 

configure vlan id 504 mode residential-bridge in-qos-prof-name name:Default_TC0

configure bridge port 1/1/2/3/99/8/1 vlan-id 501 tag untagged

configure qos interface 1/1/2/3/99/8/1 scheduler-node name:NGLT_Default cac-profile name:FD_ONTUniVideo ds-num-rem-queue not-applicable us-num-queue not-appl0
configure qos interface 1/1/2/3/99/8/1 queue 0 priority 6 weight 34 oper-weight 34 queue-profile name:NGLT_Default shaper-profile none
configure qos interface 1/1/2/3/99/8/1 queue 1 priority 6 weight 66 oper-weight 66 queue-profile name:NGLT_Default shaper-profile none
configure qos interface 1/1/2/3/99/8/1 queue 2 priority 7 weight 0 oper-weight 0 queue-profile name:NGLT_Default shaper-profile none
configure qos interface 1/1/2/3/99/8/1 queue 3 priority 8 weight 0 oper-weight 0 queue-profile name:NGLT_Default shaper-profile none
configure qos interface 1/1/2/3/99/8/1 upstream-queue 0 bandwidth-profile name:100M
configure vlan id 35 mode residential-bridge in-qos-prof-name name:1q
configure vlan id 49 mode cross-connect in-qos-prof-name name:1q
configure bridge port 1/1/2/3/99/8/1 max-unicast-mac 100  
configure bridge port 1/1/2/3/99/8/1 vlan-id 10 vlan-scope local network-vlan 3000 tag single-tagged 
configure bridge port 1/1/2/3/99/8/1 pvid 10
configure bridge port 1/1/2/3/99/8/1 pvid 49
```

* 创建全局xdsl service profile 和spectrum profile
类似如下：
```
configure xdsl ont service-profile 1 name service1
configure xdsl ont service-profile 1 active
configure xdsl ont service-profile 10 name 10 min-bitrate-down 32 min-bitrate-up 32 max-bitrate-down 200000 max-bitrate-up 200000 max-delay-down 1 max-delay-up 1
configure xdsl ont service-profile 10 active
```
这个spectrum profile是支持G.FAST 和VDSL2,实际模式由DPU与CPE DSL协商.
```
configure xdsl ont spectrum-profile 1 name both 
configure xdsl ont spectrum-profile 1 active
```
这个spectrum profile是只支持VDSL2
```
configure xdsl ont spectrum-profile 11 name vdsl22 rf-band-list 07:08:07:d0:19:0d:ac:0f:a0:19:1b:58:1c:84:19:27:74:27:a6:19:36:b0:38:0e:19:46:94:46:f8:19:52:08:53:ca:19:61:3a:61:9e:19:6d:60:74:04:19
configure xdsl ont spectrum-profile 11 vdsl vdsl-band-plan annex-b-998ade pbo-mode pbo-mode-down adsl-band allow-adsl
configure xdsl ont spectrum-profile 11 vdsl2 psd-shape-down regionbm2-psd-down
configure xdsl ont spectrum-profile 11 active
```

* 设置xdsl line
设置成GFAST
```
configure xdsl ont line 1/1/2/3/99/8/1 service-profile 1 spectrum-profile 1 g993-2-17a 
configure xdsl ont line 1/1/2/3/99/8/1 admin-state up
configure xdsl ont line 1/1/2/3/99/8/1 admin-state down
```
**OR**, 设置成VDSL2
```
configure xdsl ont line 1/1/2/3/99/8/1 admin-state down
configure xdsl ont line 1/1/2/3/99/8/1 service-profile 1 spectrum-profile 11 g993-2-17a 
configure xdsl ont line 1/1/2/3/99/8/1 admin-state up
```

* 查看XDSL line 状态统计的命令
```
show xdsl ont operational-data near-end line 1/1/2/3/99/8/1 detail 
show xdsl ont operational-data far-end line 1/1/2/3/99/8/1 detail

show xdsl carrier-data near-end 1/1/2/3/99/8/1
show xdsl carrier-data far-end 1/1/2/3/99/8/1

show xdsl ont cpe-tur-inventory 1/1/2/3/99/8/1
show xdsl ont cpe-tuc-inventory 1/1/2/3/99/8/1

admin ont-xdsl-line 1/1/2/3/99/8/1 loop-diagnostic start
admin ont-xdsl-line 1/1/2/3/99/8/1 loop-diagnostic stop
info admin ont-xdsl-line 1/1/2/3/99/8/1 detail 

configure xdsl ont line 1/1/2/3/99/8/1 admin-state down
configure xdsl ont line 1/1/2/3/99/8/1 admin-state up
```

* 使能XDSL PM统计
```
configure xdsl ont line 1/1/2/3/99/8/1 pm-collect pm-enable
configure xdsl ont line 1/1/2/3/99/8/1 phy pm enable
```

* 设置TCA:
```
configure xdsl ont line 1/1/2/1/4/8/1 service-profile 1 spectrum-profile 1 g993-2-17a pm-collect tca-enable
configure xdsl ont line 1/1/2/1/4/8/1 phy pm enable tca enable ne-err-secs 900 ne-sev-err-secs 899 ne-unavail-secs 899 fe-sev-err-secs 100 fe-unavail-secs 100
configure xdsl ont line 1/1/2/1/4/8/1 admin-state up
show alarm current ont-xdsl-tca detail 
```

* 查看基本配置状态
```
show interface port flat
show equipment ont interface
show equipment ont operational-data
show equipment slot
info configure service 
show trouble-shooting statistics interface 1/1/2/1/4/8/1
info configure interface flat  

show service fdb-mac
show service fdb-info
show service id 111 fdb
show vlan stacked-vlan
show vlan fdb-board 
show vlan bridge-port-fdb
```

* 上联口配置
```
configure service vpls 666 customer 1 v-vpls vlan 666 create
configure service vpls 666 sap nt-a:xfp:4:666 create
configure service vpls 666 sap lt:1/1/1:666 create
configure service vpls 666 no shutdown
```

This conversation is being saved in your Outlook Inbox folder.
LING Zhipeng 16:23
0第三条命令的4是什么意思
TONG Wenbin 16:23
nt-a:xfp:4 
这个四？
LING Zhipeng 16:24
是的
TONG Wenbin 16:24

第4个OLT的上联口



OLT version
show software-mngt oswp 

OLT save configuration
admin save

OLT reboot
admin equipment reboot-isam with-self-test

===================================================

```
end of this file
export AR=mips-linux-ar
export CC=mips-linux-gcc
export CXX=mips-linux-g++
export LINK=mips-linux-g++

export CFLAGS=-static
export CXXFLAGS=-static
export LDFLAGS=-static
./configure --without-snapshot --prefix=/home/linux/nodejs/node_bin
```


autoreconf     mips-linux-ar         mips-linux-ld         mips-unknown-linux-uclibc-addr2line  mips-unknown-linux-uclibc-gprof      mips-unknown-linux-uclibc-strip
autoscan       mips-linux-as         mips-linux-ld.bfd     mips-unknown-linux-uclibc-ar         mips-unknown-linux-uclibc-ld         xmlwf
autoupdate     mips-linux-c++        mips-linux-ldconfig   mips-unknown-linux-uclibc-as         mips-unknown-linux-uclibc-ld.bfd
faked          mips-linux-cc         mips-linux-ldd        mips-unknown-linux-uclibc-c++        mips-unknown-linux-uclibc-ldconfig
fakeroot       mips-linux-c++filt    mips-linux-nm         mips-unknown-linux-uclibc-cc         mips-unknown-linux-uclibc-ldd
ifnames        mips-linux-cpp 