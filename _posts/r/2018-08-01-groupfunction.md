---
layout: post
title: "[R] Group Function"
date: "2018-08-01"
excerpt: "R<ec>—<ec>„œ<ec>˜ ê·¸ë£¹<ed>•¨<ec>ˆ˜"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, groupfunction]
---

## ê¸°ë³¸ ê·¸ë£¹<ed>•¨<ec>ˆ˜


{% highlight r %}
x <- c(100,90,80,70)

# <U+653C><U+3E64>•©
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>‰ê·ãå<U+3E30>
mean(x)
{% endhighlight %}



{% highlight text %}
## [1] 85
{% endhighlight %}



{% highlight r %}
# ë¶„ì‚°
var(x)
{% endhighlight %}



{% highlight text %}
## [1] 166.6667
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>‘œì¤€<U+653C><U+3E64>¸ì°ãå<U+3E38>
sd(x)
{% endhighlight %}



{% highlight text %}
## [1] 12.90994
{% endhighlight %}



{% highlight r %}
# ìµœë<U+383C><U+3E63>€ê°<U+393C><U+3E32>
max(x)
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}



{% highlight r %}
# ìµœì†Œê°<U+393C><U+3E32>
min(x)
{% endhighlight %}



{% highlight text %}
## [1] 70
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>–‰<U+653C><U+3E63>˜ ê°œìˆ˜
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 4   NROW(x): 4"
{% endhighlight %}

ê²°ì¸¡ì¹<98>(`NA`)ê°€ <ec>ˆ<eb>Š” ê²½ìš° `na.rm`<ec>´<eb>¼<eb>Š” option<ec>„ <ec>¨<ec>•¼ì§€ë§<8c> <ed>•¨<ec>ˆ˜ë¥<bc> <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
x <- c(100,90,80,70,NA)

# Option<U+653C><U+3E63>„ <U+653C><U+3E63>„¤<U+653C><U+3E63> •<U+653C><U+3E64>•˜ì§€ <U+653C><U+3E63>•Š<U+653C><U+3E63><U+393C><U+3E64>€ ê²½ìš°
sum(x)
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}



