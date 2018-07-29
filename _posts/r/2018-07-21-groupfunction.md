---
layout: post
title: "Group Function in R"
date: "2018-07-29"
excerpt: "R에서의 그룹 함수"
output: 
  github_document:
    toc: true
    toc_depth: 3
categories: r
tag: [r, GroupFunction]
comments: true
---

## 그룹함수


{% highlight r %}
x <- c(100,90,80,70)

# 합
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
# 평균
mean(x)
{% endhighlight %}



{% highlight text %}
## [1] 85
{% endhighlight %}



{% highlight r %}
# 분산
var(x)
{% endhighlight %}



{% highlight text %}
## [1] 166.6667
{% endhighlight %}



{% highlight r %}
# 표준편차
sd(x)
{% endhighlight %}



{% highlight text %}
## [1] 12.90994
{% endhighlight %}



{% highlight r %}
# 최대값
max(x)
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}



{% highlight r %}
# 최소값
min(x)
{% endhighlight %}



{% highlight text %}
## [1] 70
{% endhighlight %}



{% highlight r %}
# 행의 개수
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 4   NROW(x): 4"
{% endhighlight %}

결측치(`NA`)가 있는 경우 `na.rm`이라는 option을 써야지만 함수를 사용할 수 있다.


{% highlight r %}
x <- c(100,90,80,70,NA)

# Option을 설정하지 않은 경우
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}



{% highlight r %}
# Option 사용
sum(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
#다른 그룹함수도 마찬가지이다.
mean(x)
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}



