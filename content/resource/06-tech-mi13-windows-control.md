+++
title = "小米13手机与台式电脑协同"
date = 2024-10-01
updated = 2024-10-01

+++

因为要记录一些东西，数据在手机APP上，导出不太方便，一边操作手机一边在电脑也不太方便。所以试着把手机投屏到台式电脑上，并进行操作。

微软电脑会有自带的投屏，但用起来不太好用。下面记录的是使用 MIUI+ 投屏的步骤。

## 台式电脑需要有无线网卡

能够连接 WiFi 。然后需要更新网卡驱动。Win + R ，cmd 打开控制台，输入命令 `Get-NetAdapter|Select Name,NdisVersion` 查看版本号，WLAN 的版本号需要大于 6.40，若低于 6.40，可尝试更新无线网卡驱动。

![NdisVersion版本](/resource/06-tech-mi13-windows-control1.png)

## 在 Windows 中安装无线显示器

> Windows 设置 -> 应用 -> 可选功能 -> 查看功能 -> 安装无线显示器

安装需要等一会。

![安装无线显示器](/resource/06-tech-mi13-windows-control5.png)

## 需要支持 Miracast 

打开控制台，输入命令 `dxdiag` 打开 DxDiag 工具，后点击 保存所有信息 ，打开保存的 txt 文件，搜索 Miracast ，需要 Miracast 为 Available 状态，否则可能需要去更新显卡设置。

![Miracast状态](/resource/06-tech-mi13-windows-control2.png)

## 电脑端下载 MIUI+ 软件

通过这个[链接](https://www.mi.com/service/notebook/drivers/A29R)下载。

![下载 MIUI+ 软件](/resource/06-tech-mi13-windows-control3.png)

## 手机和台式电脑连接同一WiFi，然后连接即可

![连接](/resource/06-tech-mi13-windows-control4.png)

参考链接：

[手机投屏到电脑（以 MIUI 14 投屏 Windows11 为例）](https://blog.csdn.net/m0_61623174/article/details/131732981)

[Win10此设备不支持接收 Miracast 无法投影的解决方法](https://blog.csdn.net/zym0218/article/details/126688857)

[如何让我的电脑支持miracast](https://jingyan.baidu.com/article/ac6a9a5eb4fdf36b643eac1c.html#)

[不是小米的电脑也可以装MIUI+实现多屏协同，来看看怎么实现](https://zhuanlan.zhihu.com/p/662860377)
