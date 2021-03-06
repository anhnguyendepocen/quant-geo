---
title: "Problem Set #1"
author: "Your Name"
date: September 4, 2018
output: 
  html_document:
    keep_md: true
---

Due Date: September 11, 2018

Total Points: 21

**1** Use the `mpg` data frame in the **ggplot2** package to create a scatter plot showing how fuel consumption in cars during highway driving depends on engine fuel displacement (liters). Hint: let the horizontal axis (`x = `) be the variable `displ` and the vertical axis (`y = `) be the variable `hwy`. (6)


```r
library(ggplot2)
ggplot(mpg, aes(x = displ, y = hwy)) +
  geom_point()
```

![](PS1_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

**2** Remake the scatter plot by adding color to the points conditional on the number of cylinders (`cyl`). Hint: include `color = cyl` as an aesthetic. (3)

**3** Assign to an object `x` the sum of 3 and 5. Find the square root of the sum. (4)

**4** Create a vector `h` containing the following integers: 2 4 0 3 1 0 0 1 2 0. Create a table showing the count frequencies (e.g., the number of 0's, 1's, etc in the vector). Hint: use the `table()` function. (4)

**5** Find the mean and median values for the set of integers assigned to vector `h` in question **4**. (4)


