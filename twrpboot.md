# 教你如何编译TWRP
编译LG G7的TWRP比其他的设备要难上一点，因为TWRP不在System分区，而是直接写在了Boot映像里。当用正常的方式进入Recovery模式时，用的是Boot里面的Ramdisk，而不是/System。所以这个教程是**教你如何编译TWRP** 
## Step.1 搭建Linxu环境
Windows Subsystem Linux啊 虚拟机啥都行 <br />
建议使用Ubuntu和Debian
## Step.2 熟悉编译TWRP那些事并编译TWRP
可以去https://forum.xda-developers.com/showthread.php?t=1943625 撸一下原帖，也可以去百度……
# Wait 你看不懂？
黑字你个憨批我怎么看得懂这些云里雾里的东西嘛！！！！！！！！（其实我也看不懂） <br />
那我改一下标题就好了嘤嘤嘤

# 如何简易的将TWRP写进Boot里！
(依旧对小白极度不友好)
## 首先我们得有Linux的环境
去百度一下Windows Subsystem Linux或者虚拟机之类的如何使用，当然你也可以装一个真的Linux（维笑）。发行版本用Ubuntu，不要问为啥，比较适合小白多一点吧啾咪。
## 安装软件
执行这个指令<br />
sudo apt-get install abootimg
小白:黑酱！老子看不懂!!!
黑字：BDYX！BDA！CNMNBHBDM？！！！
##　解开带TWRP的Boot
abootimg -x xxxxxboot.img
解完之后会得到三个文件
> zlmage

> bootimg.cfg

> initrd.img

留下initrd.img其他的都撒了（骨灰都给你羊了）
##  把initrd.img写自己想要的BOOT 
`abootimg -u xxxxxboot.img -r initrd.img` <br />
有时候会报错说啥**尺寸太大塞不进**啥的就像这样 <br />
`20f.img: updated is too big for the Boot Image (30015488 vs 25575424 bytes)` <br />
这时候你就可以在指令后面加上个-c "bootsize=xxxxxxxx"就像这样<br />
`abootimg -u xxxxxboot.img -r initrd.img -c "bootsize=30015488"`
## 成了
刷进去看看是不是能用了
欢迎朋友们加入"LG G7 ThinQ 垃圾佬快活群"或“LG G7 ThinQ Community”讨论一下哦
