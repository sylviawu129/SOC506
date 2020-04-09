---
title       : SOC 506 - R Lecture 1
subtitle    : Basics of R
author      : Zack W Almquist
job         : University of Washington
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, quiz, bootstrap, interactive] # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: [libraries/nvd3, libraries/leaflet, libraries/dygraphs]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
logo        : W-Logo_RegistrationMark_Purple_26851.png
biglogo     : Signature_Left_Purple_RGB.png
assets      : {assets: ../../assets}
--- .class #id

<style type="text/css">
body {background:grey transparent;
}
</style>

## Course overview

In this lecture we will cover
- R
- Software, IDEs and other necessary details
- Some key aspects of R as Programing Language

--- .segue bg:grey

# First things first...

--- .class #id

## Why R?

- [R](https://www.r-project.org/)
- Open Source. 
- Popular in Scientific and Industry
- Lots of material available
- Both a Dynamic and extensible library system
- High level programming language
- Programing language written for Statistics and data analysis


--- .class #id

## Why RStudio?

- [Rstudio](https://www.rstudio.com/)
- Easy to use (really!)
- Has a lot of money behind it and influential developers (e.g., Wadley Wickham)
- Good support for Github, Projects and general management
- Strong support for Rmarkdown (allows for Open Science and quick technical reports)

--- .class #id

## tidyverse

- [tidyverse](https://www.tidyverse.org/)
- Important to be aware of, Wadley Wickham has been re-imagining R and how it interacts with the Data Science Community
- Used a lot in industry
- Powerful data management
- Powerful graphics

--- .class #id

## Installing packages

- CRAN Install

```r
install.packages("here")
```
- Github Install


```r
devtools::install_github("mages/googleVis")
```

--- .class #id


## RMarkdown and Homeworks, Labs and Final Project

- All Labs, HWs and Final Project will be written in RMarkdown and compiled to HTML
- This makes a transparent document that includes all necessary R code
- THis is part of the open and reproducible science movement.

--- .class #id

## Review of template

- Next session will cover some basics of RMarkdown.

--- .class #id

### Header 

```
HEADER HERE
```

--- .class #id

## R code

- You can insert code by surrounding it with \`\`\`{r}, followed by \`\`\` (three more ticks)...

\`\`\`{r}  
code here  
\`\`\`  

- Here is an example of some simple math


```r
2 + 2
```

```
## [1] 4
```

--- .class #id

## Overview of R basics

### Assignment


```r
foo <- 2
foo
```

```
## [1] 2
```

```r
foo = 3
foo
```

```
## [1] 3
```

--- .class #id

## Overview of R basics

### Assignment


```r
4 -> foo
foo
```

```
## [1] 4
```

```r
foo <<- 5
foo
```

```
## [1] 5
```

```r
6 ->> foo
foo
```

```
## [1] 6
```

--- .class #id

## Overview of R basics

### Assignment


```r
assign("foo", 7)
foo
```

```
## [1] 7
```

--- .class #id

## Overview of R basics

### Caclulator


```r
6*8
```

```
## [1] 48
```

```r
4^3
```

```
## [1] 64
```

```r
exp(1)   # exp() is the exponential function
```

```
## [1] 2.718282
```

--- .class #id

## Overview of R basics

### Caclulator


```r
pi     # the constant 3.14159265...
```

```
## [1] 3.141593
```

```r
sin(0)
```

```
## [1] 0
```

```r
log(5) # unless you specify the base, R will assume base e
```

```
## [1] 1.609438
```

```r
log(5, base=10)  # base 10
```

```
## [1] 0.69897
```
```

--- .class #id

## Overview of R basics

### Functions


```r
ralph <- function(x) {
    x <- 2
    return(x)
}
x <- 1
ralph(x)
```

```
## [1] 2
```

```r
x
```

```
## [1] 1
```

--- .class #id

## Overview of R basics

### for loops


```r
 for( i in 1:5 ){
        print(i)
    }
```

```
## [1] 1
## [1] 2
## [1] 3
## [1] 4
## [1] 5
```

--- .class #id


## Overview of R basics

### data types: vectors


```r
one <- 1
one
```

```
## [1] 1
```

```r
is.vector(one)
```

```
## [1] TRUE
```

```r
length(one)
```

```
## [1] 1
```

--- .class #id

## Overview of R basics

### data types: vectors


```r
1:40
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
## [24] 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
```

--- .class #id

## Overview of R basics

### data types: vectors


```r
one <- 1
typeof(one)
```

```
## [1] "double"
```

```r
mode(one)
```

```
## [1] "numeric"
```

```r
storage.mode(one)
```

```
## [1] "double"
```

```r
class(one)
```

```
## [1] "numeric"
```

--- .class #id

## Overview of R basics

### data types: vectors


```r
length(LETTERS)
```

```
## [1] 26
```

```r
head(LETTERS)
```

```
## [1] "A" "B" "C" "D" "E" "F"
```

```r
tail(LETTERS)
```

```
## [1] "U" "V" "W" "X" "Y" "Z"
```

```r
length(colors())
```

```
## [1] 657
```

```r
head(colors())
```

```
## [1] "white"         "aliceblue"     "antiquewhite"  "antiquewhite1"
## [5] "antiquewhite2" "antiquewhite3"
```

```r
tail(colors())
```

```
## [1] "yellow"      "yellow1"     "yellow2"     "yellow3"     "yellow4"    
## [6] "yellowgreen"
```

```r
length(1:20)
```

```
## [1] 20
```

```r
length(double())
```

```
## [1] 0
```

--- .class #id

## Overview of R basics

### data types: vectors


```r
1:5 + 6:10
```

```
## [1]  7  9 11 13 15
```

```r
1:5 * 6:10
```

```
## [1]  6 14 24 36 50
```

```r
1:5 ^ 6:10
```

```
## Warning in 1:5^6:10: numerical expression has 15625 elements: only the
## first used
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10
```

--- .class #id

## Overview of R basics

### data types


```r
as.character(1:5)
```

```
## [1] "1" "2" "3" "4" "5"
```

```r
as.numeric(letters[1:5])
```

```
## Warning: NAs introduced by coercion
```

```
## [1] NA NA NA NA NA
```

```r
as.logical(0:5)
```

```
## [1] FALSE  TRUE  TRUE  TRUE  TRUE  TRUE
```

--- .class #id

## Overview of R basics

### data.frames


```r
Grades <- data.frame(
  Name  = c('Bob','Jeff','Mary','Valerie'), 	
  Exam.1 = c(90, 75, 92, 85),
  Exam.2 = c(87, 71, 95, 81)
)
```

--- .class #id


## Overview of R basics

### data.frames

R allows two differnt was to access elements of the `data.frame`. First is a matrix-like notation for accessing particular values. 

  Format  |   Result
--------- | --------------------------------------
`[a,b]`   |  Element in row `a` and column `b`
`[a,]`    |  All of row `a`
`[,b]`    |  All of column `b`


```r
Grades[, 2]       # print out all of column 2 
```

```
## [1] 90 75 92 85
```

```r
Grades$Name       # The $-sign means to reference a column by its label
```

```
## [1] Bob     Jeff    Mary    Valerie
## Levels: Bob Jeff Mary Valerie
```

--- .class #id

## Overview of R basics

### ifelse statement


```r
x <- rnorm(6)
x
```

```
## [1] -0.4198775 -0.8747539  2.6734483  1.6073918  0.4293330 -0.2400521
```

```r
ifelse(x < 0, x - 3, x + 3)
```

```
## [1] -3.419878 -3.874754  5.673448  4.607392  3.429333 -3.240052
```

```r
x + 3 * sign(x)
```

```
## [1] -3.419878 -3.874754  5.673448  4.607392  3.429333 -3.240052
```

--- .class #id

## Overview of R basics

### apply functions


```r
# Create the matrix
m<-matrix(c(seq(from=-98,to=100,by=2)),nrow=10,ncol=10)

# Return the product of each of the rows
apply(m,1,prod)
```

```
##  [1] -2.849130e+15 -5.344148e+15 -7.282577e+15 -8.510121e+15 -8.930250e+15
##  [6] -8.510121e+15 -7.282577e+15 -5.344148e+15 -2.849130e+15  0.000000e+00
```

```r
# Return the sum of each of the columns
apply(m,2,sum)
```

```
##  [1] -890 -690 -490 -290  -90  110  310  510  710  910
```

--- .class #id

## Overview of R basics

### apply functions


```r
# Return a new matrix whose entries are those of 'm' modulo 10
apply(m,c(1,2),function(x) x%%10) 
```

```
##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    2    2    2    2    2    2    2    2    2     2
##  [2,]    4    4    4    4    4    4    4    4    4     4
##  [3,]    6    6    6    6    6    6    6    6    6     6
##  [4,]    8    8    8    8    8    8    8    8    8     8
##  [5,]    0    0    0    0    0    0    0    0    0     0
##  [6,]    2    2    2    2    2    2    2    2    2     2
##  [7,]    4    4    4    4    4    4    4    4    4     4
##  [8,]    6    6    6    6    6    6    6    6    6     6
##  [9,]    8    8    8    8    8    8    8    8    8     8
## [10,]    0    0    0    0    0    0    0    0    0     0
```

--- .class #id



