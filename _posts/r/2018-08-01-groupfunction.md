---
layout: post
title: "[R] Group Function"
date: "2018-08-01"
excerpt: "R<ec>��<ec>��<ec>�� 그룹<ed>��<ec>��"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, groupfunction]
---

## 기본 그룹<ed>��<ec>��


{% highlight r %}
x <- c(100,90,80,70)

# <U+653C><U+3E64>��
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>�����<U+3E30>
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
# <U+653C><U+3E64>��준<U+653C><U+3E64>�����<U+3E38>
sd(x)
{% endhighlight %}



{% highlight text %}
## [1] 12.90994
{% endhighlight %}



{% highlight r %}
# 최�<U+383C><U+3E63>��<U+393C><U+3E32>
max(x)
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}



{% highlight r %}
# 최소�<U+393C><U+3E32>
min(x)
{% endhighlight %}



{% highlight text %}
## [1] 70
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>��<U+653C><U+3E63>�� 개수
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 4   NROW(x): 4"
{% endhighlight %}

결측�<98>(`NA`)가 <ec>��<eb>�� 경우 `na.rm`<ec>��<eb>��<eb>�� option<ec>�� <ec>��<ec>��지�<8c> <ed>��<ec>���<bc> <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight r %}
x <- c(100,90,80,70,NA)

# Option<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��지 <U+653C><U+3E63>��<U+653C><U+3E63><U+393C><U+3E64>� 경우
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}



