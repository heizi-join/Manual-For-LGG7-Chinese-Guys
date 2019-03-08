# 用IDA破解LG UP混刷KDZ教程
本教程对G7任何版本起作用，包括没有Root的设备，V30/35/40理论可用。 <br />
本教程的排列方式为英文字母ABCDEFGH排序而不是选择题 <br />
本教程来自 [查看链接🔗](https://forum.xda-developers.com/lg-g7-thinq/how-to/tutorial-install-korean-pie-kdz-g7-t3892700)  汉化来自@机智哒如如 由我修改发布
## 风险警告
⚠Warning 风险在向你靠近⚠<br />
⚠不建议主力机、上班族、穷困精准扶贫人口、动手能力不强、超级小白、脾气暴躁等人群自行刷机二哈，虽然风险很小但是无处不在，二哈我不能保证每一个抠脚的人不会应为抠脚导致病毒感染而死。⚠<br />
⚠步骤G时，为了省下不必要的资金浪费，请不要在刷机过程中断开连接。⚠<br />

# 开始作死！
[❤点❤我❤看❤视❤频❤教❤程❤](https://www.bilibili.com/video/av45261978/#reply1436800150)

## 注意事项
如果你的设备是在**淘宝换U Root**后刷韩版Pie, 为了不翻车请提前在Fastboot刷好Pie的Rooted Boot。 <br />
没换过U的T版慎刷，到时候8要怪我没提醒过<br />
## A
下载/安装/准备 以下 文件/软件 <br />
¤ IDA 7.0 Pro 破解版 <br />
¤ LG UP (原版) <br />
¤ Notepad++ <br />
‖ 自己机型的DLL <br />
‖ 自己的要刷的KDZ <br />
※ 将手机调到Download模式 <br />
以上均能从百度/谷歌上找到 <br />

#### DLL
-用[这个软件](https://www.lanzous.com/i3aj9cd?t)解开KDZ的LGUPc.dll即可获得该KDZ的DLL <br />
-路径为`LGUP安装文件夹/model/common/LGUP_Common.dll` <br />
-如果没有Common文件夹自行创建
-一般Common文件夹是隐藏的，建议关闭LGUP再更改。
## B
以管理员打开IDA64后步骤如下 <br />
-单击New <br />
-选择LG UP安装位置/LG UP.exe <br />
-单击底下的OK <br />
如果一切顺利的话你会进入和图中差不多的界面 <br />
![截图](/1.png)  <br />
### Note
如果不顺利的话会跳出个框让你选文件，随便选一个你喜欢的目录就好了，不是很讲究。
## C
-如果出现选择PDB文件窗口，点击取消。 <br />
-喝口水等待加载完成出现进程树 <br />
## D
![截图2](/2.png) <br />
-在工具栏右侧将“no debugger”选项改成“local windows debugger” (截图蓝框处)<br />
-单击选项的左侧绿色播放按钮(截图红框处)后选择Yes <br />
-等待弹出Warning警告弹窗后继续下一步 <br />
-单击左上角绿色播放按钮后选择Yes <br />
-等待弹出LG UP窗口后将其关闭 <br />
## E
-按住ALT+T或在顶部工具栏Search(截图绿框处)选项中找到Text <br />
-输入“.lgl”后单击OK <br />
-顶部工具栏Debugger选项(截图紫框处)中找到Breakpoints后选择Add points弹出界面后单击OK <br />
-单击绿色播放按钮后等待弹窗单击OK <br />
-单击绿色播放按钮后单击Yes后单击OK <br />

## F
-用“Notepad++”打开“LG UP安装目录/Model/Common/UI_Config.lgl” <br />
-找到`<PROCESS strName="PARTITION DL"……`下方的
`<SUPPORT strUser=“Dev” /> `（Ctrl+F搜索 输入PARTITION DL搜索即可） <br />
-把`=“Dev”`更成 `=“LAB|Store|Dev|3rdParty” `<br />
-保存 不要关闭Notepad++ 切换到IDA <br />
-单击左上角绿色播放按钮弹出LG UP界面后继续 <br />
#### Note
如果找不到lgl文件重复步骤“E”

## G
-Process选择PARTITION DL模式 <br />
-选择要刷的KDZ <br />
-点击下方Start <br />
-勾选Select All 单击OK <br />
**-如果你是Root设备，(请在刷入Rooted Boot后)解除boot_a和boot_b的勾选** <br />
#### Note
出现Warning警告窗口 <br />
-单击OK <br />
-单击绿色播放按钮**快捷键F9** <br />
-单击Yes <br />
疯狂重复以上步骤直到警告弹窗停歇 <br />
# H
完了，享受刷完的新固件吧！ <br />
有什么问题欢迎加入“[LG G7 ThinQ 垃圾佬快活群](https://jq.qq.com/?_wv=1027&k=5KEkuSU)”和我们讨论一下