{% highlight r %}
# Option <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©
sum(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 340
{% endhighlight %}



{% highlight r %}
#<U+653C><U+3E62>‹¤ë¥<U+623C><U+3E38> ê·¸ë£¹<U+653C><U+3E64>•¨<U+653C><U+3E63>ˆ˜<U+653C><U+3E62>„ ë§ˆì°¬ê°€ì§€<U+653C><U+3E63>´<U+653C><U+3E62>‹¤.
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
# <U+653C><U+3E64>•˜ì§€ë§<U+383C><U+3E63> length()<U+653C><U+3E62>‚˜ NROW()<U+653C><U+3E62>Š” <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•  <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
paste('length(x):',length(x)," ",'NROW(x):',NROW(x))
{% endhighlight %}



{% highlight text %}
## [1] "length(x): 5   NROW(x): 5"
{% endhighlight %}



{% highlight r %}
# ê²°ì¸¡ì¹<U+393C><U+3E38>(NA)ë¥<U+623C><U+3E63> <U+653C><U+3E63> œ<U+653C><U+3E63>™¸<U+653C><U+3E63>‹œ<U+653C><U+3E64>‚¤ê³ãå<U+3E30> <U+653C><U+3E64>–‰<U+653C><U+3E63>˜ <U+653C><U+3E63>ˆ˜ë¥<U+623C><U+3E63> <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•˜<U+653C><U+3E62> ¤ë©<U+623C><U+3E34> <U+653C><U+3E62>‹¤<U+653C><U+3E63>Œê³<U+623C><U+3E63> ê°™ì´ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
length(na.omit(x))
{% endhighlight %}



{% highlight text %}
## [1] 4
{% endhighlight %}

> <ec>—¬ê¸°ì„œ ì£¼ì˜<ed>•  <ec> <ec><9d>€ `na.rm`<ec>„ `TRUE`ë¡<9c> <ec>„¤<ec> •<ed>•˜ë©<b4> <ed>‰ê·<a0>, ë¶„ì‚°, <ed>‘œì¤€<ed>¸ì°¨ëŠ” ê²°ì¸¡ì§€ë¥<bc> <ec> œ<ec>™¸<ed>•œ ê°’ì´<eb>‹¤. ê·¸ëŸ¬ë©<b4> ê²°ê³¼ì¹˜ê<b0>€ <eb>‹¬<eb>¼ì§<88> <ec>ˆ˜ <ec>ˆ<ec>œ¼<eb>‹ˆ ê²°ì¸¡ì¹˜ë<a5><bc> 0<ec>œ¼ë¡<9c> ë°”ê¾¸ê±°ë‚˜<ed>•´<ec>„œ <ec>‚¬<ec>š©<ed>•˜<ec>—¬<ec>•¼ <ed>•œ<eb>‹¤.

### aggregate(): ê·¸ë£¹ ì§€<ec>–´ì£¼ëŠ” <ed>•¨<ec>ˆ˜

<eb>°<ec>´<ed>„°ë¥<bc> ë¶„í• <ed>•˜ê³<a0> ê°<81> ê·¸ë£¹<ec>œ¼ë¡<9c> ë¬¶ì<9d>€ <ed>›„ ê·¸ë£¹<ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ec>‹œì¼œì£¼<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤. `aggregate(ê³„ì‚°<eb>  ì»¬ëŸ¼ ~ ë¶„í• <ed>•´<ec>•¼ <ed>•  ê¸°ì<a4>€ ì»¬ëŸ¼, <eb>°<ec>´<ed>„°, <ed>•¨<ec>ˆ˜)` ë¡<9c> <ec>‚¬<ec>š©<ed>•œ<eb>‹¤.


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
# sqlë¡<U+393C><U+3E63> <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„<U+653C><U+3E64>•˜ë©<U+623C><U+3E34> <U+653C><U+3E62>‹¤<U+653C><U+3E63>Œê³<U+623C><U+3E63> ê°™ë‹¤.
#
# SELECT job_id, sum(salary)
# FROM employees
# GROUP BY job_id;
{% endhighlight %}

***

## 2,3ì°¨ì› <eb>°<ec>´<ed>„° <ed>•¨<ec>ˆ˜

### apply(): <ed>•¨<ec>ˆ˜ ê²°ê³¼ë¥<bc> ë°˜í™˜<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

<ed>–‰<eb> ¬, ë°°ì—´, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>— <ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•œ ê²°ê³¼ë¥<bc> ë²¡í„°, ë¦¬ìŠ¤<ed>Š¸, ë°°ì—´ <ed>˜•<ed>ƒœë¡<9c> ë¦¬í„´<ed>•œ<eb>‹¤. <ed>–‰<eb> ¬<ec>—<ec>„œ <ed>–‰<ec>´<eb>‚˜ <ec>—´<ec>˜ ë°©í–¥<ec>œ¼ë¡<9c> <ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•œ<eb>‹¤.

    `apply(x, MARGIN, FUN)`  
    
    `x`: <ed>–‰<eb> ¬, ë°°ì—´, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„
    `MARGIN`: <ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•  <eb>•Œ ë°©í–¥<ec>„ ì§€<ec> •
              `1`: <ed>–‰ë°©í–¥, `2`: <ec>—´ë°©í–¥, `c(1,2)`: <ed>–‰ê³<bc> <ec>—´ ë°©í–¥<ec>´<eb>¼<eb>Š” <ec>˜ë¯<b8>
    `FUN`: <ec> <ec>š©<ed>•  <ed>•¨<ec>ˆ˜(`sum`,`mean`,`var`,`sd`,`max`,`min`)


<ec>˜ˆ<ec> œë¥<bc> <ed><92>€<ec>–´ë³´ì.


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
# <U+653C><U+3E64>–‰<U+653C><U+3E62> ¬ <U+653C><U+3E63>‚¬<U+653C><U+3E63>´ì¦<U+383C><U+3E38> <U+653C><U+3E64>™•<U+653C><U+3E63>¸
dim(m)
{% endhighlight %}



{% highlight text %}
## [1] 2 2
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>–‰ ë°©í–¥<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> sum
apply(m, 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 4 6
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>—´ ë°©í–¥<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> sum
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
# 1<U+653C><U+3E63>—´<U+653C><U+3E63>„ <U+653C><U+3E63> œ<U+653C><U+3E63>™¸<U+653C><U+3E64>•˜ê³ãå<U+3E30> ëª¨ë“  <U+653C><U+3E64>–‰<U+653C><U+3E63>„ sum
apply(df[,c(2:3)], 1, sum)
{% endhighlight %}



{% highlight text %}
## [1] 165  NA  NA
{% endhighlight %}



{% highlight r %}
# NAê°<U+393C><U+3E32> <U+653C><U+3E63> œ<U+653C><U+3E63>™¸ <U+653C><U+3E64>›„ sum
apply(df[,c(2:3)], 1, sum, na.rm = T)
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}



{% highlight r %}
# 1<U+653C><U+3E63>—´<U+653C><U+3E63>„ <U+653C><U+3E63> œ<U+653C><U+3E63>™¸<U+653C><U+3E64>•˜ê³ãå<U+3E30> ëª¨ë“  <U+653C><U+3E63>—´<U+653C><U+3E63>„ mean
apply(df[,c(2:3)], 2, mean)
{% endhighlight %}



{% highlight text %}
##    sql python 
##     NA     NA
{% endhighlight %}



{% highlight r %}
# NAê°<U+393C><U+3E32> <U+653C><U+3E63> œ<U+653C><U+3E63>™¸<U+653C><U+3E64>•œ mean 
apply(df[,c(2:3)], 2, mean, na.rm = T)
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

> ì£¼ì˜. <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„, ë°°ì—´, <ed>–‰<eb> ¬<ec>˜ <ed>˜•<ec>‹<ec>—<ec>„œ `apply()`ë¥<bc> <ec>‚¬<ec>š©<ed>•  <eb>•Œ <eb>‹¨<ec>¼ ì»¬ëŸ¼<ec><9d>€ `apply()`ë¥<bc> <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>—†<eb>‹¤. <ed>–‰<ec>—´, ë°°ì—´, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>˜ ëª¨ì–‘<ec>œ¼ë¡<9c> ë§Œë“¤<ec>–´ ì£¼ì–´<ec>•¼ `apply()` <ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.

***

### rowSums(): <ed>–‰<ec>˜ <ed>•©


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowSums(df[,2:3], na.rm = T) # apply(df[,2:3],1, sum, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
{% endhighlight %}



{% highlight text %}
## [1] 165  90  70
{% endhighlight %}

### rowMeans(): <ed>–‰<ec>˜ <ed>‰ê·<a0>


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

rowMeans(df[,2:3], na.rm = T) # apply(df[,2:3],1, mean, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
{% endhighlight %}



{% highlight text %}
## [1] 82.5 90.0 70.0
{% endhighlight %}

***

### colSums(): <ec>—´<ec>˜ <ed>•©


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colSums(df[,2:3], na.rm = T) # apply(df[,2:3],2, sum, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
{% endhighlight %}



{% highlight text %}
##    sql python 
##    160    165
{% endhighlight %}

### colMeans(): <ec>—´<ec>˜ <ed>‰ê·<a0>


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

colMeans(df[,2:3], na.rm = T) # apply(df[,2:3],2, mean, na.rm = T) <U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}

***

### lapply(): <ed>•¨<ec>ˆ˜ ê²°ê³¼ë¥<bc> ë¦¬ìŠ¤<ed>Š¸ë¡<9c> ë¦¬í„´<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

ë²¡í„°, ë¦¬ìŠ¤<ed>Š¸, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>— <ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•˜ê³<a0> ê·<b8> ê²°ê³¼ë¥<bc> ë¦¬ìŠ¤<ed>Š¸ë¡<9c> ë¦¬í„´<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤. (ë¦¬ìŠ¤<ed>Š¸<ed>˜•: <ec>„œë¡<9c> <eb>‹¤ë¥<b8> <eb>°<ec>´<ed>„°<ed><83>€<ec>…<ec>— ê°’ì„ <ec><a0>€<ec>¥<ed>•˜<eb>Š” <ec>ë£Œí˜•)


{% highlight r %}
x <- list(a = 1:3, b = 4:6)

# <U+653C><U+3E64>‰ê· ì„ êµ¬í•  <U+653C><U+3E62>•Œ mean<U+653C><U+3E63>„ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•˜ë©<U+623C><U+3E34> <U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.
mean(x$a); mean(x$b);
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight text %}
## [1] 5
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>•˜ì§€ë§<U+383C><U+3E63> lapplyë¥<U+623C><U+3E63> <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•˜ë©<U+623C><U+3E34> <U+653C><U+3E63>œ„ë¥<U+623C><U+3E63> <U+653C><U+3E64>•œë²ˆì— <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•  <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
lapply(x,mean)
{% endhighlight %}



