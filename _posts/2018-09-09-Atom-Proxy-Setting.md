---
layout: post
title: Atom-Proxy-Setting
date: 2018-09-09 11:59:16
tags: Atom
comment: true
---

# Atom 设置和取消代理
## 设置Shadowsocks代理
```
apm config set http-proxy socks5:127.0.0.1:1080
apm config set https-proxy socks5:127.0.0.1:1080
```
## 取消ssl
```
apm config set strict-ssl false
```
## 取消代理
```
apm config set http-proxy null
apm config set https-proxy null
```
## 查看代理设置
```
apm config get http-proxy
apm config get https-proxy
```