{% highlight r %}
# Option <U+653C><U+3E63>��<U+653C><U+3E63>��
sum(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
#<U+653C><U+3E62>���<U+623C><U+3E38> 그룹<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E62>�� 마찬가지<U+653C><U+3E63>��<U+653C><U+3E62>��.
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
# <U+653C><U+3E64>��지�<U+383C><U+3E63> length()<U+653C><U+3E62>�� NROW()<U+653C><U+3E62>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 5   NROW(x): 5"
{% endhighlight %}



{% highlight r %}
# 결측�<U+393C><U+3E38>(NA)�<U+623C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E63>���<U+623C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>���<U+623C><U+3E34> <U+653C><U+3E62>��<U+653C><U+3E63>���<U+623C><U+3E63> 같이 <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>��.
length(na.omit(x))
{% endhighlight %}



{% highlight text %}
## [1] 4
{% endhighlight %}

> <ec>��기서 주의<ed>�� <ec>��<ec><9d>� `na.rm`<ec>�� `TRUE`�<9c> <ec>��<ec>��<ed>���<b4> <ed>���<a0>, 분산, <ed>��준<ed>��차는 결측지�<bc> <ec>��<ec>��<ed>�� 값이<eb>��. 그러�<b4> 결과치�<b0>� <eb>��<eb>���<88> <ec>�� <ec>��<ec>��<eb>�� 결측치�<a5><bc> 0<ec>���<9c> 바꾸거나<ed>��<ec>�� <ec>��<ec>��<ed>��<ec>��<ec>�� <ed>��<eb>��.

### aggregate(): 그룹 지<ec>��주는 <ed>��<ec>��

<eb>��<ec>��<ed>���<bc> 분할<ed>���<a0> �<81> 그룹<ec>���<9c> 묶�<9d>� <ed>�� 그룹<ed>��<ec>���<bc> <ec>��<ec>��<ec>��켜주<eb>�� <ed>��<ec>��<ec>��<eb>��. `aggregate(계산<eb>�� 컬럼 ~ 분할<ed>��<ec>�� <ed>�� 기�<a4>� 컬럼, <eb>��<ec>��<ed>��, <ed>��<ec>��)` �<9c> <ec>��<ec>��<ed>��<eb>��.


{% highlight r %}
setwd("C:/data")
emp <- read.csv('emp.csv',stringsAsFactors = F)

aggregate(SALARY ~ JOB_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
##        JOB_ID SALARY
## 1  AC_ACCOUNT   8300
## 2      AC_MGR  12008
## 3     AD_ASST   4400
## 4     AD_PRES  29040
## 5       AD_VP  34000
## 6  FI_ACCOUNT  39600
## 7      FI_MGR  12008
## 8      HR_REP   6500
## 9     IT_PROG  28800
## 10     MK_MAN  13000
## 11     MK_REP   6000
## 12     PR_REP  10000
## 13   PU_CLERK  13900
## 14     PU_MAN  11000
## 15     SA_MAN  61000
## 16     SA_REP 250500
## 17   SH_CLERK  64300
## 18   ST_CLERK  55700
## 19     ST_MAN  36400
{% endhighlight %}



{% highlight r %}
# sql�<U+393C><U+3E63> <U+653C><U+3E64>��<U+653C><U+3E64>��<U+653C><U+3E64>���<U+623C><U+3E34> <U+653C><U+3E62>��<U+653C><U+3E63>���<U+623C><U+3E63> 같다.
#
# SELECT job_id, sum(salary)
# FROM employees
# GROUP BY job_id;
{% endhighlight %}

***

## 2,3차원 <eb>��<ec>��<ed>�� <ed>��<ec>��

### apply(): <ed>��<ec>�� 결과�<bc> 반환<ed>��<eb>�� <ed>��<ec>��

<ed>��<eb>��, 배열, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>�� <ed>��<ec>���<bc> <ec>��<ec>��<ed>�� 결과�<bc> 벡터, 리스<ed>��, 배열 <ed>��<ed>���<9c> 리턴<ed>��<eb>��. <ed>��<eb>��<ec>��<ec>�� <ed>��<ec>��<eb>�� <ec>��<ec>�� 방향<ec>���<9c> <ed>��<ec>���<bc> <ec>��<ec>��<ed>��<eb>��.

    `apply(x, MARGIN, FUN)`  
    
    `x`: <ed>��<eb>��, 배열, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��
    `MARGIN`: <ed>��<ec>���<bc> <ec>��<ec>��<ed>�� <eb>�� 방향<ec>�� 지<ec>��
              `1`: <ed>��방향, `2`: <ec>��방향, `c(1,2)`: <ed>���<bc> <ec>�� 방향<ec>��<eb>��<eb>�� <ec>���<b8>
    `FUN`: <ec>��<ec>��<ed>�� <ed>��<ec>��(`sum`,`mean`,`var`,`sd`,`max`,`min`)


<ec>��<ec>���<bc> <ed><92>�<ec>��보자.


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
# <U+653C><U+3E64>��<U+653C><U+3E62>�� <U+653C><U+3E63>��<U+653C><U+3E63>���<U+383C><U+3E38> <U+653C><U+3E64>��<U+653C><U+3E63>��
dim(m)
{% endhighlight %}



{% highlight text %}
## [1] 2 2
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>�� 방향<U+653C><U+3E63>���<U+393C><U+3E63> sum
apply(m, 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 4 6
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>�� 방향<U+653C><U+3E63>���<U+393C><U+3E63> sum
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
# 1<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�����<U+3E30> 모든 <U+653C><U+3E64>��<U+653C><U+3E63>�� sum
apply(df[,c(2:3)], 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 165  NA  NA
{% endhighlight %}



{% highlight r %}
# NA�<U+393C><U+3E32> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64>�� sum
apply(df[,c(2:3)], 1, sum, na.rm = T)
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}



{% highlight r %}
# 1<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�����<U+3E30> 모든 <U+653C><U+3E63>��<U+653C><U+3E63>�� mean
apply(df[,c(2:3)], 2, mean)
{% endhighlight %}



{% highlight text %}
##    sql python 
##     NA     NA
{% endhighlight %}



{% highlight r %}
# NA�<U+393C><U+3E32> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�� mean 
apply(df[,c(2:3)], 2, mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

> 주의. <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��, 배열, <ed>��<eb>��<ec>�� <ed>��<ec>��<ec>��<ec>�� `apply()`�<bc> <ec>��<ec>��<ed>�� <eb>�� <eb>��<ec>�� 컬럼<ec><9d>� `apply()`�<bc> <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��. <ed>��<ec>��, 배열, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>�� 모양<ec>���<9c> 만들<ec>�� 주어<ec>�� `apply()` <ed>�� <ec>�� <ec>��<eb>��.

***

### rowSums(): <ed>��<ec>�� <ed>��


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowSums(df[,2:3], na.rm = T) # apply(df[,2:3],1, sum, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>� 같다.
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}

### rowMeans(): <ed>��<ec>�� <ed>���<a0>


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowMeans(df[,2:3], na.rm = T) # apply(df[,2:3],1, mean, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>� 같다.
{% endhighlight %}



{% highlight text %}
## [1] 82.5 90.0 70.0
{% endhighlight %}

***

### colSums(): <ec>��<ec>�� <ed>��


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colSums(df[,2:3], na.rm = T) # apply(df[,2:3],2, sum, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>� 같다.
{% endhighlight %}



{% highlight text %}
##    sql python 
##    160    165
{% endhighlight %}

### colMeans(): <ec>��<ec>�� <ed>���<a0>


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colMeans(df[,2:3], na.rm = T) # apply(df[,2:3],2, mean, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>� 같다.
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

***

### lapply(): <ed>��<ec>�� 결과�<bc> 리스<ed>���<9c> 리턴<ed>��<eb>�� <ed>��<ec>��

벡터, 리스<ed>��, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>�� <ed>��<ec>���<bc> <ec>��<ec>��<ed>���<a0> �<b8> 결과�<bc> 리스<ed>���<9c> 리턴<ed>��<eb>�� <ed>��<ec>��<ec>��<eb>��. (리스<ed>��<ed>��: <ec>���<9c> <eb>���<b8> <eb>��<ec>��<ed>��<ed><83>�<ec>��<ec>�� 값을 <ec><a0>�<ec>��<ed>��<eb>�� <ec>��료형)


{% highlight r %}
x <- list(a = 1:3, b = 4:6)

# <U+653C><U+3E64>��균을 구할 <U+653C><U+3E62>�� mean<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>���<U+623C><U+3E34> <U+653C><U+3E62>��<U+653C><U+3E62>��.
mean(x$a); mean(x$b);
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight text %}
## [1] 5
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>��지�<U+383C><U+3E63> lapply�<U+623C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>���<U+623C><U+3E34> <U+653C><U+3E63>���<U+623C><U+3E63> <U+653C><U+3E64>��번에 <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
lapply(x,mean)
{% endhighlight %}



{% highlight text %}
## $a
## [1] 2
## 
## $b
## [1] 5
{% endhighlight %}

<ec>��<eb>�� 코드�<bc> 비교<ed>��보자.


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
apply(df[,2:3],2, mean, na.rm = T) # unlist(lapply(df[,2:3], mean, na.rm = T)) <U+653C><U+3E63><U+393C><U+3E39>� 같다.
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

출력<ec><9d>� 같다. <ec>��료형<ec>�� <eb>��<eb>�� <ec>��<ed>��<eb>�� 것을 <ec>��<ec>��<ed>��<ec>��.


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

#### 참고. <ec>��료형<eb>��<ec>��<ed>��<ec>�� 변<ed>��

리스<ed>���<bc> <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>���<9c> 바꿔<ec>�� <ed>�� 경우가 <ec>��<eb>��. 그러�<b4> `as.data.frame()`<ec>�� <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��. 바뀌어 진다�<b4> <ec>���<bc> HAPPY<ed>�� 경우<eb>��.


{% highlight r %}
as.data.frame(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

<ec>��<ec><99>� 같이 <ec>��<ed>��<ed>�� <ec>�� <ec>��<ec>��<eb>�� <ec>��<eb>��<eb>�� 경우가 <ec>��<eb>��. 그럴 경우<ec>��<eb>�� <eb>��<ec>��<ec>�� <eb>��계�<a5><bc> 거쳐<ec>�� <ec>��<ed>��<ed>��<ec>��<ec>�� <ed>��<eb>��.


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))


# 1. 리스<U+653C><U+3E64>���<U+623C><U+3E63> 벡터<U+653C><U+3E64>��<U+653C><U+3E63>���<U+393C><U+3E63> 변<U+653C><U+3E64>��
unlist(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
# 2. 벡터<U+653C><U+3E64>��<U+653C><U+3E63>�� 매트���<U+3E64><U+653C><U+3E63>��<U+653C><U+3E64>���<U+393C><U+3E63> 변<U+653C><U+3E64>��
matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE)
{% endhighlight %}



{% highlight text %}
##      [,1] [,2]
## [1,]   80 82.5
{% endhighlight %}



{% highlight r %}
# 3. 매트���<U+3E64><U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E64>��<U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63>���<U+393C><U+3E63> 변<U+653C><U+3E64>��
x <- as.data.frame(matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE))
names(x) <- c('sql','python')