{% highlight text %}
## $a
## [1] 2
## 
## $b
## [1] 5
{% endhighlight %}

<ec>•„<eb>˜ ì½”ë“œë¥<bc> ë¹„êµ<ed>•´ë³´ì.


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
apply(df[,2:3],2, mean, na.rm = T) # unlist(lapply(df[,2:3], mean, na.rm = T)) <U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
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

ì¶œë ¥<ec><9d>€ ê°™ë‹¤. <ec>ë£Œí˜•<ec>— <eb>”°<eb>¼ <ec>›<ed>•˜<eb>Š” ê²ƒì„ <ec>‚¬<ec>š©<ed>•˜<ec>.


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

#### ì°¸ê³ . <ec>ë£Œí˜•<eb>°<ec>´<ed>„°<ec>˜ ë³€<ed>™˜

ë¦¬ìŠ¤<ed>Š¸ë¥<bc> <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>œ¼ë¡<9c> ë°”ê¿”<ec>•¼ <ed>•  ê²½ìš°ê°€ <ec>ˆ<eb>‹¤. ê·¸ëŸ¬ë©<b4> `as.data.frame()`<ec>„ <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤. ë°”ë€Œì–´ ì§„ë‹¤ë©<b4> <ec>•„ì£<bc> HAPPY<ed>•œ ê²½ìš°<eb>‹¤.


