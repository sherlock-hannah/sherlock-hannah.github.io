---
layout: post
title:  "SQLbasics"
date:   2018-02-07 18:43:31 +0800
categories: jekyll update
---
- GUI Tools:Navicat
- RDBMS: Relational Database Management System.
- API :Application Programming Interface
- Windows power shell:
 `mysql -uroot -p`
 `show databases;`
- create sql user:
 `grant all on databases name.* to "username"@"localhost" identified by "password"`
- show the structure of tables:
 `desc tablename;`
- insert data
 `insert into tablename (rowname1,name2) values("1",2);`
- create table 
 `create tablename(columnname1 type primary key,columnname2 type,columnname3 type ) ;`