# 구조 <U+653C><U+3E64>��<U+653C><U+3E63>��
str(x)
{% endhighlight %}



{% highlight text %}
## 'data.frame':	1 obs. of  2 variables:
##  $ sql   : num 80
##  $ python: num 82.5
{% endhighlight %}



{% highlight r %}
class(x) # <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>�� data.frame<U+653C><U+3E64>�� 
{% endhighlight %}



{% highlight text %}
## [1] "data.frame"
{% endhighlight %}



{% highlight r %}
mode(x) # <ec>�� <ec>��<ec><9d>� <ec>���<9c> <eb>���<b8> <ed>��<ec>�� <ec>��<ec>��<ec>�� list<ed>��<ec>��<eb>��.
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}

***

### sapply(): <ed>��<ec>�� 결과�<bc> 벡터�<9c> 리턴<ed>��<eb>�� <ed>��<ec>��

벡터, 리스<ed>��, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>�� <ed>��<ec>���<bc> <ec>��<ec>��<ed>���<a0> �<b8> 결과�<bc> 벡터�<9c> 리턴<ed>��<eb>�� <ed>��<ec>��


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

<ec>�� <eb>��<ec>��<ed>���<bc> <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>���<9c> 바꾸<ec>��보자


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

x <- sapply(df[,2:3], mean, na.rm = T)