{% highlight r %}
as.data.frame(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

<ec>´<ec><99>€ ê°™ì´ <ec>ˆ˜<ed>–‰<ed>•  <ec>ˆ˜ <ec>ˆ<ec>œ¼<eb>‚˜ <ec>•ˆ<eb>˜<eb>Š” ê²½ìš°ê°€ <ec>ˆ<eb>‹¤. ê·¸ëŸ´ ê²½ìš°<ec>—<eb>Š” <eb>‹¤<ec>Œ<ec>˜ <eb>‹¨ê³„ë<a5><bc> ê±°ì³<ec>„œ <ec>ˆ˜<ed>–‰<ed>•˜<ec>—¬<ec>•¼ <ed>•œ<eb>‹¤.


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))


# 1. ë¦¬ìŠ¤<U+653C><U+3E64>Š¸ë¥<U+623C><U+3E63> ë²¡í„°<U+653C><U+3E64>˜•<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
unlist(lapply(df[,2:3], mean, na.rm = T))
{% endhighlight %}



{% highlight text %}
##    sql python 
##   80.0   82.5
{% endhighlight %}



{% highlight r %}
# 2. ë²¡í„°<U+653C><U+3E64>˜•<U+653C><U+3E63>„ ë§¤íŠ¸ë¦ãå<U+3E64><U+653C><U+3E63>Š¤<U+653C><U+3E64>˜•ë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE)
{% endhighlight %}



{% highlight text %}
##      [,1] [,2]
## [1,]   80 82.5
{% endhighlight %}



{% highlight r %}
# 3. ë§¤íŠ¸ë¦ãå<U+3E64><U+653C><U+3E63>Š¤<U+653C><U+3E64>˜•<U+653C><U+3E63>„ <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„°<U+653C><U+3E64>”„<U+653C><U+3E62> ˆ<U+653C><U+3E63>„<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
x <- as.data.frame(matrix(unlist(lapply(df[,2:3], mean, na.rm = T)),ncol=2, byrow = TRUE))
names(x) <- c('sql','python')

# êµ¬ì¡° <U+653C><U+3E64>™•<U+653C><U+3E63>¸
str(x)
{% endhighlight %}



{% highlight text %}
## 'data.frame':	1 obs. of  2 variables:
##  $ sql   : num 80
##  $ python: num 82.5
{% endhighlight %}



{% highlight r %}
class(x) # <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„°<U+653C><U+3E62>Š” data.frame<U+653C><U+3E64>˜• 
{% endhighlight %}



{% highlight text %}
## [1] "data.frame"
{% endhighlight %}



{% highlight r %}
mode(x) # <ec>† <ec>•ˆ<ec><9d>€ <ec>„œë¡<9c> <eb>‹¤ë¥<b8> <ed>˜•<ec>´ <ec>ˆ<ec>–´<ec>„œ list<ed>˜•<ec>´<eb>‹¤.
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}

