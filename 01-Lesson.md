Introduction
================

August 28, 2018

"**The goal is to provide analytical tools that will last students a lifetime.**''---Edward Tufte

-   After this lesson you will know what this class is about, how you will be graded, and how to install R and RStudio on your laptop.

Syllabus
--------

### Contact Information

Professor James B. Elsner, Bellamy Building, Room 323a

Lesson Hours: TR 8:00-9:15 a.m.

Office Hours: TR 9:15-10:30 a.m. & 2-3 p.m. (& by appointment)

Email: <jelsner@fsu.edu>

Important links:

-   [Canvas](https://cas.fsu.edu/cas/login)
-   [GitHub](https://github.com/jelsner/quant-geo)
-   [Twitter](https://twitter.com/JBElsner)
-   [Research Website](http://myweb.fsu.edu/jelsner/_site/)

### Materials

Students need a laptop computer with R and RStudio.

### Short Description

Quantitative geography is useful for addressing many of the problems facing our world today. In this course I will teach you some of the quantitative methods routinely used by professional geographers. The methods will be coded in the R programming language. Access to the R programming language will be done through R Notebooks within the RStudio environment.

### Learning Outcomes

The course has the following expected learning outcomes:

-   Factual: You will acquire basic knowledge of statistical methods in data analysis. You will become familiar with the terminology used to describe data and the statistical procedures and outcomes applied in quantitative geographical analysis.

-   Conceptual: You will develop an understanding of some of the statistical tools and when to apply them in data analysis and modeling. You will cultivate a first-order understanding of the motivations, advantages, and disadvantages for different methods and how uncertainties in the data and methods propagate through your analysis.

-   Procedural: You will learn how to use R to analyze, graph, and model data. You will learn how to work within RStudio to create reproducible analyses. You will learn how to analyze data statistically. You will be able to interpret the results of your model in terms of the physical variables. You will be able to explain the significance of effects. You will learn enough R to be able to build on this knowledge throughout your career.

-   Meta cognitive: You will recognize the potential and some limitations of statistical and data analytic methods with respect to the constraints set by the underlying physical and deterministic processes you seek to explore. You will be able to identify reasonable inferences or conclusions from your analyses. You will gain an appreciation for the importance of open-source research.

I expect you to have some understanding of descriptive statistical concepts such as means, standard deviations, and correlation as well as some basic knowledge of inference (e.g., *t*-test). Everything you do in this class will be done using R/RStudio.

There is *no required textbook* for this course but you are responsible for working through the code given in each lesson.

### Grading Policies

Grades are determined by two exams (each worth 40%) and several (4-6) assignments cumulatively worth 20%. There are NO make-up exams. Class attendance is expected, but not required. Late assignments are not accepted. Assignments and exams will be done using R Notebooks and submitted to me in digital format. No extra credit will be given.

| Grade | Score  | Standard                                   |
|-------|--------|--------------------------------------------|
| A     | 93-100 | Outstanding; few if any errors/omissions   |
| B     | 85-93  | Good; only minor errors/omissions          |
| C     | 75-85  | Satisfactory; minor and a few major errors |
| D     | 65-75  | Poor; many major errors and omissions      |

**I will use plus and minus grades.**

### Academic Honor Code

<http://www.eng.fsu.edu/~peterson/fsuhc.html>

### Students With Disabilities Act

Students needing academic accommodation should: (1) register with and provide documentation to the Student Disability Resource Center; (2) bring a letter to me indicating the need for accommodation and what type. This should be done sometime during the first week of classes.

### Syllabus Change Policy

This syllabus is a guide for the course and is subject to change with advanced notice. The exam dates/times are firm.

### Schedule (subject to change)

| Week | Day      | Date         | Topic                             |
|------|----------|--------------|-----------------------------------|
| 1    | Tuesday  | August 28    | Introduction (Mr. Fricker)        |
| 1    | Thursday | August 30    | RStudio and R                     |
| 2    | Tuesday  | September 4  | Using R                           |
| 2    | Thursday | September 6  | Data and Data Frames              |
| 3    | Tuesday  | September 11 | Grammar for Data                  |
| 3    | Thursday | September 13 | Grammar for Data                  |
| 4    | Tuesday  | September 18 | Grammar for Graphs                |
| 4    | Thursday | September 20 | Grammar for Graphs                |
| 5    | Tuesday  | September 25 | Maps in R (ggplot2)               |
| 5    | Thursday | September 27 | Maps in R (tmap)                  |
| 6    | Tuesday  | October 2    | Review for First Exam             |
| 6    | Thursday | October 4    | FIRST EXAM                        |
| 7    | Tuesday  | October 9    | Bayesian Data Analysis            |
| 7    | Tuesday  | October 11   | Bayesian Data Analysis            |
| 8    | Tuesday  | October 16   | Regression                        |
| 8    | Thursday | October 18   | Regression                        |
| 9    | Tuesday  | October 23   | NO CLASS (Out of Town)            |
| 9    | Thursday | October 25   | NO CLASS (Out of Town)            |
| 10   | Tuesday  | October 30   | Regression                        |
| 10   | Thursday | November 1   | Classification & Regression Trees |
| 11   | Tuesday  | November 6   | Logistic Regression               |
| 11   | Thursday | November 8   | Quantile Regression               |
| 12   | Tuesday  | November 13  | Grammar for Spatial Data          |
| 12   | Thursday | November 15  | Geographic Regression             |
| 13   | Tuesday  | November 20  | NO CLASS (Out of Town)            |
| 13   | Thursday | November 22  | NO CLASS (Thanksgiving)           |
| 14   | Tuesday  | November 27  | Spatial Autocorrelation           |
| 14   | Thursday | November 29  | Spatial Regression                |
| 15   | Tuesday  | December 4   | Spatial Regression                |
| 15   | Thursday | December 6   | Review for Second Exam            |
| 16   | Friday   | December 14  | SECOND EXAM (3-5p)                |

Modern Data Analysis
--------------------

Modern data analysis must be done on a computer. You have two choices: use a spreadsheet or code with a programming language.

Being able to code is an increasingly important skill.

A spreadsheet is convenient (at least at first), but it is ultimately limiting and hampers three properties that are essential for scientific data analysis: *Reproducibility*, *Communication*, *Automation*.

### Reproducibility

If an analysis is to be convincing to others, the trail from the data to the final output must be made available.

It is difficult to do this with a spreadsheet. It is too easy for mistakes to creep in (for example, accidentally sorting just a column rather than the entire table).

A scientific paper describing the result of an analysis is advertisement for a specific claim. But `proof` is the procedure that was used to obtain the result. The computer code is the message.

### Communication

Computer code is the grammar of communicating what you did. It is not just to get the computer to do what you want it to do but to communicate with other scientists and to your future self.

It is difficult to explain precisely what you did when working with a spreadsheet. Click here, then right click here, then choose menu X, etc. The words we use are not standard.

Computer code is an efficient way to communicate because all important information is given as plain text.

### Automation

If you've made a GIS map you know how difficult it is to recreate it with a new set of data.

This is common in science since data are frequently updated.

During data preparation and exploration you are likely to find problems.

Running computer code with new data is simple.

The R programming language
--------------------------

R is the leading open source statistical programming language.

R is free, open-source, runs on Windows, Macs, etc. Excellent graphing capabilities. Powerful, extensible, and relatively easy to learn syntax. Thousands of functions.

Limited graphical user interface (GUI) meaning it is harder to learn at the outset. No commercial support. It's a programming language so you need to appreciate syntax issues.

Common metaphors for working with computers are: browsers, iTunes, Excel, Word, etc. R is nothing like these. It is easy to forget commands. There are no visual cues: A blank screen is intimidating. It’s not the easiest language to learn but once you get the hang of the basic syntax the data analytic floodgates open. R is generative, like a written language.

R allows you to take advantage of the availability of new, cutting edge applications in emerging statistical fields. For geographers this is apparent in applied spatial statistics.

Also, an increasing number of scientists are reporting results in the context of R, and it's important to know what they are talking about. Most of the world's leading statisticians use and contribute to R.

### Get R

Go to [Get R](http://www.r-project.org) --&gt; Click on CRAN (Comprehensive R Archive Network) --&gt; Scroll to a mirror site. If you are using Windows --&gt; base --&gt; R-\*\*\*.exe --&gt; Save File. Do this now.

Click on the download icon and follow the instructions to install R. You can apply the default options.

### Dynamic report generation

R is a computational engine. Combining R with **RStudio** allows you to generate reports on the fly.

A common practice in writing scientific reports is to (1) import data into a software package, (2) run a procedure to get the results, (3) copy and paste selected pieces of the result in a document program, and (4) add a few descriptions of the results to finish.

Problems:

1.  error-prone because there is too many manual steps to the workflow;
2.  the manual steps are tedious (copying/pasting results between documents);
3.  workflow is hard to record especially when it involves spreadsheets, therefore it is difficult to reproduce;
4.  a change to the data requires you to go through the same procedure again, which can take nearly the same amount of time and effort;
5.  the analysis and writing are mixed together, so attention has to be paid to synchronizing the parts.

A dynamic report is generated automatically from computer code. Just like a software package has its source code, a dynamic report has its source as a mixture of computer code and text.

When you compile the source report, the code in it is executed and replaced with the output; you get a final report by mixing the code output with the original writings.

Because you manage only source code, you are free from the problems above. For example, you can change a single parameter in the code, and get a different report on the fly.

**RStudio** helps you generate dynamic reports from your R session. In this class you will use RStudio to create answer sheets for your homework and exams. You can use it to take notes during class.

### Get RStudio

Click on [Get RStudio](http://rstudio.org) --&gt; Download RStudio Desktop --&gt; Install and open RStudio. Do this now.

After opening RStudio you should see four window panes. The upper left pane is the markdown file, the upper right pane contains the environment and history panels, the lower right pane contains the plots, packages, etc panels, and the lower left is the R console and the conversion progress panel.

Make a graph
------------

The first thing we will do is create a graph using the functions in the **ggplot2** package. Begin by obtaining the package.

``` r
#install.packages("ggplot2")
library(ggplot2)
```

R has thousands of packages. We will use some of them this semester.

The first line is a function that gets the package from CRAN and installs it on your computer. The second line is a function that makes the package with all its functions available to your current R session.

We will use the `airquality` data frame. It is a built-in data set in the **datasets** package that was loaded as part of the base R installation. The data set contains daily air quality measurements from New York City during May through September 1973. Type:

``` r
head(airquality)
```

    ##   Ozone Solar.R Wind Temp Month Day
    ## 1    41     190  7.4   67     5   1
    ## 2    36     118  8.0   72     5   2
    ## 3    12     149 12.6   74     5   3
    ## 4    18     313 11.5   62     5   4
    ## 5    NA      NA 14.3   56     5   5
    ## 6    28      NA 14.9   66     5   6

This gives the first 6 (default) rows of the data frame. The data set contains ozone concentration (ppm), solar radiation, wind speed, temperature (F), month and day.

The data frame is a table (matrix) of values. The `dim()` function gives the size (number of rows and columns).

``` r
dim(airquality)
```

    ## [1] 153   6

``` r
length(airquality$Ozone)
```

    ## [1] 153

Here we are interested in the question, is ozone concentration higher on warmer days? Before we compute statistics we should plot the data.

``` r
ggplot(data = airquality, aes(x = Temp, y = Ozone)) +
  geom_point()
```

    ## Warning: Removed 37 rows containing missing values (geom_point).

![](01-Lesson_files/figure-markdown_github/unnamed-chunk-5-1.png)

Describe what you see. What does the warning mean?

Is ozone concentration higher on windy days? Make a plot and answer this question.