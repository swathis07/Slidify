---
title       : Developing Data Products Project
subtitle    : Data Science Specialization - Coursera
author      : Swathi S.
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## About the Project

The goal of the project is to build an interactive web application using `Shiny`. Shiny is a platform that helps create interactive R program embedded into the web.

For this project, I created an app that uses Census Statistics data of all the states of USA to understand how various statistics are related to each other.

--- .class #id

## Application

`Overview`:
This application allows the user to select US states statistics whose interaction they would like to observe. The data is based on the U.S. Department of Commerce, Bureau of the Census (1977) Statistical Abstract of the United States. This data is available in the R dataset library `state`.

`Function`:
You can select any two variable whose interaction you would observe by selecting the relevant statistic from the drop down menu. 

The `Plot` tab shows an interactive chart of how the selected variables interact. The chart is created using rCharts.

The `Summary` tab shows the summary of the regression model that was fitted to the data.

The `Table` tab displays the original data in a sortable and searchable data format for users to play around and understand the data better.

The application can be found at https://hereandnow.shinyapps.io/Project/

--- .class #id

## Application Snapshot

This is a snapshot of the application running on shinyapp

<iframe src ="Capture.PNG"></iframe>

--- .class #id

## R Code sample

This is part of the code that was used in creating the data used for the application


```r
state <- data.frame(state.x77)
state <- data.frame(cbind(rownames(state),state[,c(-5,-7)]))
colnames(state)[c(1,5,6)]<-c("State","Life_Expectancy","HS_Grad")
str(state)
```

```
## 'data.frame':	50 obs. of  7 variables:
##  $ State          : Factor w/ 50 levels "Alabama","Alaska",..: 1 2 3 4 5 6 7 8 9 10 ...
##  $ Population     : num  3615 365 2212 2110 21198 ...
##  $ Income         : num  3624 6315 4530 3378 5114 ...
##  $ Illiteracy     : num  2.1 1.5 1.8 1.9 1.1 0.7 1.1 0.9 1.3 2 ...
##  $ Life_Expectancy: num  69 69.3 70.5 70.7 71.7 ...
##  $ HS_Grad        : num  41.3 66.7 58.1 39.9 62.6 63.9 56 54.6 52.6 40.6 ...
##  $ Area           : num  50708 566432 113417 51945 156361 ...
```

--- .class #id
