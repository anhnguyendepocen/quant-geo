---
title: "R and RStudio"
author: "James B. Elsner"
date: August 30, 2018
output: 
  html_document:
    keep_md: true
---

"**The role of the teacher is to create the conditions for invention rather than provide ready-made knowledge.**"---Seymour Papert

* After this lesson you will (1) know the basics of the R language, (2) be able to create a graph in R, (3) be able to mix R code and text in a markdown document, and (4) know how to generate HTML from an Rmd file.
* Everyone should have R and RStudio on a laptop with this `02-Lesson.Rmd` file opened in RStudio.

## Review 

### Grading

* Grades: Two exams each worth 40% and several (4-6) homework problem sets (20%).
* Exam Dates: First Exam: Thursday, October 4, Final Exam: Friday, December 14 (final exam week). No makeup exams.
* Exams and problems sets will be done with R markdown documents (Rmd files) and emailed to me (both the Rmd and HTML files). 
* Exams will be done without a proctor.
* Exams will be time restricted. 
* Exams will be available in an Rmd file through Canvas.

### Reproducible research

If your science is to be a convincing the trail from data to final output must be openly available. R and RStudio help you generate scientific reports that are a mixture of text and code. This makes it easy to create an understandable trail from hypothesis, to experimental design, to data, to analysis, to results. Reproducible research.

### Make a scatter plot

We will use the functions in the **ggplot2** package to make graphs. First download the package from a CRAN site. You can do this using the Package tab in the lower-right window pane or with the `install.packages()` function where the name of the package is in quotes inside the parentheses.

```r
install.packages("ggplot2")
```

Next make the functions from the **ggplot2** package available for this particular session.

```r
library(ggplot2)
```

The `install.packages()` function gets the package named **ggplot2** from CRAN and puts it on your computer. Then the `library()` function makes the package and all its functions available to your current R session. Only the `library()` function needs to be done every time you open RStudio.

Start with the `airquality` data frame in the **datasets** package that is loaded as part of the **base** R package. The data contains daily air quality measurements from a location in New York City between May and September 1973.

```r
head(airquality)
```

```
##   Ozone Solar.R Wind Temp Month Day
## 1    41     190  7.4   67     5   1
## 2    36     118  8.0   72     5   2
## 3    12     149 12.6   74     5   3
## 4    18     313 11.5   62     5   4
## 5    NA      NA 14.3   56     5   5
## 6    28      NA 14.9   66     5   6
```

```r
dim(airquality)
```

```
## [1] 153   6
```

The function `head()` lists the first six rows of the data along with the column names including contains ozone concentration (ppm), solar radiation, wind speed, temperature (F), month and day. The function `dim()` gives the number of rows (first number) and the number of columns in the data frame.

Question: Is ozone concentration higher on warmer days? You should look at your data before doing statistics. This involves making graphs. The most important scientific graph is the scatter plot. It involves plotting two variables in a two-dimensional cartesian plane defined by the values of the variables.

```r
ggplot(airquality, aes(x = Temp, y = Ozone)) + 
  geom_point()
```

```
## Warning: Removed 37 rows containing missing values (geom_point).
```

