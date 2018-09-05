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
### shadowsocks-ng for Mac OS
- [tutorial (old vs new version of client, system vs socks5 proxy)](https://lvii.gitbooks.io/outman/content/ss.mac.html)
- check [md5 and sha1](https://github.com/notpeter/apple-installer-checksums/blob/master/xcode.md)
`md5 whatever.dmg` and `shasum whatever.dmg`

### [ssh as socks proxy](http://www.pchou.info/linux/2015/11/01/ssh-tunnel.html)

```bash
ssh -D 7001 username@remote-host
```

### terminal proxy settings on Mac OS
- [install brew](http://brew.sh)
- [proxychains](https://github.com/shadowsocks/shadowsocks/wiki/Using-Shadowsocks-with-Command-Line-Tools)
- [issues regarding SIP(System Integrity Protection)](https://github.com/rofl0r/proxychains-ng/issues/78)
- [solution-disable SIP](http://gaocegege.com/Blog/随笔/shadowsocks-with-terminal)
- [more reading about SIP](https://www.zhihu.com/question/31116473)
- proxychains for google chrome on Ubuntu `proxychains google-chrome`

### proxy setting for curl and git commands
- proxy for terminal: configure `export ALL_PROXY=socks5://127.0.0.1:1080
` in `.bashrc` or `.zshrc` and then `source ~/.bashrc
`
- [curl](http://stackoverflow.com/questions/24568788/doing-https-requests-through-a-socks5-proxy-tor-with-curl)  ```curl --socks5-hostname localhost:1080 ip.gs``` (more options```curl -h```)
- git[[1]](https://segmentfault.com/q/1010000000118837)[[2]](http://cms-sw.github.io/tutorial-proxy.html)

### proxifiers really makes life easier (true global proxy for all applications)
- [Comparison of proxifiers](https://en.wikipedia.org/wiki/Comparison_of_proxifiers)
- [proxifier for both windows and MacOS](http://www.proxifier.com/)
- [guides](https://www.echoteen.com/proxifier-newway.html)


### useful tips for network
- one line http server ```python -m SimpleHTTPServer 8000```
- one line ftp server ```python -m pyftpdlib```
