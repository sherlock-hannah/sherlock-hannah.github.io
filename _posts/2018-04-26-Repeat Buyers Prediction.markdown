---
layout: post
title:  "Repeat Buyers Prediction"
date:   2018-04-27 18:43:31 +0800
categories: jekyll update
---
## Decription
predict the probability that these new buyers would purchase items from the same merchants again within 6 months
## Data
TABLE1. statistics of training and testing data

|data  | users |merchants|pairs |positive pairs|positive%|
| :--- | :---- |:----    |:---- |:----         |:----    |
|train |212062 |1993     |260864|     15952    |6.1151%  |
|test  |212108 |1993     |261477|

Table 2: Statistics of log activity data

|rows|users|merchants|items|categories|brands|
| :---| :---- |:----|:---- |:----|:----|
|54925330 |424170| 4995 |1090390| 1658|8444|


Table 3: Statistics of action types

|click   | add-to-cart |purchase        |add-to-favourite |
| :---   | :----       |:----    |:---- |
|48550713|3292144      |3005723(0.054724)|76750(0.001397)|

item id is the id of the item
bought by the user from the merchant on the Double 11 day,

## Feature engnieering
user-related features, merchant-related features
and user-merchant interactive features




1. divide action_type into three parts:clicks/add to carts, purchases, add-to-favourite
groupby user_id and merchant_id
and out into file user_action
2. use sql join train and user_action on user_id
3. extract the action_type when day == 1111


## Visualization




## Model Training




## Reference
[Repeat Buyers Prediction after Sales Promotion for Tmall Platform
](http://shichuan.org/doc/23.pdf)
