---
layout: post
title:  "Matplotlib"
date:   2018-01-26 18:43:31 +0800
categories: jekyll update
---

-1.Basic Plots with Matplotlib
 * i.The general syntax is`import package.subpackage as local_name.`such as `import matplotlib.pyplot as plt `
 * ii. `plt.plot(a, b)` `plt.scatter()` `plt.xscale(log)` on a logarithmic scale `plt.show()` to display the plot
- 2.Histograms`plt.hist(values,bins=n)`plots a histogram of the list named x `plt.hist(x)`
 `plt.clf()` clean and start again
- 3.Customization
 * i. `plt.xlabel('')` `plt.title('')` `plt.ytick([0,2,4,6,8,10])` means start from 0 up to 10
 how to combine theses
 * ii. `fill_between() `  build a line plot where the area under the graph is colored.
 * iii.  `plt.scatter(alpha = n, ,)`. Alpha can be set from zero to one, where 0 totally transparant, and 1 is not transparant.
 * iiii. Add `plt.grid(True)` after the `plt.text()`calls so that gridlines are drawn on the plot.



## Additional reeding
[size image and source code](https://matplotlib.org/1.5.1/gallery.html)
