## Linux学习笔记
[http://www.imooc.com/video/3243/0]

- 主分区：最多只能有4个。
- 扩展分区：
 - 最多只能有1个。
 - 主分区加扩展分区最多有4个。
 - 不能写入数据，只能包含逻辑分区
- 逻辑分区

数据块block默认4kb
访问文件先查表，概念假设，I节点(INODE)、修改时间、权限。

[http://www.imooc.com/video/3244/]

`dev`目录专门放硬件设备文件名

**硬件设备文件名**

|硬件|设备文件名|
|:---|:----:|
|IDE硬盘| /dev/hd[a-d]|
|SCSI/SATA/USB 硬盘| /dev/sd[a~p]|
|光驱| /dev/cdrom或/dev/hdc|
|软盘| /dev/fd[0-l]|
|打印机（25针）| /dev/lp[0-2]|
|打印机（USB)| /dev/usb/lp[0-15]|
|鼠标| /dev/mouse|

**分区设备文件名**
- 设备文件名
 - /dev/hdal(IDE  硬盘接口）
 - /dev/sdal ( SCS 砸盘接口、 SATA 硬盘接口）

**挂载**
- 必须分区
 - / (根分区）
 - swap分区（交换分区，内存2倍，不超过2GB )
- 推荐分区
 - /boot (启动分区，200MB )
 
逻辑分区一定是从5开始分




