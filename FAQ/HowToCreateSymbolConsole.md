How to create a symbol for /dev/ttyUSBx:  
* `udevadm info /dev/ttyUSB0 |grep ID_PATH`  
 Get the ID_PATH info  
* `touch /etc/udev/rules.d/99-usb-serial.rules`  
* add the following text like this:    

 >SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:00:1d.0-usb-0:1.5.1:1.0", SYMLINK+="ttyUSB_0"
