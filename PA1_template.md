# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
activityData <- read.csv("activity.csv", stringsAsFactors = FALSE)
```


## What is mean total number of steps taken per day?

```r
stepsByDay <- aggregate(steps ~ date, data = activityData, FUN = sum)
stepsByDay$day <- 1:nrow(stepsByDay)

library(ggplot2)
g <- ggplot(stepsByDay, aes(day))
g + geom_bar(aes(weight=steps)) +
  labs(x = "Day Number", y = "Number of Steps")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

```r
mean(stepsByDay$steps)
```

```
## [1] 10766.19
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