![](02-Lesson_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

Describe what you see. Why the warning?

Question: On average is ozone concentration higher on windy days? Create a graph to help you answer this question.

```r
ggplot(airquality, aes(x = Wind, y = Ozone)) + 
  geom_point()
```

```
## Warning: Removed 37 rows containing missing values (geom_point).
```

![](02-Lesson_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

The answer is no.

We can use a label instead of a dot for the locations in this two-dimensional scatterpolot by adding the `label` aesthetic and using `geom_text`. 

```r
ggplot(airquality, aes(x = Wind, y = Ozone, label = Ozone)) +
  geom_text()
```

```
## Warning: Removed 37 rows containing missing values (geom_text).
```

![](02-Lesson_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

Another example:

```r
ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width)) + 
  geom_point(aes(color = Species))
```

![](02-Lesson_files/figure-html/unnamed-chunk-7-1.png)<!-- -->

More about graphs next week.

## Turning in your problem sets (and exams) using R, RStudio, & knitr

You will submit your problem sets (and exams) to me through email. Email both the Rmd file with your answers and the HTML file the results from selecting the Knit tab.

1. Download the PSX.Rmd file from Campus under Assignments.
2. Use your last name and rename the file accordingly Lastname_PSX.Rmd
3. Open the file in RStudio: File > Open File
4. In the file replace 'Your Name' with your name.
5. Answer the questions by typing the code between the chunk markers.
6. Select the Knit button to generate the HTML.
7. Attach the HTML and Rmd files in an email (<jelsner@fsu.edu>) to me. Include a subject line (e.g. Assignment X).

## Finishing R

When you start RStudio the version number and name is printed and instructions on quitting. When you quit, RStudio will offer to save the current session. Saving your session is not usually necessary. You can type: `quit()` or select the red button in the upper-left corner of RStudio.

## Calculations

R evaluates commands typed at the prompt and returns the result to the screen. The prompt is the blue greater than symbol (`>`). To find the sum of the square root of 25 and 2, at the prompt type

```r
sqrt(25) + 2
```

```
## [1] 7
```

The number inside the brackets indexes the output. Here there is only one bit of output, the answer 7. The prompt that follows indicates R is ready for another command.

```r
12/3 - 5
```

```
## [1] -1
```

How would you calculate the 5th power of 2? How would you find the product of 10.3 & -2.9? How would you find the average of 8.3 and 10.2?

How about 4.5% of 12,000?

```r
.045 * 12000 
```

```
## [1] 540
```

## Functions

Many math and statistical functions are available. A function has a name followed by a pair of parentheses. Arguments are placed inside the parentheses as needed.

For example,

```r
sqrt(2)
```

```
## [1] 1.414214
```


```r
sin(pi)
```

```
## [1] 1.224647e-16
```

How do you interpret this output?  Type (highlight then click Run): .0000000000000001224647
Why not zero?

```r
exp(1)
```

```
## [1] 2.718282
```

```r
log(10)
```

```
## [1] 2.302585
```

Many functions have arguments with default values. For example, you only need to tell the random number generator `rnorm()` how many numbers to produce. The default mean is zero. To replace the default value, specify the corresponding argument name.

```r
rnorm(10)
```

```
##  [1]  1.1072955 -1.5492153 -0.7014626 -0.7521061  1.7681700  0.8263354
##  [7] -1.1105408 -0.6075719 -0.3469150 -0.5077580
```

```r
rnorm(10, mean = 5)
```

```
##  [1] 6.152260 5.529266 6.166859 6.258841 6.285107 6.641359 4.732451
##  [8] 4.775717 4.555507 5.191571
```

## Syntax is important

You get an error message when you type a function that R does not understand. For example:

```r
squareroot(2)
```
Error: could not find function "squareroot"


```r
sqrt 2
```
Error: syntax error


```r
sqrt(-2)
```

```
## Warning in sqrt(-2): NaNs produced
```

```
## [1] NaN
```


```r
sqrt(2
+
```

The last command shows what happens if R encounters a line that is not complete. The continuation prompt (`+`) is printed, indicating you did not finish the command.

## Saving an object

Use the assignment operatore to save an object. You put a name on the left-hand side of the left pointing arrow (`<-`) and the value on the right. Assignments do not produce output.

```r
x <- 2 
x + 3    
```

```
## [1] 5
```

```r
x <- 10
```

Here you assigned `x` to be a numeric object. Assignments are made using the left-pointing arrow (less than followed by a dash) [or an equal sign.]

## Object names

You are free to make object names out of letters, numbers, and the dot or underline characters.  A name starts with a letter or a dot (a leading dot may not be followed by a number). But you can't use mathematical operators, such as +, -, *, and /.

Some examples of names include:

```r
x <- 2
n <- 25
a.long.number <- 123456789
ASmallNumber <- .001
```

Case matters. `DF` is different than `df` or `Df`.

Some names are commonly used to represent certain types of data. For instance, `n` is for length; `x` or `y` are data vectors; and `i` and `j` are integers and indices.

These conventions are not forced, but consistent use of them makes it easier for you (and others) to understand what you've done.

## Getting and loading packages from CRAN

Lots of packages are available in R.  Packages are groups of functions that do specific tasks. To install and load a package from the R console, determine the name of the package (http://cran.r-project.org/).  Then type

```r
chooseCRANmirror()
```

Select a site, then if you're interested in the **UsingR** package, type

```r
install.packages("UsingR")
library("UsingR")
```

The first function retrieves the package from CRAN and installs it on your computer. The second makes the package available to your current R session (loads the function).  

When you restart R you will need to reload the package, but you will not need to re-install it. The function `require()` works much like `library()`. 

In RStudio you can use the Packages tab and the Install Packages link. The packages on your computer are listed alphabetically.  The check mark indicates they are available to your current session.

Install and load the **spgwr** package.

## Entering data

The `c()` function is useful for getting a small amount of data into R. The function combines (concatenates) items (elements). Example: consider a set of hypothetical annual land falling hurricane counts over a ten-year period.

2  3  0  3  1  0  0  1  2  1

To enter these into your environment, type

```r
counts <- c(2, 3, 0, 3, 1, 0, 0, 1, 2, 1)
counts
```

```
##  [1] 2 3 0 3 1 0 0 1 2 1
```

Notice a few things. You assigned the values to an object called counts. The assignment operator is an equal sign (`=`). Values do not print. They are assigned to an object name. They are printed by typing the object name as we did on the second line. Finally, the values when printed are prefaced with a `[1]`. This indicates that the object is a vector and the first entry in the vector is a value of 2 (The number immediately to the right of [1]). More on this later.

You can save some typing by using the arrow keys to retrieve previous commands.  Each command is stored in a history file and the up arrow key will move backwards through the history file and the down arrow forwards.  The left and right arrow keys will work as expected.
 
## Applying a function

Once the data are stored in an object, you use functions on them. R comes with all sorts of functions that you can apply to your counts data.

```r
sum(counts)         # total number of hurricanes making landfall
```

```
## [1] 13
```

```r
length(counts)      # length of the data vector
```

```
## [1] 10
```

```r
sum(counts)/length(counts)   # average number of hurricanes
```

```
## [1] 1.3
```

Other useful functions include, `sort()`, `min()`, `max()`, `range()`, `diff()`, and `cumsum()`.  Try these on the landfall counts.  What does `range()` do?  What does `diff()` do?

## Mean

The average (or mean) value of a set of numbers ($x$'s) is defined as:
$$
\bar x = \frac{x_1 + x_2 + \cdots + x_n}{n}
$$
The function `mean()` makes this calculation on your set of counts.

```r
mean(counts)
```

```
## [1] 1.3
```

## Data vectors

The count data is stored as a vector. R keeps track of the order that the data were entered. First element,second element, and so on. This is good for a couple of reasons. Here the data has a natural order - year 1, year 2, etc. You don't want to mix these. You would like to be able to make changes to the data item by item instead of entering the entire data again. Also vectors are math objects making them easy to manipulate.

Suppose `counts` contain the annual number of land-falling hurricanes from the first decade of a longer record. You want to keep track of counts over other decades. This could be done by the following, example.

```r
cD1 <- counts
cD2 <- c(0, 5, 4, 2, 3, 0, 3, 3, 2, 1) 
```
 
Note that you make a copy of the first decade of counts and save the vector using a different object name.

Most functions operate on each element of the data vector at the same time.

```r
cD1 + cD2
```

```
##  [1] 2 8 4 5 4 0 3 4 4 2
```

The first year of the first decade is added from the first year of the second decade and so on.

What happens if you apply the `c()` function to these two vectors?

```r
c(cD1, cD2)
```

```
##  [1] 2 3 0 3 1 0 0 1 2 1 0 5 4 2 3 0 3 3 2 1
```

If you are interested in each year's count as a difference from the decade mean, you type:

```r
cD1 - mean(cD1)
```

```
##  [1]  0.7  1.7 -1.3  1.7 -0.3 -1.3 -1.3 -0.3  0.7 -0.3
```

In this case a single number (the mean of the first decade) is subtracted from each element of the vector of counts.

This is an example of data recycling. R repeats values from one vector so that its length matches the other vector. Here the mean is repeated 10 times.

## Variance

Suppose you are interested in the variance of the set of landfall counts. The formula is given by:
$$
\hbox{var}(x) = \frac{(x_1 - \bar x)^2 + (x_2 - \bar x)^2 + \cdots + (x_n - \bar x)^2}{n-1}
$$

Note: The formula is given as LaTeX math code with the double dollar signs starting (and ending) the math mode. It's a bit hard to read but it translates exactly to math as you would read it in a scientific article or textbook. Look at the HTML file.

Although the `var()` function will compute this for you, here you see how you could do this directly using the vectorization of functions. The key is to find the squared differences and then add up the values.

The key is to find the squared differences and then add them up.

```r
x <- cD1
xbar <- mean(x)
x - xbar
```

```
##  [1]  0.7  1.7 -1.3  1.7 -0.3 -1.3 -1.3 -0.3  0.7 -0.3
```

```r
(x - xbar)^2
```

```
##  [1] 0.49 2.89 1.69 2.89 0.09 1.69 1.69 0.09 0.49 0.09
```

```r
sum((x - xbar)^2)
```

```
## [1] 12.1
```

```r
n <- length(x)
n
```

```
## [1] 10
```

```r
sum((x - xbar)^2)/(n - 1)
```

```
## [1] 1.344444
```

To verify type

```r
var(x)
```

```
## [1] 1.344444
```

## Data vectors have a type

One restriction on data vectors is that all the values have the same type. This can be numeric, as in counts, character strings, as in

```r
simpsons <- c("Homer", "Marge", "Bart", "Lisa", "Maggie")
simpsons
```

```
## [1] "Homer"  "Marge"  "Bart"   "Lisa"   "Maggie"
```

Note that character strings are made with matching quotes, either double, ", or single, '.

If you mix the type within a data vector, the data will be coerced into a common type, which is usually a character.  Arithmetic operations do not work on characters.

Returning to the land falling hurricane counts.

```r
cD1 <- c(2, 3, 0, 3, 1, 0, 0, 1, 2, 1)   
cD2 <- c(0, 5, 4, 2, 3, 0, 3, 3, 2, 1)
```

Now suppose the National Hurricane Center (NHC) reanalyzes a storm, and that the 6th year of the 2nd decade is a 1 rather than a 0 for the number of landfalls. In this case you type

```r
cD2[6] <- 1    # assign the 6 year of the decade a value of 1 landfall
```

The assignment to the 6th entry in the vector cD2 is done by referencing the 6th entry of the vector with square brackets `[]`. 

It's important to keep this in mind: Parentheses `()` are used for functions and square brackets `[]` are used to extract values from vectors (and arrays, lists, etc). REPEAT: `[]` are used to extract or subset values from vectors, data frames, matrices, etc.


```r
cD2    #print out the values
```

```
##  [1] 0 5 4 2 3 1 3 3 2 1
```

```r
cD2[2]  # print the number of landfalls during year 2 of the second decade
```

```
## [1] 5
```

```r
cD2[4]  # 4th year count
```

```
## [1] 2
```

```r
cD2[-4]  # all but the 4th year
```

```
## [1] 0 5 4 3 1 3 3 2 1
```

```r
cD2[c(1, 3, 5, 7, 9)]   # print the counts from the odd years
```

```
## [1] 0 4 3 3 2
```

One way to remember how to use functions is to think of them as pets.  They don't come unless they are called by name (spelled properly). They have a mouth (parentheses) that likes to be fed (arguments), and they will complain if they are not feed properly.

## Finding help

There are many different functions---more than you are able to keep in your head. R has built-in help facilities. These can be consulted for information about what is returned by the function, for details on additional arguments, and for examples.

If you know the name of the function, you can type for example:

```r
?quantile
```

This works great if you can remember the name of the function. The function `apropos()` searches for functions with names containing a string of characters.

```r
apropos("mean")
```

```
##  [1] ".colMeans"      ".rowMeans"      "colMeans"       "kmeans"        
##  [5] "mean"           "mean_cl_boot"   "mean_cl_normal" "mean_sdl"      
##  [9] "mean_se"        "mean.Date"      "mean.default"   "mean.difftime" 
## [13] "mean.POSIXct"   "mean.POSIXlt"   "rowMeans"       "weighted.mean"
```

The function `help.search()` will search each entry in the help system and returning matches (often many) of functions that mention the word "mean".

Most help pages have examples. These can be run one-by-one by cutting and pasting into the console, or all at once by using the function example.

```r
example(mean)
```

```
## 
## mean> x <- c(0:10, 50)
## 
## mean> xm <- mean(x)
## 
## mean> c(xm, mean(x, trim = 0.10))
## [1] 8.75 5.50
```

## Working smarter

R's console keeps a history of your commands. The previous commands are accessed using the up and down arrow keys. Repeatedly pushing the up arrow will scroll backward through the history so you can reuse previous commands.

Many times you wish to change only a small part of a previous command, such as when a typo is made.  With the arrow keys you can access the previous command then edit it as desired.

You can save the history into a file and then load it later.

```r
savehistory("Aug30")
loadhistory("Aug30")
```

Since you are working in an Rmd file there is usually no need to save your history file.

## Creating structured data

Sometimes data have a pattern. For instance the integers 1 through 99. To enter these one by one would be a waste of time. Instead, the colon function is used for creating simple sequences.

```r
1:100
```

```
##   [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
##  [18]  18  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34
##  [35]  35  36  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51
##  [52]  52  53  54  55  56  57  58  59  60  61  62  63  64  65  66  67  68
##  [69]  69  70  71  72  73  74  75  76  77  78  79  80  81  82  83  84  85
##  [86]  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100
```

```r
rev(1:100)
```

```
##   [1] 100  99  98  97  96  95  94  93  92  91  90  89  88  87  86  85  84
##  [18]  83  82  81  80  79  78  77  76  75  74  73  72  71  70  69  68  67
##  [35]  66  65  64  63  62  61  60  59  58  57  56  55  54  53  52  51  50
##  [52]  49  48  47  46  45  44  43  42  41  40  39  38  37  36  35  34  33
##  [69]  32  31  30  29  28  27  26  25  24  23  22  21  20  19  18  17  16
##  [86]  15  14  13  12  11  10   9   8   7   6   5   4   3   2   1
```

```r
100:1
```

```
##   [1] 100  99  98  97  96  95  94  93  92  91  90  89  88  87  86  85  84
##  [18]  83  82  81  80  79  78  77  76  75  74  73  72  71  70  69  68  67
##  [35]  66  65  64  63  62  61  60  59  58  57  56  55  54  53  52  51  50
##  [52]  49  48  47  46  45  44  43  42  41  40  39  38  37  36  35  34  33
##  [69]  32  31  30  29  28  27  26  25  24  23  22  21  20  19  18  17  16
##  [86]  15  14  13  12  11  10   9   8   7   6   5   4   3   2   1
```

It's often desirable to specify either the step size and the starting and ending points or the starting and ending points and the length of the sequence. The `seq()` function does this.

```r
seq(1, 9, by = 2)
```

```
## [1] 1 3 5 7 9
```

```r
seq(1, 10, by = 2)
```

```
## [1] 1 3 5 7 9
```

```r
seq(1, 9, length = 5)
```

```
## [1] 1 3 5 7 9
```

To create a vector of the same value use the `rep()` function. The simplest usage is to repeat the first argument a specified number of times.

```r
rep(1, 10)
```

```
##  [1] 1 1 1 1 1 1 1 1 1 1
```

```r
rep(1:3, 3)
```

```
## [1] 1 2 3 1 2 3 1 2 3
```

More complicated patterns can be repeated by specifying pairs of equal-sized vectors. In this case, each element of the first vector is repeated the corresponding number of times specified by the element in the second vector.

```r
rep(c("long", "short"), c(1, 2))
```

```
## [1] "long"  "short" "short"
```

## Examining your data

To find the maximum number of landfalls in the first decade, type:

```r
max(cD1)
```

```
## [1] 3
```

Which years had the maximum?

```r
cD1 == 3
```

```
##  [1] FALSE  TRUE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE
```

Notice the double equals signs (`==`).  This tests each value in `cD1` to see if it is equal to 3. The 2nd and 4th values are equal to 3 so TRUEs are returned. Think of this as asking R a question. Is the value equal to 3?  R answers all at once with a vector of TRUE's and FALSE's.

Now the question is, how do you get the vector element corresponding to the TRUE values?  That is, which years have 3 landfalls?

```r
which(cD1 == 3)
```

```
## [1] 2 4
```

The function `which.max()` can be used to get the first maximum.

```r
which.max(cD1)
```

```
## [1] 2
```

You might also want to know the total number of landfalls in each decade and the number of years in a decade without a landfall.  Or how about the ratio of the mean number of landfalls over the two decades.

```r
sum(cD1); sum(cD2)
```

```
## [1] 13
```

```
## [1] 24
```

Here you stack function calls on a single line by using the semicolon `;`.

```r
sum(cD1 == 0); sum(cD2 == 0)
```

```
## [1] 3
```

```
## [1] 1
```


```r
mean(cD2)/mean(cD1)
```

```
## [1] 1.846154
```

So there is 85% more landfalls during the second decade.  Is this statistically significant?

To remove an object from your environment use the `rm()` function.

```r
rm(cD1, cD2)
```

## Practice & Help

* Standard learning path: 
1. Install R
2. Install RStudio
3. Google "How do I [THING I WANT TO DO] in R?"

* Install the package **swirl**. Type `swirl()` and select R Programming > Vectors, Missing Values, Subsetting Vectors, and Matrices and Data Frames

* The online book [R for Data Science](http://r4ds.had.co.nz/) by Grolemund and Wickham is an excellent resource for getting started with using R.

* https://rstudio.cloud/
