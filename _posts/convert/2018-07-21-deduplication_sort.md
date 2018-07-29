---
layout: post
title: "Deduplication and Sort in R"
date: "2018-07-29"
excerpt: "중복데이터 삭제와 정렬"
output: 
  github_document:
    toc: true
    toc_depth: 3
categories: r
tag: [r, 중복제거]
comments: true
---

## Deduplication

### unique(): 중복제거

`unique()`를 사용하여 중복된 값을 제거하여 표현할 수 있다.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

unique(x)
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10 NA  1 11
{% endhighlight %}

NA값이 출력된다. NA값이 출력되지 않길 원한다면 `na.omit`을 사용한다.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

na.omit(unique(x))
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10  1 11
## attr(,"na.action")
## [1] 9
## attr(,"class")
## [1] "omit"
{% endhighlight %}

깔끔하게 쓰고 싶다면 `as.integer()`를 사용한다.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

as.integer(na.omit(unique(x)))
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10  1 11
{% endhighlight %}

***

## Sort

### sort(): 정렬해주는 함수


{% highlight r %}
x <- c(3,2,4,8,6,5,10,NA,1,11,NA,15)

# NA값은 제외되고 출력된다.
sort(x)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# 오름차순(기본값)
sort(x, decreasing = FALSE)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# 내림차순
sort(x, decreasing = TRUE)
{% endhighlight %}



{% highlight text %}
##  [1] 15 11 10  8  6  5  4  3  2  1
{% endhighlight %}



{% highlight r %}
# NA 출력 안함(기본값)
sort(x, decreasing = FALSE, na.last = NA)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# NA를 끝에다가 출력
sort(x, decreasing = FALSE, na.last = TRUE)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15 NA NA
{% endhighlight %}



{% highlight r %}
# NA를 처음에다가 출력
sort(x, decreasing = FALSE, na.last = FALSE)
{% endhighlight %}



{% highlight text %}
##  [1] NA NA  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# 내림차순을 rev()로 표현 가능
rev(sort(x))
{% endhighlight %}



{% highlight text %}
##  [1] 15 11 10  8  6  5  4  3  2  1
{% endhighlight %}


***
  
### order(): 정렬의 색인을 반환
  
정렬의 위치(index) 정보를 반환할 때 사용한다.


{% highlight r %}
x <- c(30,50,10,40,20,NA)

sort(x)
{% endhighlight %}



{% highlight text %}
## [1] 10 20 30 40 50
{% endhighlight %}



{% highlight r %}
# 정렬의 색인을 반환
order(x) # 10이 3번 index에, 20번은 5번 index에... 있다고 해석하면 된다.
{% endhighlight %}



{% highlight text %}
## [1] 3 5 1 4 2 6
{% endhighlight %}



{% highlight r %}
# 위치 정보로 출력
x[order(x)] # SORT 기능
{% endhighlight %}



{% highlight text %}
## [1] 10 20 30 40 50 NA
{% endhighlight %}



{% highlight r %}
# 위치정보에 NA정보를 표시 안함 
x[order(x, decreasing = TRUE, na.last = NA)]
{% endhighlight %}



{% highlight text %}
## [1] 50 40 30 20 10
{% endhighlight %}



{% highlight r %}
# 위치정보에 NA를 마지막에 표시하여 출력 (기본값)
x[order(x, decreasing = TRUE, na.last = TRUE)]
{% endhighlight %}



{% highlight text %}
## [1] 50 40 30 20 10 NA
{% endhighlight %}



{% highlight r %}
# 위치정보에 NA를 처음에 표시하여 출력
x[order(x, decreasing = TRUE, na.last = FALSE)]
{% endhighlight %}



{% highlight text %}
## [1] NA 50 40 30 20 10
{% endhighlight %}

***
  
### doBy 패키지: 데이터 프레임에 정렬


{% highlight r %}
# emp table road
setwd("C:/data")
{% endhighlight %}



{% highlight text %}
## Error in setwd("C:/data"): cannot change working directory
{% endhighlight %}



{% highlight r %}
emp <- read.csv('emp.csv',stringsAsFactors = F)
{% endhighlight %}



{% highlight text %}
## Error in file(file, "rt"): cannot open the connection
{% endhighlight %}



{% highlight r %}
# doBy package road
library(doBy)
{% endhighlight %}



{% highlight text %}
## Error in library(doBy): there is no package called 'doBy'
{% endhighlight %}



{% highlight r %}
# SALARY를 기준으로 오름차순 정렬
orderBy(~SALARY,emp[,c("LAST_NAME","SALARY")])
{% endhighlight %}



{% highlight text %}
## Error in orderBy(~SALARY, emp[, c("LAST_NAME", "SALARY")]): could not find function "orderBy"
{% endhighlight %}



{% highlight r %}
# 내림차순(컬럼 앞에 -를 이용)
orderBy(~-SALARY,emp[,c("LAST_NAME","SALARY")])
{% endhighlight %}



{% highlight text %}
## Error in orderBy(~-SALARY, emp[, c("LAST_NAME", "SALARY")]): could not find function "orderBy"
{% endhighlight %}

여러 개의 컬럼으로 정렬을 하는 경우가 있다. 그 때는 `~`뒤에 컬럼끼리 연결하되, 오름차순(+)인지 내림차순인지(-)를 명시해주어야 한다.


{% highlight r %}
# 오름차순의 순서(+를 이용)
orderBy(~DEPARTMENT_ID+SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
## Error in orderBy(~DEPARTMENT_ID + SALARY, emp[, c("LAST_NAME", "SALARY", : could not find function "orderBy"
{% endhighlight %}



{% highlight r %}
# 내림차순의 순서(-를 이용)
orderBy(~-DEPARTMENT_ID-SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
## Error in orderBy(~-DEPARTMENT_ID - SALARY, emp[, c("LAST_NAME", "SALARY", : could not find function "orderBy"
{% endhighlight %}



{% highlight r %}
# 오름차순과 내림차순 혼용(첫 컬럼에 + 생략 가능)
orderBy(~DEPARTMENT_ID-SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
## Error in orderBy(~DEPARTMENT_ID - SALARY, emp[, c("LAST_NAME", "SALARY", : could not find function "orderBy"
{% endhighlight %}

