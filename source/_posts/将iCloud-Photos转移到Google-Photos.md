title: 将 iCloud Photos 转移到 Google Photos
date: 2017-08-01 10:10:46
tags:
---

最近，在为转移 Android 阵地作准备。其中 iCloud 上 50G 的照片是最大的问题。

一开始使用 iOS 上的 [Google Photos](https://itunes.apple.com/app/apple-store/id962194608?pt=9008&ct=dwebpromo-empty&mt=8) 同步整个相册，但在移动设备上做一个全同步显然是十分不划算的，不仅不稳定、损耗设备，而且还对设备的使用造成不便。

于是乎，我把同步的工作转移到 Mac 上。

### 源文件

macOS 本地 Photos 源文件所在的地方。<span class="bigfoot-footnote__container"> <button class="bigfoot-footnote__button" id="fnref:1" data-footnote-number="1" data-footnote-identifier="1" alt="See Footnote 1" rel="footnote" data-bigfoot-footnote="
Right Click Photos Library.photoslibrary and Show Package Contents"> <svg class="bigfoot-footnote__button__circle" viewbox="0 0 6 6" preserveaspectratio="xMinYMin"><circle r="3" cx="3" cy="3" fill="white"/></svg> <svg class="bigfoot-footnote__button__circle" viewbox="0 0 6 6" preserveaspectratio="xMinYMin"><circle r="3" cx="3" cy="3" fill="white"/></svg> <svg class="bigfoot-footnote__button__circle" viewbox="0 0 6 6" preserveaspectratio="xMinYMin"><circle r="3" cx="3" cy="3" fill="white"/></svg> </button></span><br><a id="more"></a>

```
~/Pictures/Photos Library.photoslibrary/Masters/
```

### 准备同步

由于 [Backup and Sync from Google.app](https://www.google.com/drive/download/)  只能选择文件夹进行同步，因此我们需要将 **Masters** 文件夹拿出来。What？把50G东西复制一份？NONONO！我们只需要创建一个快捷方式就可以了。

```
ln -s ~/Pictures/Photos Library.photoslibrary/Masters  ~/Pictures
```

将 **Photos iCloud** 设置为 **Download Originals to this Mac**
![](http://7xsqni.com1.z0.glb.clouddn.com/2017-08-01-Screen%20Shot%202017-08-01%20at%207.11.05%20PM.png)

### 开始同步

在 **Backup and Sync from Google.app** 上选择刚刚创建的快捷方式，并按下**OK**，然后开始扫描文件。

![](http://7xsqni.com1.z0.glb.clouddn.com/2017-08-01-Screen%20Shot%202017-08-01%20at%206.36.22%20PM.png)
	
### 完成
	
等待同步结束，你就可以将图片转移到 **Google Photos** 了。


🎉🎉🎉

始终是两个公司的产物，所以有一些不尽人意的地方：

1. 没有 Exif 信息的图片时间会根据上传时间而改变（如：从 微信.app 拍摄的图片）；
2. **Google Photos.app** 上会出现重复图，Zero KB，可能是僵尸图；

由于 Google Photos 是监测文件夹的变化的，无奈我的 macbook 是乞丐版，128G版，不能一直这样增加照片，所以这次同步完成后，我就开始使用 iOS 客户端同步了，只要勤同步，一个晚上同步一天拍摄的照片还是可以的。

-EOF-