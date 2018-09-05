---
layout: post
title:  "set up proxy for your working environment"
date:   2018-09-04 18:43:31 +0800
categories: jekyll update
---

### Ubuntu shadowsocks-qt5 and proxichains
- shadowsocks-qt5
```
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```
- shadowsocks command lines

  install package by `sudo apt install shadowsocks`, and configure file `sudo vi /etc/shadowsocks.json`, with the format
  ```
  {
"server":"server-ip",
"server_port":8000,
"local_address": "127.0.0.1",
"local_port":1080,
"password":"your-password",
"timeout":600,
"method":"aes-256-cfb"
}
```
run on the background `sudo sslocal -c /etc/shadowsocks.json -d start`, to enable auto start on boot, edit `sudo vi /etc/rc.local
`, with the format
```
#!/bin/sh -e
sudo sslocal -c /etc/shadowsocks.json -d start
exit 0
```
then make your file executable `sudo chmod 755 /etc/rc.local`

- proxychains
```
sudo apt-get install proxychains
sudo nano /etc/proxychains.conf
Change the following line :
socks4 127.0.0.1 9050
To :
socks5 127.0.0.1 9050
```
### tutorials of v2ray,[     [1]](https://toutyrater.github.io/basic/vmess.html)[ [2]](https://www.v2ray.com/)
