---
layout: post
title:  "Jingdong_user_buy_time"
date:   2018-05-30 18:43:31 +0800
categories: jekyll update
---
## Description
predict users buy specified category item on which day

- 1.classification: user buy or not :0 not ,1 buy
- 2.regression : predict time of buy

## Metric
a = 0.4

![userdistribution](/pictures/s.png)

user metric

![userdistribution](/pictures/s1.png)

time metric

![userdistribution](/pictures/s2.png)



## Data
raw data:
1. item_info(item_id,price,category,parameter1,2,3)
2. user_info(user_id,age,gender,level)
3. user_action(user_id,item_id,action_date,action_types,action_times)
4. user_order(user_id,item_id,order_id,order_date,order_region,order_number)
5. user_comment(user_id,order_id,comment_date,comment_level)

Table1.Basic info of prediction data

|        | user_id|sku_id |a_date              |category|
| :------| :----- |:------| :---------         |:------ |
| predict| 50000> |37724  |2017/5/01-2017/5/30 |101,30 |
| all    | 98924  |99412  |2016/5/01-2017/4/30 |71,46,83, 101,1,30|


Table2.Basic info of users data

|age     |sex    |level |a_type |score |o_area|
| :----- | :---- |:---- |:----  |:----  |:---- |
|-1:unknown 1-6|0:male 1:female 2:secret | 1-5 |1:click 2:focus| 1:good 2:well 3:bad -1:null |1-30|

Table3.Statistics of users-buy data

|userscount   |mean   |std   |min |25 %|50%|75%|max  |
| :-----      | :---- |:---- |:---|:---|:--|:--|:--  |
|98924        |12     | 28   |1   |2   |6  |15 |3919 |


## pre_process
1. transfer datatype ,eg:object to datetime
2. examine duplicate `user_order.duplicated().value_counts()`
if exists ,then `user_order = user_order.drop_duplicates()`



## Visualization



Figure1.Users age,sex and level distribution

![userdistribution](/pictures/jduserdistribution.png)

Figure2.Relationship between time and buy,click,focus

![bcftmonth](/pictures/bcftmonth.png)

![bcftday](/pictures/bcftday.png)

Figure3.Time interval of repeat buy

![timeinterval](/pictures/timeinterval.png)
cate = 30
![timeinterval](/pictures/diff_30_jd.png)
cate = 101
![timeinterval](/pictures/diff_101_jd.png)





Figure4.The number of user of different order number

![order_number](/pictures/order_number.png)


Figure5.The number of different category of item

![cateitem](/pictures/cateitem.png)

Figure6.The number of purchased item in different area

![areabuy](/pictures/areabuy.png)

Figure7.The number of purchased item of different category

![cateitem](/pictures/201605cate.png)



Figure8.The price of purchased item of different category

![cateitem](/pictures/pricecate.png)

Figure9.Total number of users purchased per month

![monthuser](/pictures/monthuser.JPG)

Figure10.Comment hour in one day

![monthuser](/pictures/comment_hour_jd.png)

Figure11.The first order day in different month
![monthuser](/pictures/different_month_first_order_day.png)


8. label cate = 30,101  user buy  or not,and pearson feature correlation

## Regulation based on Visualization analysis
- outlier of  specified month such as 6,11,4 should be delete



## Feature engnieering
![RTBfeature](/pictures/RTBfeature.JPG)

### user feature
- rate of click to buy, focus to buy
- the sum of different behavior in recent day
- the active level in recent day
- dense rank



### item feature

### Category feature

### user-item
- repeat buyers

### item-category
- rank the most purchased item in category

### user-cstegory

### time feature
- weekday


## Model
- light bgm





## reference
- [video](https://jdata.jd.com/html/knowledge.html)
