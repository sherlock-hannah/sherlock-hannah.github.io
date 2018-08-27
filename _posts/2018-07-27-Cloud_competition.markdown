---
layout: post
title:  "Cloud_competition"
date:   2018-07-27 18:43:31 +0800
categories: jekyll update
---
[DataStudio](https://ide2-cn-shanghai.data.aliyun.com/)

# Nowcasting problems

- [Nowcasting (meteorology)](https://en.wikipedia.org/wiki/Nowcasting_(meteorology))
- [Convolutional LSTM Network: A Machine Learning Approach for Precipitation Nowcasting](https://arxiv.org/abs/1506.04214)





# Metrics
to do:
offline measure

transform it to multi_class question

# Data Preprocessing
1. create new feature x_y,concat by x,y.
2. calculate mobile mean of predicted value by different member
3. Add mobile STDEV but the score is 0.06
n
to do :
1. create new feature by x,y geography feature and time feature by sample_id
2. how to select useful feature

## Imbalanced Classes

- [Dealing with Imbalanced Classes in Machine Learning](https://towardsdatascience.com/dealing-with-imbalanced-classes-in-machine-learning-d43d6fa19d2)

## Table operations in pandas
- [Cross join / cartesian product between pandas DataFrames](https://mkonrad.net/2016/04/16/cross-join--cartesian-product-between-pandas-dataframes.html)
  ```python
  def df_crossjoin(df1, df2, **kwargs):
    df1['_tmpkey'] = 1
    df2['_tmpkey'] = 1

    res = pd.merge(df1, df2, on='_tmpkey', **kwargs).drop('_tmpkey', axis=1)
    res.index = pd.MultiIndex.from_product((df1.index, df2.index))

    df1.drop('_tmpkey', axis=1, inplace=True)
    df2.drop('_tmpkey', axis=1, inplace=True)

    return res
  ```

- [Update a dataframe in pandas while iterating row by row](https://stackoverflow.com/questions/23330654/update-a-dataframe-in-pandas-while-iterating-row-by-row)

- Hierarchical Indexing
  1. [A demonstration of simple uses of MultiIndex](https://www.somebits.com/~nelson/pandas-multiindex-slice-demo.html)
  2. [Hierarchical Indexing](https://jakevdp.github.io/PythonDataScienceHandbook/03.05-hierarchical-indexing.html)
  3. [Turn Pandas Multi-Index into column](https://stackoverflow.com/questions/20110170/turn-pandas-multi-index-into-column)
  `df.reset_index(inplace=True)`



- Pivot table
  1. [How to pivot a dataframe](https://stackoverflow.com/questions/47152691/how-to-pivot-a-dataframe?noredirect=1&lq=1)
  2. [Reshaping and Pivot Tables](https://pandas.pydata.org/pandas-docs/stable/reshaping.html)
  3. [pandas pivot table to data frame](https://stackoverflow.com/questions/42708193/pandas-pivot-table-to-data-frame/42708606)
  4. [Pandas - Convert columns to new rows after groupby](https://stackoverflow.com/questions/47849364/pandas-convert-columns-to-new-rows-after-groupby)




# Model

1. linear_regression
2. gbdt_regression
3. ps-smart
4. random_forest multi class  
5. naive bayes classification

# App
1. write api
   - [example](https://help.aliyun.com/document_detail/87952.html)
   - [video](https://tianchi.aliyun.com/forum/videoStream.html?spm=5176.11409386.0.0.50ca1d071Xk1A1&postsId=9552#postsId=9552)
2. visualization
   - [bar](https://help.aliyun.com/document_detail/88519.html)

# Reference
- [solution](https://tianchi.aliyun.com/forum/new_articleDetail.html?spm=5176.8366600.0.0.762d311fPJr24s&raceId=231669&postsId=6065)

- [aliyun_document](https://help.aliyun.com/document_detail/42703.html?spm=a2c4g.11186623.6.563.rzwU4n#KV2Table)

- [PAI](https://tianchi.aliyun.com/forum/new_articleDetail.html?spm=5176.8366600.0.0.7837311fyoOSie&raceId=231596&postsId=1516)

- [Higher proficiency of sql](https://tianchi.aliyun.com/forum/new_articleDetail.html?spm=5176.9876270.0.0.4ce9e44awL7bHT&raceId=&postsId=2608)

- [react](https://reactjs.org/)
- [spring](https://spring.io/projects/spring-framework)
- [mybatis](http://www.mybatis.org/mybatis-3/)
- [java_basic](http://www.runoob.com/java/java-basic-datatypes.html)

# questions
1. what is oss