{% highlight r %}
mean(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 85
{% endhighlight %}



{% highlight r %}
# 하지만 length()나 NROW()는 사용할 수 있다.
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 5   NROW(x): 5"
{% endhighlight %}



{% highlight r %}
# 결측치(NA)를 제외시키고 행의 수를 사용하려면 다음과 같이 사용한다.
length(na.omit(x))
{% endhighlight %}



{% highlight text %}
## [1] 4
{% endhighlight %}

> 여기서 주의할 점은 `na.rm`을 `TRUE`로 설정하면 평균, 분산, 표준편차는 결측지를 제외한 값이다. 그러면 결과치가 달라질 수 있으니 결측치를 0으로 바꾸거나해서 사용하여야 한다.

### aggregate(): 그룹 지어주는 함수

데이터를 분할하고 각 그룹으로 묶은 후 그룹함수를 적용시켜주는 함수이다. `aggregate(계산될 컬럼 ~ 분할해야 할 기준 컬럼, 데이터, 함수)` 로 사용한다.


{% highlight r %}
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
aggregate(SALARY ~ JOB_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
## Error in eval(m$data, parent.frame()): object 'emp' not found
{% endhighlight %}



{% highlight r %}
# sql로 표현하면 다음과 같다.
#
# SELECT job_id, sum(salary)
# FROM employees
# GROUP BY job_id;
{% endhighlight %}

***

## 2,3차원 데이터 함수

### apply(): 함수 결과를 반환하는 함수

행렬, 배열, 데이터프레임에 함수를 적용한 결과를 벡터, 리스트, 배열 형태로 리턴한다. 행렬에서 행이나 열의 방향으로 함수를 적용한다.

    `apply(x, MARGIN, FUN)`  
    
    `x`: 행렬, 배열, 데이터프레임
    `MARGIN`: 함수를 적용할 때 방향을 지정
              `1`: 행방향, `2`: 열방향, `c(1,2)`: 행과 열 방향이라는 의미
    `FUN`: 적용할 함수(`sum`,`mean`,`var`,`sd`,`max`,`min`)


예제를 풀어보자.


{% highlight r %}
m <- matrix(1:4, ncol = 2)
m
{% endhighlight %}



{% highlight text %}
##      [,1] [,2]
## [1,]    1    3
## [2,]    2    4
{% endhighlight %}



{% highlight r %}
# 행렬 사이즈 확인
dim(m)
{% endhighlight %}



{% highlight text %}
## [1] 2 2
{% endhighlight %}



{% highlight r %}
# 행 방향으로 sum
apply(m, 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 4 6
{% endhighlight %}



{% highlight r %}
# 열 방향으로 sum
apply(m, 2, sum)
{% endhighlight %}



{% highlight text %}
## [1] 3 7
{% endhighlight %}



{% highlight r %}
#
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))
df
{% endhighlight %}



{% highlight text %}
##    name sql python
## 1  king  90     75
## 2 smith  NA     90
## 3  jane  70     NA
{% endhighlight %}



{% highlight r %}
# 1열을 제외하고 모든 행을 sum
apply(df[,c(2:3)], 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 165  NA  NA
{% endhighlight %}



{% highlight r %}
# NA값 제외 후 sum
apply(df[,c(2:3)], 1, sum, na.rm = T)
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}



{% highlight r %}
# 1열을 제외하고 모든 열을 mean
apply(df[,c(2:3)], 2, mean)
{% endhighlight %}



{% highlight text %}
##    sql python 
##     NA     NA
{% endhighlight %}



{% highlight r %}
# NA값 제외한 mean 
apply(df[,c(2:3)], 2, mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

> 주의. 데이터프레임, 배열, 행렬의 형식에서 `apply()`를 사용할 때 단일 컬럼은 `apply()`를 사용할 수 없다. 행열, 배열, 데이터프레임의 모양으로 만들어 주어야 `apply()` 할 수 있다.

***

### rowSums(): 행의 합


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowSums(df[,2:3], na.rm = T) # apply(df[,2:3],1, sum, na.rm = T) 와 같다.
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}

### rowMeans(): 행의 평균


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowMeans(df[,2:3], na.rm = T) # apply(df[,2:3],1, mean, na.rm = T) 와 같다.
{% endhighlight %}



{% highlight text %}
## [1] 82.5 90.0 70.0
{% endhighlight %}

***

### colSums(): 열의 합


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colSums(df[,2:3], na.rm = T) # apply(df[,2:3],2, sum, na.rm = T) 와 같다.
{% endhighlight %}



{% highlight text %}
##    sql python 
##    160    165
{% endhighlight %}

### colMeans(): 열의 평균


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colMeans(df[,2:3], na.rm = T) # apply(df[,2:3],2, mean, na.rm = T) 와 같다.
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

***

### lapply(): 함수 결과를 리스트로 리턴하는 함수

벡터, 리스트, 데이터프레임에 함수를 적용하고 그 결과를 리스트로 리턴하는 함수이다. (리스트형: 서로 다른 데이터타입에 값을 저장하는 자료형)


{% highlight r %}
x <- list(a = 1:3, b = 4:6)

# 평균을 구할 때 mean을 사용하면 된다.
mean(x$a); mean(x$b);
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight text %}
## [1] 5
{% endhighlight %}



{% highlight r %}
# 하지만 lapply를 사용하면 위를 한번에 사용할 수 있다.
lapply(x,mean)
{% endhighlight %}



{% highlight text %}
## $a
## [1] 2
## 
## $b
## [1] 5
{% endhighlight %}

아래 코드를 비교해보자.


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