# 1. 매트���<U+3E64><U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>���<U+393C><U+3E63> 변<U+653C><U+3E64>��
x <- matrix(x, ncol = 2, byrow=TRUE)

# 2. <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E64>��<U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>�� 변<U+653C><U+3E64>��
x <- as.data.frame(x)
names(x) <- c('sql','python')
x
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

***


### tapply(): 그룹<ed>�� <ed>�� 결과�<bc> 리턴

벡터, <eb>��<ec>��<ed>��<ed>��<eb>��<ec>��<ec>�� <ec><a0>�<ec>��<eb>�� <eb>��<ec>��<ed>���<bc> 주어�<84> 기�<a4>�<ec>�� <eb>��<eb>�� 그룹<ec>���<9c> 묶�<9d>� <eb>�� 그룹<ed>��<ec>���<bc> <ec>��<ec>��<ed>���<a0> �<b8> 결과�<bc> array<ed>��<ec>���<9c> 리턴<ed>��<eb>�� <ed>��<ec>��


{% highlight r %}
tapply(emp$SALARY, emp$DEPARTMENT_ID, sum)
{% endhighlight %}



{% highlight text %}
##     10     20     30     40     50     60     70     80     90    100 
##   4400  19000  24900   6500 156400  28800  10000 304500  63040  51608 
##    110 
##  20308
{% endhighlight %}



{% highlight r %}
# aggregate()<U+653C><U+3E63><U+393C><U+3E39>� 비슷<U+653C><U+3E64>��<U+653C><U+3E62>��.
aggregate(SALARY ~ DEPARTMENT_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
##    DEPARTMENT_ID SALARY
## 1             10   4400
## 2             20  19000
## 3             30  24900
## 4             40   6500
## 5             50 156400
## 6             60  28800
## 7             70  10000
## 8             80 304500
## 9             90  63040
## 10           100  51608
## 11           110  20308
{% endhighlight %}


<ec>��<eb>�� 컬럼<ec>�� 기�<a4>�<ec>���<9c> Grouping<ec>�� <ed>��<eb>���<b4> `list`<ed>��<ec>���<9c> 컬럼<ec>�� 묶어<ec>�� <ed>��<ec>��<ec>�� <eb>��<ec>��주어<ec>�� <ed>��<eb>��.
  

{% highlight r %}
# vector<U+653C><U+3E64>��<U+653C><U+3E63>���<U+393C><U+3E63> 묶을 <U+653C><U+3E63>�� error 발생
tapply(emp$SALARY, c(emp$DEPARTMENT_ID,emp$JOB_ID), sum)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, c(emp$DEPARTMENT_ID, emp$JOB_ID), sum): ���ڵ��� �ݵ�� ���� ���̸� ������ �մϴ�
{% endhighlight %}



{% highlight r %}
tapply(emp$SALARY, list(emp$DEPARTMENT_ID,emp$JOB_ID), sum)
{% endhighlight %}



{% highlight text %}
##     AC_ACCOUNT AC_MGR AD_ASST AD_PRES AD_VP FI_ACCOUNT FI_MGR HR_REP
## 10          NA     NA    4400      NA    NA         NA     NA     NA
## 20          NA     NA      NA      NA    NA         NA     NA     NA
## 30          NA     NA      NA      NA    NA         NA     NA     NA
## 40          NA     NA      NA      NA    NA         NA     NA   6500
## 50          NA     NA      NA      NA    NA         NA     NA     NA
## 60          NA     NA      NA      NA    NA         NA     NA     NA
## 70          NA     NA      NA      NA    NA         NA     NA     NA
## 80          NA     NA      NA      NA    NA         NA     NA     NA
## 90          NA     NA      NA   29040 34000         NA     NA     NA
## 100         NA     NA      NA      NA    NA      39600  12008     NA
## 110       8300  12008      NA      NA    NA         NA     NA     NA
##     IT_PROG MK_MAN MK_REP PR_REP PU_CLERK PU_MAN SA_MAN SA_REP SH_CLERK
## 10       NA     NA     NA     NA       NA     NA     NA     NA       NA
## 20       NA  13000   6000     NA       NA     NA     NA     NA       NA
## 30       NA     NA     NA     NA    13900  11000     NA     NA       NA
## 40       NA     NA     NA     NA       NA     NA     NA     NA       NA
## 50       NA     NA     NA     NA       NA     NA     NA     NA    64300
## 60    28800     NA     NA     NA       NA     NA     NA     NA       NA
## 70       NA     NA     NA  10000       NA     NA     NA     NA       NA
## 80       NA     NA     NA     NA       NA     NA  61000 243500       NA
## 90       NA     NA     NA     NA       NA     NA     NA     NA       NA
## 100      NA     NA     NA     NA       NA     NA     NA     NA       NA
## 110      NA     NA     NA     NA       NA     NA     NA     NA       NA
##     ST_CLERK ST_MAN
## 10        NA     NA
## 20        NA     NA
## 30        NA     NA
## 40        NA     NA
## 50     55700  36400
## 60        NA     NA
## 70        NA     NA
## 80        NA     NA
## 90        NA     NA
## 100       NA     NA
## 110       NA     NA
{% endhighlight %}



