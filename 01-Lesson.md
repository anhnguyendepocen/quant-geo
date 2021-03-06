---
title: "Introduction"
author: "James B. Elsner"
date: August 28, 2018
output: 
  html_document:
    keep_md: true
---

"**The goal is to provide analytical tools that will last students a lifetime.**''---Edward Tufte

After this lesson you will (1) know what this class is about, (2) know how you will be graded, (3) know how to install R and RStudio on your laptop, and (4) know how to make a scatter plot.

## Syllabus

### Contact Information

* Professor James B. Elsner, Bellamy Building, Room 323a
* Lesson Hours: TR 8:00-9:15 a.m.
* Office Hours: TR 9:15-10:30 a.m. & 2-3 p.m. (& by appointment)

Email: <jelsner@fsu.edu>

Links to Elsner's stuff:

* [Canvas](https://cas.fsu.edu/cas/login)
* [GitHub](https://github.com/jelsner/quant-geo)
* [Twitter](https://twitter.com/JBElsner)
* [Research Website](http://myweb.fsu.edu/jelsner/_site/)

### Required Materials

A laptop computer with R and RStudio installed. Bring your laptop to every class.

### Short Description

This course is an introduction to data science and statistical thinking for geographers. You will use is the R programming language. You will use the RStudio integrated development environment (IDE) to work with R.

### Learning Outcomes

Expected learning outcomes:

* Factual: You will acquire basic knowledge of data science. You will become familiar with the terminology used to describe data and the procedures and outcomes applied to visualizing, wrangling, and drawing conclusions from data.

* Conceptual: You will develop an understanding of some of the statistical tools and when to apply them in data analysis and modeling. You will cultivate a first-order understanding of the motivations, advantages, and disadvantages for different methods and how uncertainties in the data and methods propagate through your analysis.

* Procedural: You will learn how to use R to analyze, graph, and model data. You will learn how to work within RStudio to create reproducible science. You will learn how to analyze data statistically. You will be able to interpret the results of your model. You will be able to determine the significance of effects. You will learn enough R to be able to build on this knowledge throughout your career.

* Meta cognitive: You will recognize the potential of data science and some of its limitations. You will be able to identify reasonable statistical inferences. You will gain an appreciation for the importance of open-source science.

I expect you to have an understanding of basic statistical concepts like mean, standard deviation, and correlation. Everything you will do in this class will be done using R/RStudio.

There is _no required textbook_. You are responsible for working through and understanding the code that will be available on Canvas before each lesson.

### Grading Policies

Grades are determined by two exams (each worth 40%) and several (4-6) assignments cumulatively worth 20%. There are NO make-up exams. Class attendance is expected, but not required. Late assignments are not accepted. Assignments and exams will be done using R markdown and submitted to me in digital format. No extra credit will be given.

Grade | Score | Standard
------|-------|---------
A     | 93-100| Outstanding; few if any errors/omissions
B     | 85-93 | Good; only minor errors/omissions
C     | 75-85 | Satisfactory; minor and a few major errors
D     | 65-75 | Poor; many major errors and omissions

**I will use plus and minus grades.**

### Academic Honor Code

http://www.eng.fsu.edu/~peterson/fsuhc.html

### Students With Disabilities Act

Students needing academic accommodation should: (1) register with and provide documentation to the Student Disability Resource Center (https://dos.fsu.edu/sdrc/); (2) bring a letter to me indicating the need for accommodation and what type. This should be done sometime during the first week of classes.

### Syllabus Change Policy

This syllabus is a guide for the course and is subject to change with advanced notice. The exam dates/times are firm.

### Schedule (subject to change with notice)

Week | Day      | Date         | Topic
-----|----------|--------------|------
1    | Tuesday  | August 28    | Introduction
1    | Thursday | August 30    | RStudio and R 
2    | Tuesday  | September 4  | Working with R
2    | Thursday | September 6  | Data and Data Frames
3    | Tuesday  | September 11 | Grammar for Data
3    | Thursday | September 13 | Grammar for Data
4    | Tuesday  | September 18 | Grammar for Graphs
4    | Thursday | September 20 | Grammar for Graphs
5    | Tuesday  | September 25 | Maps with R
5    | Thursday | September 27 | Maps with R
6    | Tuesday  | October 2    | Review for First Exam
6    | Thursday | October 4    | FIRST EXAM
7    | Tuesday  | October 9    | Bayesian Data Analysis
7    | Tuesday  | October 11   | Bayesian Data Analysis
8    | Tuesday  | October 16   | Regression
8    | Thursday | October 18   | Regression
9    | Tuesday  | October 23   | Regression
9    | Thursday | October 25   | Classification & Regression Trees
10   | Tuesday  | October 30   | Logistic Regression
10   | Thursday | November 1   | Quantile Regression
11   | Tuesday  | November 6   | Grammar for Spatial Data
11   | Thursday | November 8   | Geographic Regression
12   | Tuesday  | November 13  | Geographic Regression
12   | Thursday | November 15  | Spatial Autocorrelation
13   | Tuesday  | November 20  | NO CLASS (out of town)
13   | Thursday | November 22  | NO CLASS (Thanksgiving)
14   | Tuesday  | November 27  | Spatial Autocorrelation
14   | Thursday | November 29  | Spatial Regression
15   | Tuesday  | December 4   | Spatial Regression
15   | Thursday | December 6   | Review for Second Exam
16   | Friday   | December 14  | SECOND EXAM (3-5p)

## Data Science

Data science must be done on a computer. You have two choices: use a spreadsheet or code with a programming language. 

A spreadsheet is convenient, but it is ultimately limiting and hampers three properties essential for proper scientific data analysis: *Reproducibility*, *Communication*, *Automation*.

Today coding is an important skill for most technical jobs. Here I will teach you how to code using R. Just like learning to write doesn't necessarily make you a writer, learning to code doesn't mean you will be a coder.

### Reproducibility

If your analysis is to be convincing, the trail from the data you started with to the final output must be available to the public.

It is difficult to create a reproducible trail with a spreadsheet. It is easy to make mistakes (e.g., accidentally sorting just a column rather than the entire table).

A scientific paper describing the result of your analysis is advertisement for a specific claim. But the `proof` is the procedure that was used to obtain the result. The code should be the exact procedure.

### Communication

Code is the recipe for what you did. It is the most efficient way to communicate exactly what you did. Communication to others and to your future self.

It's hard to explain precisely what you did when working with a spreadsheet. Click here, then right click here, then choose menu X, etc. The words you might use to describe these procedures are not standard.

Said another way: Code is an efficient way to communicate because all important information is given as plain text without ambiguity.

### Automation

If you've ever made a map using GIS you know how hard it is to make another (even similar one) with a new set of data. Executing code with new data is simple.

## The R programming language

* R is the leading open source statistical programming language. R vs Python.
* R is free, open-source, runs on Windows, Macs, etc. Excellent graphing capabilities. Powerful, extensible, and relatively easy to learn syntax. Thousands of functions.
* R has all the cutting edge statistical methods including methods in spatial statistics.
* R is increasingly used by scientists of all stripes. Most of the world's statisticians use (and contribute to) it.

### Get R

* Go to [Get R](http://www.r-project.org).
* Click on CRAN (Comprehensive R Archive Network).
* Click one of the mirror sites.
* Select one of the precompiled binary distributions.
* If you are using Windows, select base, then Download R*** for Windows.
* Click on the downloaded file to install. 
* Use the default options.

### Dynamic report generation

Combining R with **RStudio** allows you to generate reports on the fly.

A common practice in writing scientific reports is to (1) import data into a software package, (2) run a procedure to get the results, (3) copy and paste selected pieces of the result in a document program, and (4) add a few descriptions of the results to finish.

Problems:

1. error-prone because there are many manual steps to the workflow;
2. the manual steps are tedious (copying/pasting results between documents);
3. workflow is hard to record when it involves spreadsheets, therefore it is difficult to reproduce;
4. a change to the data requires you to go through the same procedure again, which can take nearly the same amount of time and effort as the original effort;
5. the analysis and writing are typically mixed together, so your attention has to be paid to synchronizing the parts.

A dynamic report is generated automatically from code. Just like a software package has its source code, a dynamic report has its source as a mix of code and text. 

When you compile the source report, the code is executed and placed in the output; you get a final report that contains code and the human readable text. 

Because you manage only one document, you are free from many of the problems above. For example, you can change a single parameter in the code, that produces an updated report.

**RStudio** helps you generate dynamic reports from your R session. In this class you will use RStudio to create answer sheets for your homework and exams. You can use it to take notes during class. 

### Get RStudio

* Go to [Get RStudio](http://rstudio.org).
* Select Download RStudio.
* Select RStudio Desktop (FREE).
* Click on the downloaded file to install.

After opening RStudio you should see your window separate into four panes. The upper left pane is the markdown file (`01-Lesson.Rmd`), the upper right pane contains the environment and history panels, the lower right pane contains the plots, packages, etc panels, and the lower left is the R console.

### Install a package

The first thing you will do is create a graph using the functions in the **ggplot2** package. Packages are pieces of code for doing certain things. The **ggplot2** package has code pieces for making nice graphs.

Two steps:

1. Download the package from CRAN.

This is done by selecting the `Packages` tab  in the lower right panel. Select `Install` then type the name of the package `ggplot2`. Note: That is the same as typing `install.packages("ggplot2")` in the console.

2. Make the code available to your particular R session. This is done by issuing the `library(ggplot2)` command in the console. Here you want to make this command part of the markdown file so you delinate the command from the text by placing triple graves (`) followed by {r} before the command and triple graves after the command.

```r
library(ggplot2)
```

R has thousands of packages. You will use some of them this semester.

Installing gets the package from CRAN and puts it on your local computer. The `library(ggplot2)` makes all the code from the package available to your **current** R session.

NOTE: Step (1) is done once. Step (2) must be done everytime you open an new R session.

### Examine some data

We will use the `airquality` data frame. It is a built-in data set in the **datasets** package that was loaded as part of the base R installation. The data set contains daily air quality measurements from New York City during May through September 1973. Type:

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

This shows the first 6 rows of the data frame. The data set contains ozone concentration (ppm), solar radiation, wind speed, temperature (F), month and day. The number of rows shown can be changed with the `n = ` argument (e.g., `head(airquality, n = 10)` will display the first ten rows.

The data frame is a matrix of values with column names. Think of it as a table you might see in a report. The `dim()` function gives the size (number of rows and columns).

```r
dim(airquality)
```

```
## [1] 153   6
```


```r
length(airquality$Ozone)
```

```
## [1] 153
```

### Make a scatter plot graph

Here you are interested in the question, is ozone concentration higher on warmer days? Before you compute statistics you should plot our data. The plot of choice when you have two numeric variables is the scatter plot.

The argument `data =` must identify a data frame by name. Here the data frame is named `airquality`. The values in the column labeled `Temp` are plotted along the horizontal axis and the values in the column labeled `Ozone` are plotted along the vertical axis. This is done with the `aes()` function and the `x =` and `y =` arguments.

```r
ggplot(data = airquality, aes(x = Temp, y = Ozone)) +
  geom_point()
```

```
## Warning: Removed 37 rows containing missing values (geom_point).
```

![](01-Lesson_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

* Describe what you see. 
* What does the warning mean?
* On average is ozone concentration higher on windy days? DO: Make a scatter plot to answer this question.

### On your own

Consider the `cars` data frame. DO: Create a scatter plot showing breaking distance (`dist`) on the vertical axis and traveling speed (`speed`) on the horizontal axis. Describe what you see.
