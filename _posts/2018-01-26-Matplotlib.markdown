---
layout: post
title:  "Matplotlib"
date:   2018-01-26 18:43:31 +0800
categories: jekyll update
---

if you use python3 in ubuntu ,you should put`%matplotlib inline` ,then it could display figure.


## Basic Plots with Matplotlib

- The general syntax is`import package.subpackage as local_name.`such as `import matplotlib.pyplot as plt `
- `plt.plot(a, b)`  `plt.xscale(log)` on a logarithmic scale
- `plt.show()` to display the plot
- `plt.clf()` clean and start again

### Series.plot
`series.plot(kind='line',xlim=[0,10])`

xlim : limit of x axis
ylim: limit of y axis

### Histograms
`df.asymmetry.plot.hist(title='',bins=n)`plots a histogram of the list named x `plt.hist(x)`

add subplot
```
train1 = train.drop(['id'],axis =1)
trainpair = train1.fillna(-1)
fig = plt.figure(figsize=(14,14))
for i in range(1,101):
    axi = fig.add_subplot(10,10,i)
    trainpairi = trainpair.iloc[:,i]
    axi.hist(trainpairi)

```

```
f, ax = plt.subplots(1, 4, figsize=(14,6))
ax[0].set_title('May')
ax[1].set_title('June')
ax[2].set_title('July')
ax[3].set_title('August')

user_order_cate_first.loc[user_order_cate_first['o_month']==5,'o_day'].plot(kind='hist',ax = ax[0])
user_order_cate_first.loc[user_order_cate_first['o_month']==6,'o_day'].plot(kind='hist',ax = ax[1])
user_order_cate_first.loc[user_order_cate_first['o_month']==7,'o_day'].plot(kind='hist',ax = ax[2])
user_order_cate_first.loc[user_order_cate_first['o_month']==8,'o_day'].plot(kind='hist',ax = ax[3])
```




### 2D scatter
Agraphical presentation of the relationship between two quantitative variables.

`df.plot.scatter(x='',y='')`

```
N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)
area = np.pi * (15 * np.random.rand(N))**2  # 0 to 15 point radii

plt.scatter(x, y, s=area, c=colors, alpha=0.5)
plt.show()

```

### 3D scatter plot
```
from mpl_toolkits.mplot3d import Axes3D`
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.set_xlabel('Final Grade')
ax.set_ylabel('First Grade')
ax.set_zlabel('Daily Alcohol')
ax.scatter(student_dataset.G1, student_dataset.G3,student_dataset['Dalc'], c='r', marker='.')
plt.show()
```
then if you want to spin 3D scatter plot,you can install pyqt5
`pip install pyqt5`
`%matplotlib qt5`

### Boxplot
`plt.boxplot()`

### Bar
`df.plot(kind = 'bar' or 'barh',stacked = True or False )`

`plt.bar(np.arrage(n),data,tick_label=[,])`

[different type of bar](https://zhuanlan.zhihu.com/p/25128216)
ex:
```
plt.figure(figsize=(20,14))
plt.bar(range(len(df.index)), df.iloc[:,0], label='isnull',fc = 'b')
plt.bar(range(len(df.index)), df.iloc[:,1], label='null',tick_label = df.index,fc = 'r')
plt.legend()
plt.show()
```

### Treemap
`import squarify`
`squarify.plot(sizes=data, label=data.index,color=colors)`
[Treemap](https://python-graph-gallery.com/202-treemap-with-colors-mapped-on-values/)

## Figure and subplot
- create a new figure `fig = plt.figure(figsize=(,))`
- add subplot `ax1 = fig.add_subplot(2,2,1)`
(2,2)means this figure is 2*2 and 1 is the first figure


## Customization
- `plt.xlabel('')` `plt.title('')` `plt.ytick([0,2,4,6,8,10])` means start from 0 up to 10
```
pclass.set_xlabel('Pclass')
pclass.set_title('population distribution of different class')
pclass.set_xticks([1,2,3])
pclass.set_xticklabels(['upper','middle','lower'])
```
- `fill_between() `  build a line plot where the area under the graph is colored.
- `plt.scatter(alpha = n, ,)`. Alpha can be set from zero to one, where 0 totally transparant, and 1 is not transparant
- Add `plt.grid(True)` after the `plt.text()`calls so that gridlines are drawn on the plot.
















## Additional reeding
- [size image and source code](https://matplotlib.org/1.5.1/gallery.html)
- [flowingdata](http://flowingdata.com/category/tutorials/)
- [python-graph-gallery](https://python-graph-gallery.com/)