{% highlight r %}
# 결측치���<U+3E35><U+623C><U+3E63> 0<U+653C><U+3E63>���<U+393C><U+3E63> 치환
tapply(emp$SALARY, list(emp$DEPARTMENT_ID,emp$JOB_ID), sum, default = 0)
{% endhighlight %}



{% highlight text %}
##     AC_ACCOUNT AC_MGR AD_ASST AD_PRES AD_VP FI_ACCOUNT FI_MGR HR_REP
## 10           0      0    4400       0     0          0      0      0
## 20           0      0       0       0     0          0      0      0
## 30           0      0       0       0     0          0      0      0
## 40           0      0       0       0     0          0      0   6500
## 50           0      0       0       0     0          0      0      0
## 60           0      0       0       0     0          0      0      0
## 70           0      0       0       0     0          0      0      0
## 80           0      0       0       0     0          0      0      0
## 90           0      0       0   29040 34000          0      0      0
## 100          0      0       0       0     0      39600  12008      0
## 110       8300  12008       0       0     0          0      0      0
##     IT_PROG MK_MAN MK_REP PR_REP PU_CLERK PU_MAN SA_MAN SA_REP SH_CLERK
## 10        0      0      0      0        0      0      0      0        0
## 20        0  13000   6000      0        0      0      0      0        0
## 30        0      0      0      0    13900  11000      0      0        0
## 40        0      0      0      0        0      0      0      0        0
## 50        0      0      0      0        0      0      0      0    64300
## 60    28800      0      0      0        0      0      0      0        0
## 70        0      0      0  10000        0      0      0      0        0
## 80        0      0      0      0        0      0  61000 243500        0
## 90        0      0      0      0        0      0      0      0        0
## 100       0      0      0      0        0      0      0      0        0
## 110       0      0      0      0        0      0      0      0        0
##     ST_CLERK ST_MAN
## 10         0      0
## 20         0      0
## 30         0      0
## 40         0      0
## 50     55700  36400
## 60         0      0
## 70         0      0
## 80         0      0
## 90         0      0
## 100        0      0
## 110        0      0
{% endhighlight %}



{% highlight r %}
# aggregate <U+653C><U+3E63>��<U+653C><U+3E63>��
aggregate(SALARY ~ DEPARTMENT_ID+JOB_ID, emp, sum)
{% endhighlight %}



{% highlight text %}
##    DEPARTMENT_ID     JOB_ID SALARY
## 1            110 AC_ACCOUNT   8300
## 2            110     AC_MGR  12008
## 3             10    AD_ASST   4400
## 4             90    AD_PRES  29040
## 5             90      AD_VP  34000
## 6            100 FI_ACCOUNT  39600
## 7            100     FI_MGR  12008
## 8             40     HR_REP   6500
## 9             60    IT_PROG  28800
## 10            20     MK_MAN  13000
## 11            20     MK_REP   6000
## 12            70     PR_REP  10000
## 13            30   PU_CLERK  13900
## 14            30     PU_MAN  11000
## 15            80     SA_MAN  61000
## 16            80     SA_REP 243500
## 17            50   SH_CLERK  64300
## 18            50   ST_CLERK  55700
## 19            50     ST_MAN  36400
{% endhighlight %}

모양<ec>�� <eb>��<ec>�� <ec>��<ed><98>�<ec>�� <ec>��<eb>��<ed>�� 모양<ec>�� 만들<eb>���<a0> <ed>�� <eb>�� <ec>��<ec>��<ed>��<ec>��.

