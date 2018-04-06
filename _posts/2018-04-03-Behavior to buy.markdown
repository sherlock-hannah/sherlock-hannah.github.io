---
layout: post
title:  "Behavior to buy"
date:   2018-04-03 18:43:31 +0800
categories: jekyll update
---
## Description
Predicting whether customer purchase products in 18.Dec according to their behavior last month.

## Data

| variable     | description                      |  
| :------------| :-------------                   |
| user_id      | int64       20000users           |
| item_id      | int64 tableuser4758484 item422858|
| behavior_type|1(browse)2(Collect)3(cart)4(buy)  |
| user_geohash | user location                    |
| item_geohash | item location                    |
| time         | precise to hour                  |
| item_category| int64                            |


## Goal
Set a model and output a table(the prediction of users buying products in 18.Dec) include two columns user_id and item_id.

## Metric
![F1](../pictures/F1.png)

## Analysis

![behaviortype](../pictures/behaviortype.png)

![behaviortypeday](../pictures/behaviortypeday.png)

![CTR](../pictures/CTR.png)
