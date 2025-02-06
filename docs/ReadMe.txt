sbus驱动程序
https://github.com/jenswilly/sbus_serial.git

B站演示视频
https://www.bilibili.com/video/BV15M4m1Q7fz


4、如果要永久赋予普通用户操作USBCAN设备的权限，需要修改udev配置，并固定文件名，增加文件：/etc/udev/rules.d/10-hotrc-ch340.rules，内容如下：
	KERNEL=="ttyUSB*", ATTRS{idVendor}=="1a86", ATTRS{idProduct}=="7523", MODE:="0777", SYMLINK+="HotRC"

	重新加载udev规则后插拔设备即可应用新权限：
	# udevadm control --reload

ubuntu 22.04 安装 CH340串口驱动
https://blog.csdn.net/qq_44936797/article/details/143707771
sudo apt-get remove brltty # 可能被盲文程序拦截