lapply(df[,2:3], mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
## $sql
## [1] 80
## 
## $python
## [1] 82.5
{% endhighlight %}



{% highlight r %}
apply(df[,2:3],2, mean, na.rm = T) # unlist(lapply(df[,2:3], mean, na.rm = T)) 와 같다.
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
colMeans(df[,2:3], na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

출력은 같다. 자료형에 따라 원하는 것을 사용하자.


{% highlight r %}
# lapply 
lapply(df[,2:3], mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
## $sql
## [1] 80
## 
## $python
## [1] 82.5
{% endhighlight %}



{% highlight r %}
# apply 
apply(df[,2:3],2, mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
# colMeans
colMeans(df[,2:3], na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

***

#### 참고. 자료형데이터의 변환

리스트를 데이터프레임으로 바꿔야 할 경우가 있다. 그러면 `as.data.frame()`을 사용할 수 있다. 바뀌어 진다면 아주 HAPPY한 경우다.


{% highlight r %}
as.data.frame(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

이와 같이 수행할 수 있으나 안되는 경우가 있다. 그럴 경우에는 다음의 단계를 거쳐서 수행하여야 한다.


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))


# 1. 리스트를 벡터형으로 변환
unlist(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
# 2. 벡터형을 매트릭스형로 변환
matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE)
{% endhighlight %}



{% highlight text %}
##      [,1] [,2]
## [1,]   80 82.5
{% endhighlight %}



{% highlight r %}
# 3. 매트릭스형을 데이터프레임으로 변환
x <- as.data.frame(matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE))
names(x) <- c('sql','python')

# 구조 확인
str(x)
{% endhighlight %}



{% highlight text %}
## 'data.frame':	1 obs. of  2 variables:
##  $ sql   : num 80
##  $ python: num 82.5
{% endhighlight %}



{% highlight r %}
class(x) # 데이터는 data.frame형 
{% endhighlight %}



{% highlight text %}
## [1] "data.frame"
{% endhighlight %}



{% highlight r %}
mode(x) # 속 안은 서로 다른 형이 있어서 list형이다.
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}

***

### sapply(): 함수 결과를 벡터로 리턴하는 함수

벡터, 리스트, 데이터프레임에 함수를 적용하고 그 결과를 벡터로 리턴하는 함수


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

x <- sapply(df[,2:3], mean, na.rm = T)
x
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
str(x); class(x); mode(x);
{% endhighlight %}



{% highlight text %}
##  Named num [1:2] 80 82.5
##  - attr(*, "names")= chr [1:2] "sql" "python"
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

위 데이터를 데이터프레임으로 바꾸어보자


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

x <- sapply(df[,2:3], mean, na.rm = T)

# 1. 매트릭스형으로 변환
x <- matrix(x, ncol = 2, byrow=TRUE)

# 2. 데이터프레임형 변환
x <- as.data.frame(x)
names(x) <- c('sql','python')
x
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

***


### tapply(): 그룹핑 후 결과를 리턴

벡터, 데이터프레임에 저장된 데이터를 주어진 기준에 따라 그룹으로 묶은 뒤 그룹함수를 적용하고 그 결과를 array형으로 리턴하는 함수


{% highlight r %}
tapply(emp$SALARY, emp$DEPARTMENT_ID, sum)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, emp$DEPARTMENT_ID, sum): object 'emp' not found
{% endhighlight %}



{% highlight r %}
# aggregate()와 비슷하다.
aggregate(SALARY ~ DEPARTMENT_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
## Error in eval(m$data, parent.frame()): object 'emp' not found
{% endhighlight %}


여러 컬럼을 기준으로 Grouping을 하려면 `list`형으로 컬럼을 묶어서 함수에 넣어주어야 한다.
  

{% highlight r %}
# vector형으로 묶을 시 error 발생
tapply(emp$SALARY, c(emp$DEPARTMENT_ID,emp$JOB_ID), sum)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, c(emp$DEPARTMENT_ID, emp$JOB_ID), sum): object 'emp' not found
{% endhighlight %}



{% highlight r %}
tapply(emp$SALARY, list(emp$DEPARTMENT_ID,emp$JOB_ID), sum)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, list(emp$DEPARTMENT_ID, emp$JOB_ID), sum): object 'emp' not found
{% endhighlight %}



{% highlight r %}
# 결측치를 0으로 치환
tapply(emp$SALARY, list(emp$DEPARTMENT_ID,emp$JOB_ID), sum, default = 0)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, list(emp$DEPARTMENT_ID, emp$JOB_ID), sum, : object 'emp' not found
{% endhighlight %}



{% highlight r %}
# aggregate 사용
aggregate(SALARY ~ DEPARTMENT_ID+JOB_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
## Error in eval(m$data, parent.frame()): object 'emp' not found
{% endhighlight %}

모양을 눈에 익혀서 이러한 모양을 만들려고 할 때 사용하자.

