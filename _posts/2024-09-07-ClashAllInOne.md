---
layout: post
title: C919 All in One for Clash Verge 使用指南
description: Clash Verge：一款功能强大的代理工具
date: 2024-09-07
tags: Clash VPN 代理
categories: QyQ-Tech 网络工具
---
<swiper-container keyboard="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true" rewind="true">
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/ClashConfig/1.jpg" title="导入配置步骤" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/ClashConfig/2.jpg" title="节点选择界面" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/ClashConfig/3.jpg" title="测试节点延迟" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/ClashConfig/4.jpg" title="编辑规则" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/ClashConfig/5.jpg" title="添加自定义规则" class="img-fluid rounded z-depth-1" %}</swiper-slide>
</swiper-container>
<div class="caption">
    Clash Verge 使用指南图示
</div>

# 导入配置

订阅地址请联系管理员或在通知群中获取。获取后，将其粘贴至 Clash Verge（后称 Clash）软件的 **订阅** 部分：

1. 在 `订阅① - 订阅地址框②` 中粘贴订阅地址。
2. 点击 `导入③`，在下方导入我们提供的配置文件④。
3. 点击更新按钮⑤可更新配置文件。

# 节点选择

选中配置文件后，将 Clash 切换到 **代理** 菜单栏。**代理** 分为三种模式 ⓪：

- **规则**：使用已配置好的规则进行代理（如 bilibili 不翻墙，YouTube 要翻墙）。
- **全局**：所有流量都走代理（翻墙）。
- **直连**：所有流量都不走代理（不翻墙）。

在 **规则** 模式下，可以看到我们提供的 **策略组① ② ③ ④ ⑤ ⑥**。每个策略组中可以包含节点或别的策略组。例如：

- `YouTube 策略组` 选择 `Hightraffic`
- `Hightraffic` 选择 `Hightraffic-sanmao`
- `Hightraffic-sanmao` 选择 `香港-01`

则 `YouTube 策略组` 的流量会顺着策略组走 `香港-01` 节点。YouTube 网站已经由预先配置好的规则作为 `YouTube 策略组`，因此可以实现正常访问 YouTube。

## 注意

我们目前订购了三家机场的服务，分别是 FASTLink、Sanmao、CF。具体说明如下：

- **FASTLink** 的节点存在于 `Proxy` 策略组中。
- **Sanmao** 和 **CF** 的节点存在于带有关键词 `Hightraffic` 的策略组中。

**FASTLink** 节点速度好但价格较高，其余两个服务的性价比更高。因此我们推荐：

- 非视频网站使用 **FASTLink** 节点。
- 视频网站使用 **Sanmao** 或 **CF** 节点。

（目前配置文件只允许国外视频网站使用 Sanmao 或 CF）

# 开始使用

在 Clash 软件中，打开 **设置 - 系统设置 - 系统代理** 开关，即可开始使用代理。

# Q&A

> **1. 订阅地址导入、更新失败怎么办？**

1. 请检查订阅地址是否正确。
2. 请检查网络是否正常：将订阅地址复制到浏览器中打开，若能下载则是 Clash 软件问题，可以尝试重启软件或设备；若不能下载检查网络正常之后请联系管理员。

> **2. 为什么国外网页打开很慢？**

1. 请根据网页的 URL 地址确定策略组，如 `youtube.com` 是 `YouTube 策略组`，`microsoft.com` 是 `Microsoft 策略组`。没有直接对应策略组的国外网站一般在 `Proxy` 策略组中。
2. 请根据策略组选择合适的节点。如 `youtube.com` 访问慢、卡顿，请在 `YouTube 策略组` 中：
   - 点击 **更改测试链接按钮①**。
   - 在链接框②中填写 YouTube 网址。
   - 点击 **测试按钮③**，查看各个节点的延迟，选择延迟合适的节点即可。

> **3. 如何自定义规则，如 bilibili 走代理？**

1. 在 **订阅** 中找到想修改的配置文件，右键，点击 **编辑规则**。

2. 在弹出的窗口中，选择：

   - **规则类型**：`DOMAIN-SUFFIX`
   - **规则内容**：`bilibili.com`
   - **代理策略**：选择 `Hightraffic`

   点击 **保存** 后，`bilibili.com` 的流量会走 `Hightraffic 策略组`，该策略组会根据选择好的节点走代理。

在 **规则类型** 中，还可以选择：

- `DOMAIN`：精确匹配域名。
- `DOMAIN-SUFFIX`：匹配域名后缀。
- `DOMAIN-KEYWORD`：匹配域名关键词。
- `GEOIP`：根据地理位置匹配。
- `IP-CIDR`：根据 IP 地址段匹配。
- `PROCESS-NAME`：根据进程名匹配。

在 **代理策略** 中，可以选择：

- `DIRECT`：直连，不走代理。
- `REJECT`：拒绝访问。
- `PASS`：跳过，不经过 Clash 代理处理，直接连接网络。

也可以选择配置文件中的策略组，例如 `Proxy`、`Hightraffic`、`YouTube` 等，这些策略组会根据设置好的节点走代理。

> **4. 电脑没网了？**

一般是因为在Clash中开启了系统代理，这会修改电脑的网络连接的代理设置，但是Clash软件没有开启。请打开Clash软件，或者在电脑的系统设置里面关闭系统代理。

否则，请重启Clash软件，或者重启电脑。