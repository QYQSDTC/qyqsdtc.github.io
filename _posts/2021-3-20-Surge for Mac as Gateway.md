---
Title: Surge for Mac as Gateway
Format: post
Tag:
	Surge
	Mac
	VPN
---

# Surge for Mac as Gateway: Turn your Mac into a powerful VPN server.

只有Mac能够翻墙很不爽？那么这篇博客将会告诉你如何使用Surge for Mac来代理局域网内所有的设备以实现全设备翻墙。

**注**：Surge 和 VPN服务需要单独购买。

## 准备工作

购买surge for Mac：[surge for Mac](https://nssurge.com/)

订阅VPN机场

在以上准备工作就绪后，我们就可以使用Surge for Mac的网关模式来代理我们局域网内的所有设备了。

## Config on Mac

确保你的surge打开了增强模式，并且已经是系统代理

![CleanShot 2021-03-20 at 11.12.34@2x](/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/CleanShot 2021-03-20 at 11.12.34@2x.png)

接下来查看Mac的内网IP

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/CleanShot 2021-03-20 at 11.15.29@2x.png" alt="CleanShot 2021-03-20 at 11.15.29@2x" style="zoom: 50%;" />

记住这个内网IP，接下来我们设置想要代理的设备。

## Config on target devices

这里我们以IOS设备为例，其他设备同理。

首先我们打开手机上的无线网设置，连接与Mac相同的局域网，然后手动设置ip address 为任意内网未使用ip，子网掩码不用改，然后把路由器地址改为Mac端内网ip

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0904-6211748.PNG" style="zoom:33%;" />

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0905-6211762.PNG" style="zoom:33%;" />

之后再在DNS添加**192.18.0.2**

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0906.PNG" style="zoom:33%;" />

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0908.PNG" style="zoom:33%;" />

这样便设置完成了。

如果能在Mac端的surge内看到这个设备的流量便说明代理成功了。

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/CleanShot 2021-03-20 at 12.14.05@2x.png" alt="CleanShot 2021-03-20 at 12.14.05@2x" style="zoom:50%;" />



## 那么要是设备数量太多怎么办？

这时候就可以让Mac端surge作为DHCP server来代理内网内的所有设备。

[watch this vedio for more](https://www.youtube.com/watch?v=i4VEz9UltQE&t=923s)

## 另外Surge for IOS 也能提供为其他设备代理的功能

只需要和安装了surge的设备连接在同一Wi-Fi下，打开无线设置->Config Proxy，然后填入ios surge内的ip和port就🉑️

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0909.PNG" alt="IMG_0909" style="zoom:33%;" />

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0910.PNG" style="zoom:33%;" />

<img src="/Users/qyq/Library/Mobile Documents/com~apple~CloudDocs/Development/My_Blog/_posts/2021-3-20-Surge for Mac as Gateway.assets/IMG_0911.PNG" style="zoom:33%;" />