***

### sapply(): <ed>•¨<ec>ˆ˜ ê²°ê³¼ë¥<bc> ë²¡í„°ë¡<9c> ë¦¬í„´<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

ë²¡í„°, ë¦¬ìŠ¤<ed>Š¸, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>— <ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•˜ê³<a0> ê·<b8> ê²°ê³¼ë¥<bc> ë²¡í„°ë¡<9c> ë¦¬í„´<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜


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

<ec>œ„ <eb>°<ec>´<ed>„°ë¥<bc> <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>œ¼ë¡<9c> ë°”ê¾¸<ec>–´ë³´ì


{% highlight r %}
df <- data.frame(name = c('king','smith','jane'),
                 sql = c(90,NA,70),
                 python = c(75,90,NA))

x <- sapply(df[,2:3], mean, na.rm = T)

# 1. ë§¤íŠ¸ë¦ãå<U+3E64><U+653C><U+3E63>Š¤<U+653C><U+3E64>˜•<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
x <- matrix(x, ncol = 2, byrow=TRUE)

# 2. <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„°<U+653C><U+3E64>”„<U+653C><U+3E62> ˆ<U+653C><U+3E63>„<U+653C><U+3E64>˜• ë³€<U+653C><U+3E64>™˜
x <- as.data.frame(x)
names(x) <- c('sql','python')
x
{% endhighlight %}



{% highlight text %}
##   sql python
## 1  80   82.5
{% endhighlight %}

***


### tapply(): ê·¸ë£¹<ed>•‘ <ed>›„ ê²°ê³¼ë¥<bc> ë¦¬í„´

ë²¡í„°, <eb>°<ec>´<ed>„°<ed>”„<eb> ˆ<ec>„<ec>— <ec><a0>€<ec>¥<eb>œ <eb>°<ec>´<ed>„°ë¥<bc> ì£¼ì–´ì§<84> ê¸°ì<a4>€<ec>— <eb>”°<eb>¼ ê·¸ë£¹<ec>œ¼ë¡<9c> ë¬¶ì<9d>€ <eb>’¤ ê·¸ë£¹<ed>•¨<ec>ˆ˜ë¥<bc> <ec> <ec>š©<ed>•˜ê³<a0> ê·<b8> ê²°ê³¼ë¥<bc> array<ed>˜•<ec>œ¼ë¡<9c> ë¦¬í„´<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜


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
# aggregate()<U+653C><U+3E63><U+393C><U+3E39>€ ë¹„ìŠ·<U+653C><U+3E64>•˜<U+653C><U+3E62>‹¤.
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


<ec>—¬<eb>Ÿ¬ ì»¬ëŸ¼<ec>„ ê¸°ì<a4>€<ec>œ¼ë¡<9c> Grouping<ec>„ <ed>•˜<eb> ¤ë©<b4> `list`<ed>˜•<ec>œ¼ë¡<9c> ì»¬ëŸ¼<ec>„ ë¬¶ì–´<ec>„œ <ed>•¨<ec>ˆ˜<ec>— <eb>„£<ec>–´ì£¼ì–´<ec>•¼ <ed>•œ<eb>‹¤.
  

{% highlight r %}
# vector<U+653C><U+3E64>˜•<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë¬¶ì„ <U+653C><U+3E63>‹œ error ë°œìƒ
tapply(emp$SALARY, c(emp$DEPARTMENT_ID,emp$JOB_ID), sum)
{% endhighlight %}



{% highlight text %}
## Error in tapply(emp$SALARY, c(emp$DEPARTMENT_ID, emp$JOB_ID), sum): ÀÎÀÚµéÀº ¹İµå½Ã °°Àº ±æÀÌ¸¦ °¡Á®¾ß ÇÕ´Ï´Ù
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
# ê²°ì¸¡ì¹˜ëãå<U+3E35><U+623C><U+3E63> 0<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ì¹˜í™˜
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
# aggregate <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©
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

ëª¨ì–‘<ec>„ <eb>ˆˆ<ec>— <ec>µ<ed><98>€<ec>„œ <ec>´<eb>Ÿ¬<ed>•œ ëª¨ì–‘<ec>„ ë§Œë“¤<eb> ¤ê³<a0> <ed>•  <eb>•Œ <ec>‚¬<ec>š©<ed>•˜<ec>.

