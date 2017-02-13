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

6个纯命令行界面`[Ctrl]+[Alt]+[F1]～[F6]`,图形界面`[Ctrl]+[Alt]+[F7]`

`Ctrl+c`强行终止当前程序|`Ctrl+d`退出终端|`Ctrl+z`将当前程序放到后台运行，恢复到前台为命令`fg`|`Ctrl+a`相当于`Home`键,`Ctrl+a`相当于`End`键|`Ctrl+k`删除从光标所在位置到行末|`Ctrl+u`删除从光标所在位置到行首|`Alt+Backspace`向前删除一个单词|`Shift+PgUp`将终端显示向上滚动|`Shift+PgDn`将终端显示向下滚动|`Ctrl+P`相当于`上`键|`Ctrl+N`相当于`下`键|`Ctrl+H`相当于`Backspace`键






