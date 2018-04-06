---
layout: post
title:  "How to put website online"
date:   2018-01-16 18:43:31 +0800
categories: jekyll update
---
### How DNS works
- [Inside the Domain Name System](https://www.youtube.com/watch?v=GlZC4Jwf3xQ)
- [An Introduction to DNS Terminology, Components, and Concepts](https://www.digitalocean.com/community/tutorials/an-introduction-to-dns-terminology-components-and-concepts)
- [Public DNS](https://segmentfault.com/a/1190000004607227)

### Purchase a domain name from godaddy
- Change domain's IP address on the DNS management page.
- modify record type A to your desired ip address

### Install Nginx
```
apt-get update
apt-get install nginx
service nginx stop
service nginx start
mkdir /srv/www /srv/www/colinmc.me
```
- Configure nginx to serve files from that directory.
- Open `/etc/nginx/sites-available/default` in your favorite text editor and update the line with the root directive such that it looks as follows: `root /srv/www/colinmc.me;`

```
service nginx restart
```

- [How do I put up a simple, static website?](https://www.digitalocean.com/community/questions/how-do-i-put-up-a-simple-static-website)

- [How To Install Nginx on Ubuntu 14.04 LTS](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-14-04-lts)

![cat](/imgs/cat.jpg)

### Install FileZilla
Choose SFTP - Secure File Transfer Protocol (Linux)!
Port 22
If this port can not connect server,use other port such as 27292 etc.
