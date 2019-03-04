# Note
本教程对G7任何版本起作用，包括没有Root的设备，V30/35/40理论可用。 <br />
本教程的排列方式为英文字母ABCDEFGH排序而不是选择题 <br />
本教程来自 [查看链接🔗](https://forum.xda-developers.com/lg-g7-thinq/how-to/tutorial-install-korean-pie-kdz-g7-t3892700)  汉化来自@机智哒如如 由我修改发布 <br />

 <br />
⚠如果你的设备是在**淘宝换U Root**后刷韩版Pie, 为了不翻车请提前在Fastboot刷好Pie的Rooted Boot⚠ <br />
 <br />
⚠如果你的设备是Root后刷其他版本的固件, 为了不翻车请提前在Fastboot刷好该固件的Rooted Boot⚠ <br />
 <br />
⚠如果你的设备是欧版Root刷韩版Pie, 为了不翻车请提前在Fastboot刷好root过的Boot⚠ <br />



# 开始!
 <br />
## A:
下载/安装/准备 以下 文件/软件 <br />
¤ IDA 7.0 Pro 破解版 <br />
¤ LG UP (原版) <br />
¤ Notepad++ <br />
‖ 自己机型的DLL <br />
‖ LMG71020C固件KDZ <br />
※ 将手机调到Download模式 <br />
以上均能从百度/谷歌上找到 <br />
KDZ待会再搬运，请持续关注看看号 <br />
 <br />
B: <br />
以管理员打开IDA64后步骤如下 <br />
-单击New <br />
-选择LG UP安装位置/LG UP.exe <br />
-单击底下的OK <br />
如果一切顺利的话你会进入到图中的界面 <br />
**假装我是个截图** <br />
**假装我是个截图** <br />
**假装我是个截图** <br />
Note: <br />
如果不顺利的话会跳出个框让你选文件，随便选一个你喜欢的目录就好了，不是很讲究。 <br />
 <br />
C: <br />
-如果出现选择PDB文件窗口，点击取消。 <br />
-喝口水等待加载完成出现进程树 <br />
 <br />
D:
-在工具栏右侧将“no debugger”选项改成“local windows debugger” <br />
-单击选项的左侧绿色播放按钮后选择Yes <br />
-等待弹出Warning警告弹窗后继续下一步 <br />
-单击左上角绿色播放按钮后选择Yes <br />
-等待弹出LG UP窗口后将其关闭 <br />
 <br />
E:
-按住ALT+T或在顶部工具栏Search选项中找到Text <br />
-输入“.lgl”后单击OK <br />
-顶部工具栏Debugger选项中找到Breakpoints后选择Add points弹出界面后单击OK <br />
-单击绿色播放按钮后等待弹窗单击OK <br />
-单击绿色播放按钮后单击Yes后单击OK <br />
 <br />
F: <br />
-用“Notepad++”打开“LG UP安装目录/Model/Common/UI_Config.lgl” <br />
-将36行的=“Dev”改为=“LAB|Store|Dev|3rdParty”
-保存 不要关闭Notepad++ 切换到IDA <br />
-单击左上角绿色播放按钮弹出LG UP界面后继续 <br />
 <br />
G: <br />
-Process选择PARTITION DL模式 <br />
-选择要刷的KDZ <br />
-点击下方Start <br />
-勾选Select All 单击OK
**如果你是Root设备，(请在刷入Rooted Boot后)解除boot_a和boot_b的勾选** <br />
 <br />
G-Note: <br />
出现Warning警告窗口 <br />
-单击OK <br />
-单击绿色播放按钮**快捷键F9** <br />
-单击Yes <br />
疯狂重复以上步骤直到警告弹窗停歇 <br />
 <br />
H: 
完了，享受刷完的新固件吧！ <br />
有什么问题欢迎加入“LG G7 ThinQ 垃圾佬快活群”和我们讨论一下
