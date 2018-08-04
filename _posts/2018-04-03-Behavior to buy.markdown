---
layout: post
title:  "Behavior to buy"
date:   2018-04-03 18:43:31 +0800
categories: jekyll update
---
## Description
Predicting whether customer purchase products in 18.Dec according to their behavior last month.
- U——users set
- I——product set
- P——product subset，P ⊆ I
- D——U to I behavior dataset
- our goal is using D to construct a recommend model of uers of U to product of P.

## Data

| variable     | description                      |  
| :------------| :-------------                   |
| user_id      | int64                            |
| item_id      | int64                            |
| behavior_type|1(browse)2(Collect)3(cart)4(buy)  |
| user_geohash | user location (include NAN)      |
| item_geohash | item location                    |
| time         | precise to hour                  |
| item_category| int64                            |

D dataset
- records:23291027
- user_id:20000
- item_id:4758484
- item_category:9557
- User_item pair:23291027 and purchased pair: 232579 CTR=0.0099857
- min time:2014-11-18 00 max time:2014-12-18 00

P dataset
- item_id:422858
- item_category:1054

## Goal
Set a model and output a table(the prediction of users buying products in 18.Dec) include two columns user_id and item_id.

## Metric
![F1](../pictures/F1.png)

## Feature engnieering
1. user feature
2. item feature
3. Category feature
4. user-item
5. item-category
6. user-cstegory

Cross feature

![BTB](../pictures/BTBfeature.JPG)

time series cut:


different behavior add by timing different value group by user or item


details:
![BTB](../pictures/BTBfe1.png)
![BTB](../pictures/BTBfe2.png)
![BTB](../pictures/BTBfe3.png)





## Sampling
using user interactive data which date is the day before predictted day.

## Transformation

1. divide behaviortype into 4 parts and group by user_id or item_id

`user_item_count = pd.crosstab([data.user_id,data.item_id],data.behavior_type)
`
2. the relationship between when user add product to shoppingcart and purchasedd

3. x0 how many times user click this product
   x1 did user add this product to shoppingcart
   x2 did user buy this product within one week

4. the latest day users action

5. the time interval between other action_type and purchase

6. the relationship between the times of other action_type and purchase of different item


## Analysis

![behaviortype](../pictures/behaviortype.png)

![behaviortypeday](../pictures/behaviortypeday.png)

![CTR](../pictures/CTR.png)

![CTR](../pictures/user_ctr.png)

![time_interval](../pictures/buserrandom.png)




## Regulation based on analysis
1. the product people add to shoppingcart last day have higher probability being purchased.





## Model_selection
- XGBoost


- [basic_LogisticRegression](https://mr-rxz.github.io/%E6%BA%90%E7%A0%81%E8%A7%A3%E8%AF%BB/2016/08/16/%E6%BA%90%E7%A0%81%E8%A7%A3%E8%AF%BB-1-%E5%A4%A9%E6%B1%A0%E7%A7%BB%E5%8A%A8%E6%8E%A8%E8%8D%90%E7%AE%97%E6%B3%95%E7%AB%9E%E8%B5%9B.html)
















## Problems
1. how to print a figure include 9000 item


## Additional reading
- [summary of ALI recommend algorithm ](https://blog.csdn.net/u014374284/article/details/49933487)
- [competition thought](https://blog.csdn.net/Bryan__/article/details/51713596)
