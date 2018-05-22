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

## Analysis visualization

![behaviortype](../pictures/behaviortype.png)

![behaviortypeday](../pictures/behaviortypeday.png)

![CTR](../pictures/CTR.png)


## Transformation

1. divide behaviortype into 4 parts and group by user_id or item_id

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

![user_behavior](../pictures/buser.jpg)

![user_behaviorrandom](../pictures/buserrandom.png)

## Regulation based on analysis
- 1.the product people add to shoppingcart last day have higher probability being purchased.





## Model_selection


## Problems
1. how tp print a figure include9000item
