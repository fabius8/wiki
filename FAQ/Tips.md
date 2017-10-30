# 备忘
* 密码   
*-RDS.pdf 密码 `docs16130`
* python  
 https://stackoverflow.com/questions/18641438/installing-pip-3-2-on-cygwin
* FR地址  
http://isam-cq.web.alcatel-lucent.com/cqweb/

* 编译结果  
 http://135.251.206.224/cgi-bin/asb_delivery?selectRelease=HDR5601&selecttype=FDT
 http://135.251.206.106:8084/job/HDR5601_FDT1356_build_stage2/

* 版本地址  
http://135.251.206.224/IMAGE/HDR5601XGPON/  
* coverity  
 http://135.251.206.181:8080/reports.htm#v12692/p10076/fileInstanceId=28594610&defectInstanceId=21437421&mergedDefectId=90393  
 Coverity 的使用  
 http://fn-cm.sbell.com.cn/wiki/index.php/Coverity
* iperf
```
udp:  iperf3   -c 10.1.1.1  -p 9001  -u  -l 1024  -t 0  
tcp:  iperf3   -c 10.1.1.1  -p 9001  -l 1024  -t 0  

peijiancheng       10.1.1.1:9000
fangzheng            10.1.1.1:9001
zhaobio                  10.1.1.1:9002
shenpeihua           10.1.1.1:9003
zhangyiming          10.1.1.1:9004
xuqianqian          10.1.1.1:9005
zhuweiwei            10.1.1.1:9006
liqihua                    10.1.1.1:9007
yangyue                 10.1.1.1:9008
wuzhengyu            10.1.1.1:9009
guochunyang        10.1.1.1:9010
hedingjun               10.1.1.1:9011
```

* serial
```
[root@localhost qemu]# cat /etc/udev/rules.d/99-usb-serial.rules
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.1:1.0", SYMLINK+="ttyUSB_0"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.1:1.0", SYMLINK+="ttyUSB_1"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.3:1.0", SYMLINK+="ttyUSB_2"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.2.1:1.0", SYMLINK+="ttyUSB_3"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.4:1.0", SYMLINK+="ttyUSB_4"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.2.2:1.0", SYMLINK+="ttyUSB_5"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.2.1:1.0", SYMLINK+="ttyUSB_6"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.2.3:1.0", SYMLINK+="ttyUSB_7"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.4:1.0", SYMLINK+="ttyUSB_8"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.2.2:1.0", SYMLINK+="ttyUSB_9"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.3:1.0", SYMLINK+="ttyUSB_10"
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.6.2.3:1.0", SYMLINK+="ttyUSB_11"
```

* stc ip
135.251.193.12
```
3	1	pei jiancheng	R004J 19
3	2	pei jiancheng	R004J 20
3	3	pei jiancheng	R004J 21
3	4	pei jiancheng	R004J 22
3	5	zhang yiming	R004J 23
3	6	zhang yiming	R004J 24
```
* proxy ip  
135.245.48.34:8000

* O7 问题解决  
把光钎，改串号，删configs下面pon_disable

* vbox 共享文件不能创建软连接解决方法  
`VBoxManage setextradata VM_NAME VBoxInternal2/SharedFoldersEnableSymlinksCreate/SHARE_NAME 1`

* mount 共享文件  
`sudo mount -t vboxsf -o uid=$UID,gid=$(id -g) ShareName NewFolder`

* training 培训资料  
 https://ct.web.alcatel-lucent.com/scm-lib4/show-index-quick.cgi?key=8DM-02690-11..-TQZZA&index_sheet=

* windows proxy command
```
netsh interface portproxy show all
netsh interface portproxy add v4tov4 listenport=10001 listenaddress=0.0.0.0 connectport=10001 connectaddress=135.251.228.199
netsh interface portproxy add v4tov4 listenport=20001 listenaddress=0.0.0.0 connectport=20001 connectaddress=135.251.228.199
netsh interface portproxy reset
```