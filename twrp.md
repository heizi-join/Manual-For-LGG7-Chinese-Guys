# 编译TWRP教程

## 介绍
编译LG G7的TWRP比其他的设备要难上一点，因为TWRP不在System分区，而是直接写在了Boot映像里。当用正常的方式进入Recovery模式时，用的是Boot里面的Ramdisk，而不是/System。所以这个教程是**教你如何把TWRP写进Boot里面**。

## 正题

### 要求
linux(推荐Debian) (虚拟机也可以) <br />
20G空间 <br />
一些工具 `abootimg` `repo` `m4` `bison` `flex build-essential`  (Debian) <br />
ccache  (Even though this is fully optional)(黑字:看不懂？) <br />
	

### 文件
The guide from [Dees_troy is prett straighforward.](https://forum.xda-developers.com/showthread.php?t=1943625) That's why I oriented myself on this one.

I'd recommend using the minimal manifest as this is enough to build twrp properly.
Cloning it with git is noot needed. Use Google's repo tool, which you can find in the debian/ubuntu repos.
If you cannot find it in the repos of your distro, you can still get it from [here](https://gerrit.googlesource.com/git-repo/).

After getting this tool, get the minimal manifest linked in the guide (branch android-8.0), by following the procedures listed in the README of it.

Clone the following repo into the folder: `git clone https://github.com/sellerie98/android_device_lge_judy device/lge/judy`.

### Building
Now go back and setup the build enviroment:
 - run: `sudo apt install ccache` (This step is optional, but speeds up recompilations immensely, also it's only needed if its not installed yet)
 - export: `export LC_ALL=C`
 - export: `export USE_CCACHE=1` (Only do this if you decided to use ccache and have it installed)
 - run: `. ./build/envsetup.sh`
 - enter command: `lunch omni_judy-eng`
 - run: `make bootimage -j?` (Replace the ? with the number of the threads the device you're currently building on has +1)

This will take a while, but after that, you should have a bootimage.
This bootimage will most probably not work, so don't flash it yet! 

### Preparing the boot image
You need to modify any original boot image to make it work.
You can obtain these by getting a KDZ file (e.g. the one that autoprime posted [here](https://forum.xda-developers.com/lg-g7-thinq/development/dump-g7-stock-vendor-t3840834) and extracting it with kdztools mentioned in the 'General infos.md' file.
For that we use `abootimg`:
 - Create an empty folder and copy the twrp image and the original boot image into it
 - extract the twrp image: `abootimx -x <twrp image>
 - replace the initrd in the original image with TWRP: `abootimg -u <original image> -r initrd.img`

And voilá! There we have a LG G7 ThinQ boot image capable of booting TWRP and the respective android version (depending on the version you got the boot image from).
