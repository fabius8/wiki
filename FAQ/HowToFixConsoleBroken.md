[[_TOC_]]

# 虚拟机串口不能访问问题原因？
插拔串口导致，虚拟机实例需要重新加载。

# 如何解决串口不能访问问题？
提供一个临时的方法：
* 登录到 `虚拟机服务器`
`ssh admin@10.9.65.19`

* 连接虚拟机qemu-kvm, 进入命令行模式
`virsh --connect qemu:///system`
输入密码 `asbasb`

* 查看自己的虚拟机实例
`list --all`
```
virsh # list --all
 Id    Name                           State
----------------------------------------------------
 5     Win7-2-zhaoBiao                running
 6     Win7-10-guochunyang            running
 7     Win7-3-shenpeihua              running
 8     Win7-4-zhangYiMing             running
 10    Win7-6-zhuWeiWei               running
 13    Win7-9-wuZhenyu                running
 14    server-20-ubuntu64             running
 31    Win7-7-liqihua                 running
 32    Win7-5-xuqianqian              running
 34    Win7-11-hedingjun              running
 36    Win7-8-yangYue                 running
 38    Win7-0-peijiancheng            running
 -     centos7.0-11-hedingjun         shut off
 -     centos7.0-base                 shut off
 -     ubuntu-fangzheng               shut off
 -     Win7-1-fangzheng               shut off
 -     Win7-base                      shut off
```
* 强制杀死自己的虚拟实例 `destroy Win7-1-fangzheng`
```
virsh # destroy Win7-1-fangzheng
Domain Win7-1-fangzheng destroyed
```

* 启动自己的虚拟实例 `start Win7-1-fangzheng`
```
virsh # start Win7-1-fangzheng
Domain Win7-1-fangzheng started
```
* NOTE  
 如果上述操作不行，请进工作站直接通过`minicom`检查下串口是否有问题。  
 `ssh admin@135.252.227.21`  
 `sudo minicom -D /dev/ttyUSB_3 -b 115200` 

 |端口|使用人|
| ---------------- | -------------- |
|/dev/ttyUSB_0 |pengneng|
|/dev/ttyUSB_1 | fangzheng|
|/dev/ttyUSB_2 |zhaobiao|
|/dev/ttyUSB_3 |shenpeihua|
|/dev/ttyUSB_4 |zhangyiming|
|/dev/ttyUSB_5 |xuqianqian|
|/dev/ttyUSB_6 |zhuweiwei|
|/dev/ttyUSB_7 |liqihua|
|/dev/ttyUSB_8|loudanqiong|
|/dev/ttyUSB_9 |wuzhenyu|
|/dev/ttyUSB_10|guochunyang|
|/dev/ttyUSB_11 |hedingjun|
|/dev/ttyUSB_12 |yangyue|
|/dev/ttyUSB_13 |ligunkui|
 
 如果仍有问题，请往下看`TIPS`

# TIPS  
有时串口会出现的错误，可能是hub供电不足导致的，`dmesg` 查看日志，出现以下错误日志，`重启虚拟机`恢复不了，需要`插拔串口USB总线`:
```
[3016317.931219] pl2303 ttyUSB17: pl2303_set_control_lines - failed: -32
[3016317.931588] pl2303 2-1.5.3:1.0: pl2303_vendor_write - failed to write [0000]: -32
[3016317.931968] pl2303 ttyUSB17: pl2303_set_control_lines - failed: -32
```
插拔之后恢复正常，通过`dmesg` 能看到如下日志：
```
[3016418.482908] usb 2-1.5.2.2: pl2303 converter now attached to ttyUSB18
[3016418.546537] usb 2-1.5.2.3: new full-speed USB device number 67 using ehci-pci
[3016418.621528] usb 2-1.5.2.3: New USB device found, idVendor=067b, idProduct=2303
[3016418.621535] usb 2-1.5.2.3: New USB device strings: Mfr=1, Product=2, SerialNumber=0
[3016418.621551] usb 2-1.5.2.3: Product: USB-Serial Controller
[3016418.621555] usb 2-1.5.2.3: Manufacturer: Prolific Technology Inc.
[3016418.622846] pl2303 2-1.5.2.3:1.0: pl2303 converter detected
[3016418.624767] usb 2-1.5.2.3: pl2303 converter now attached to ttyUSB20
```
* zhangyiming遇到需要进下虚拟机登一下com，remote才能登录com。。。

# 代理远程地址列表
  
|代理远程地址|使用人|
| ---------------- | -------------- |
|135.251.228.199:7000 |pengneng|
|135.251.228.199:7001 |fangzheng|
|135.251.228.199:7002 |zhaobiao|
|135.251.228.199:7003 |shenpeihua|
|135.251.228.199:7004 |zhangyiming|
|135.251.228.199:7005 |xuqianqian|
|135.251.228.199:7006 |zhuweiwei|
|135.251.228.199:7007 |liqihua|
|135.251.228.199:7008 |loudanqiong|
|135.251.228.199:7009 |wuzhenyu|
|135.251.228.199:7010 |guochunyang|
|135.251.228.199:7011 |hedingjun|
|135.251.228.199:7012 |yangyue|
|135.251.228.199:7013 |lijunhui|