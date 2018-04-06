---
layout: post
title:  "Matplotlib"
date:   2018-01-26 18:43:31 +0800
categories: jekyll update
---
if you use python3 in ubuntun ,you should put`%matplotlib inline` ,then it could display figure.

## Basic Plots with Matplotlib
- The general syntax is`import package.subpackage as local_name.`such as `import matplotlib.pyplot as plt `
- `plt.plot(a, b)`  `plt.xscale(log)` on a logarithmic scale
- `plt.show()` to display the plot
- `plt.clf()` clean and start again

### Histograms
`df.asymmetry.plot.hist(title='',bins=n)`plots a histogram of the list named x `plt.hist(x)`
### 2D scatter
`df.plot.scatter(x='',y='')`
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

## Figure AND subplot
- create a new figure `fig = plt.figure()`
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

## Seaborn
[Seaborn](https://blog.csdn.net/cymy001/article/details/78423920)

## Additional reeding
[size image and source code](https://matplotlib.org/1.5.1/gallery.html)
[flowingdata](http://flowingdata.com/category/tutorials/)
