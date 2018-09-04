---
layout: post
title:  "How to use linux terminal"
date:   2018-01-14 18:43:31 +0800
categories: jekyll update
---

## Basic command
- list files `ls`
- `find / -name FILENAME` ingnore case `-iname FILENAME`
- autocomplete filename `TAB`+`FILENAME`
- change directory `cd FOLDER`; go to root directory `cd /`; go up a level `cd..`; go to current folder `cd .`
- creat an empty file `touch FILE`
- edit file `nano FILE`
- previous commands up/down arrows, `history`
- clear the screen `clear`
- rename a file `mv NAME_A NAME_B`

```
mv jdata_user_action1.csv /home/zhen/Desktop/jdata.csv
```
rename or move file1 to file2
if file2 is an existing directory, moves file1 into
directory file2

- remove a file `rm FILE`
- make directory `mkdir FOLDERNAME`
- remove directory `rm -r FOLDERNAME`
- `watch sensor` look CPU temperature
- chmod 1 execute only 2 write only 4 read only  ugo
u-owner g-group o-others
- chown an abbreviation of change owner
 - [chown command](http://www.cnblogs.com/peida/archive/2012/12/04/2800684.html)
- `less` can preview


## Install package

- `apt-get update` and `apt-get install APP`

update chrome

```
sudo apt-get update
sudo apt-get install -y google-chrome-stable
```


- install atom `sudo snap install atom --classic`

- Convert PDF into text
 - `sudo apt-get install ocrmypdf` install ocrmypdf
 - `apt-get install tesseract-ocr-chi-sim`install chinese simplified language
 - `sudo ocrmypdf --force-ocr -l chi_sim 数据挖掘与数据化运营实战++思路、方法、技巧与应用.pdf out.pdf`
 - `ocrmypdf --help`


- convert jpg to gif
 - `sudo apt-get install imagemagick`
 - `convert -delay 20 -loop 0 *.png example.gif`

## Editor

- nano editor
  `CTRL`+`O` write out `CTRL`+`X`exit

- vim editor
  - `ESC` + `:` + `q` exit
  - `i` before write
  - `ESC` + `:` + `Wq` save


## Another reading
- [linux terminal cheat sheet](https://files.fosswire.com/2007/08/fwunixref.pdf)
- [explainshell commands](explainshell.com)


### Markdown
  - [markdown cheatsheet1](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

  - [markdown cheatsheet2](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)

## Problems
- when open my laptop ,it access to old system

 - solution:
press shift before restart ,and UNIF to bios
