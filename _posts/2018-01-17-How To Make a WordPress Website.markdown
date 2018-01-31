---
layout: post
title:  "How To Make a WordPress Website"
date:   2018-01-17 18:43:31 +0800
categories: jekyll update
---
- [Initial Server Setup with Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04#step-four-%E2%80%94-add-public-key-authentication-(recommended))
```
local$ ssh root@SERVER_IP_ADDRESS
adduser demo
gpasswd -a demo sudo
```
- [How To Install Linux, Apache, MySQL, PHP (LAMP) stack on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04)

- [How To Install Wordpress on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-14-04)


- [How To Configure Secure Updates and Installations in WordPress on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu)

## Problems and Solutions
### Public Key Authentication
generate a key pair
`local$ ssh-keygen`
mannally copy the public key
```
su - demo
mkdir .ssh
chmod 700 .ssh
nano .ssh/authorized_keys
chmod 600 .ssh/authorized_keys`
```

[detail](https://github.com/zhenfisher/web/blob/master/_posts/2018-1-10-SSH.md)

### Wordpress:unable to update and upload
- Unable to create directory wp-content/uploads/2018/01. Is its parent directory writable by the server?
- 1. Tips:![It is important that you request unique values each time. Do NOT copy the values shown below!](/imgs/tips.jpg)
- 2.`chown -Rf www-data:www-data /var/www`
- 3. `sudo nano /etc/php5/apache2/php.ini`
change `post_max_size` in php.ini

     ```
     Maximum allowed size for uploaded files.
upload_max_filesize = 40M**;
     Must be greater than or equal to upload_max_filesize
post_max_size = 40M**
     ```
[Wordpress unable to upload and install theme](https://www.digitalocean.com/community/questions/wordpress-unable-to-upload-and-install-theme)
