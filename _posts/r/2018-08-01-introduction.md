---
layout: post
title: "[R] Introduction"
date: "2018-08-01"
excerpt: "R? ê·¸ê²Œ ë­ì•¼?"
output: 
  github_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: R
---

# R

<eb>‰´ì§ˆëœ<eb>“œ AUKLAND <eb><8c>€<ed>•™<ec>˜ Ross Lhaka, Robert Clifford Gentlemanê°€ 1995<eb>…„<ec>— ê°œë°œ<ed>•œ <ec>†Œ<ed>”„<ed>Š¸<ec>›¨<ec>–´<ec>´ê³<a0> <eb>°<ec>´<ed>„° ë¶„ì„<ec>„ <ec>œ„<ed>•œ <ed>†µê³<84> ë°<8f> ê·¸ë˜<ed>”½<ec>Š¤ë¥<bc> ì§€<ec>›<ed>•˜<eb>Š” ë¬´ë£Œ <ec>†Œ<ed>”„<ed>Š¸<ec>›¨<ec>–´<ec>´<eb>‹¤.

<br>

## R<ec>„ <ec>‚¬<ec>š©<ed>•´<ec>•¼ <ed>•˜<eb>Š” <ec>´<ec>œ 

1. R<ec><9d>€ ë¬´ë£Œ<ec>†Œ<ed>”„<ed>Š¸<ec>›¨<ec>–´<ec>´<eb>‹¤.
2. <eb>°<ec>´<ed>„°ë¥<bc> ë¶„ì„<ec>„ <ec>œ„<ed>•´<ec>„œ ê°€<ec>¥ ë§ì´ <ec>“°<eb>Š” <ed>†µê³<84> <ed>”Œ<eb>«<ed>¼<ec>´<eb>‹¤.
3. ë³µì¡<ed>•œ <eb>°<ec>´<ed>„°ë¥<bc> <eb>‹¤<ec>–‘<ed>•œ ê·¸ë˜<ed>”„ë¡<9c> <ed>‘œ<ed>˜„<ed>•  <ec>ˆ˜ê°€ <ec>ˆ<eb>‹¤.
4. ë¶„ì„<ec>„ <ec>œ„<ed>•œ <eb>°<ec>´<ed>„°ë¥<bc> <ec>‰½ê²<8c> <ec><a0>€<ec>¥<ed>•˜ê³<a0> ì¡°ì‘<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
5. <eb>ˆ„êµ¬ë“ ì§€ <ec>œ <ec>š©<ed>•œ <ed>Œ¨<ed>‚¤ì§€ë¥<bc> <ec>ƒ<ec>„±<ed>•´<ec>„œ ê³µìœ <ed>•  <ec>ˆ˜ <ec>ˆê³<a0> <ec>ƒˆë¡œìš´ ê¸°ëŠ¥<ec>— <eb><8c>€<ed>•œ <ec> „<eb>‹¬<ec>´ ë¹ ë¥´<eb>‹¤.
6. <ec>–´<eb>– <ed>•œ OS<ec>—<ec>„œ<eb>„ <ec>„¤ì¹˜ê<b0>€ ê°€<eb>Š¥<ed>•˜<eb>‹¤. 

<br>

## R <ec>„¤ì¹<98>

[R-project](https://www.r-project.org/)
[Rstudio](https://www.rstudio.com/)

***

<br>

## R<ec>˜ ê¸°ë³¸ ë³€<ec>ˆ˜

- ë³€<ec>ˆ˜ <ec>´ë¦„ì<9d>€ <ec>•Œ<ed>ŒŒë²<b3>, <ec>ˆ«<ec>, _, .(ë§ˆì¹¨<ed>‘œ) <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
- ë³€<ec>ˆ˜ <ec>´ë¦¼ì˜ ì²«ê<b8>€<ec><eb>Š” <ec>•Œ<ed>ŒŒë²<b3> <eb>˜<eb>Š” .(ë§ˆì¹¨<ed>‘œ)ë¡<9c> <ec>‹œ<ec>‘<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
- .(ë§ˆì¹¨<ed>‘œ)ë¡<9c> <ec>‹œ<ec>‘ <ed>•  ê²½ìš°<ec>—<eb>Š” ë°”ë¡œ <eb>’¤<ec>— <ec>ˆ«<ec>ë¥<bc> <ec>…<eb> ¥<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
    - ë³€<ec>ˆ˜ <ec>´ë¦„ìœ¼ë¡<9c> ê°€<eb>Š¥<ed>•œ <ec>˜ˆ: `a`, `i`, `x2`, `.y`
    - ë³€<ec>ˆ˜<ec>´ë¦„ìœ¼ë¡<9c> <ec>‚¬<ec>š©<ec>´ ë¶ˆê<b0>€<eb>Š¥<ed>•œ <ec>˜ˆ: `1a`, `.2`, `k-j`


{% highlight r %}
x <- 1
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
y <<-2
print(y)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
z = 3
print(z)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63> „<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„ ë°©ì‹(xë³€<U+653C><U+3E63>ˆ˜<U+653C><U+3E62>Š” ê¸€ë¡œë²Œë³€<U+653C><U+3E63>ˆ˜ì²˜ëŸ¼ ì²˜ë¦¬<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.)
sum(x <- c(1,2,3,4,5)) 
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
x
{% endhighlight %}



{% highlight text %}
## [1] 1 2 3 4 5
{% endhighlight %}



{% highlight r %}
# ì§€<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„ ë°©ì‹(yë³€<U+653C><U+3E63>ˆ˜<U+653C><U+3E62>Š” ë¡œì»¬ë³€<U+653C><U+3E63>ˆ˜ì²˜ëŸ¼ ì²˜ë¦¬<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.)
sum(y = c(1,2,3,4,5)) 
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
y
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}

***

### <ec>ˆ«<ec>(<ec> •<ec>ˆ˜, <ec>‹¤<ec>ˆ˜)


{% highlight r %}
x <- 2
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
# ë³€<U+653C><U+3E63>ˆ˜<U+653C><U+3E63>˜ <U+653C><U+3E64><U+383C><U+3E33>€<U+653C><U+3E63>…<U+653C><U+3E63>„ return<U+653C><U+3E64>•´ì£¼ëŠ” method
class(x)
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

R<ec>—<ec>„œ<eb>Š” ê¸°ë³¸<ec> <ec>œ¼ë¡<9c> <ec>ˆ«<ec>ë¥<bc> <ec>‹¤<ec>ˆ˜ë¡<9c> <ed>‘œ<ed>˜„<ed>•œ<eb>‹¤.


{% highlight r %}
y <- 2L
class(y)
{% endhighlight %}



{% highlight text %}
## [1] "integer"
{% endhighlight %}

<eb><8c>€ë¬¸ì `L`(RESERVED WORD)<ec>„ <ec>‚¬<ec>š©<ed>•˜ë©<b4> <ec> •<ed>™•<ed>•˜ê²<8c> <ec> •<ec>ˆ˜ë¡<9c> <ed>‘œ<ed>˜„<eb>œ<eb>‹¤.


{% highlight r %}
z <- x+y
# class<U+653C><U+3E63><U+393C><U+3E39>€ ë¹„ìŠ·<U+653C><U+3E64>•˜ê²<U+383C><U+3E63> <U+653C><U+3E64><U+383C><U+3E33>€<U+653C><U+3E63>…ê³<U+623C><U+3E63> ê°’ì„ <U+653C><U+3E62>™<U+653C><U+3E63>‹œ<U+653C><U+3E63>— return<U+653C><U+3E64>•´ì¤€<U+653C><U+3E62>‹¤.
str(z)
{% endhighlight %}



{% highlight text %}
##  num 4
{% endhighlight %}

`is.type`<ec><99>€ ê°™ì<9d>€ <ed>˜•<ec>‹(`is.numeric`,`is.integer`,`is.character`,`is.logical` <eb>“±)<ec><9d>€ ë³€<ec>ˆ˜<ec>˜ <ed><83>€<ec>…<ec>„ <ed>™•<ec>¸<ed>•˜<eb>Š” ë°©ë²•<ec>œ¼ë¡<9c> BOOLEAN<ed>˜•<ec>‹<ec>œ¼ë¡<9c> <ed>‘œ<ed>˜„<ed>•´ì¤€<eb>‹¤.


{% highlight r %}
is.numeric(z)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
is.integer(y)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}

***

### <ec>ˆ«<ec>(ì§€<ec>ˆ˜<ed>‘œê¸°ë²•)


{% highlight r %}
# 1 * 10^2
1e2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}



{% highlight r %}
# 5 * 10^-1
5e-1
{% endhighlight %}



{% highlight text %}
## [1] 0.5
{% endhighlight %}

***

### ë¬¸ì<ec>—´

ë¬¸ì<ec>—´<ec>„ <ec>…<eb> ¥<ed>•  <eb>•Œ<eb>Š” ''(Single quation mark)<eb>‚˜ ""(double quation mark)ë¥<bc> <ec>‚¬<ec>š©<ed>•˜ë©<b4> <eb>œ<eb>‹¤.


{% highlight r %}
s1 <- 'hello'
class(s1)

s2 <- "<U+653C><U+3E63>•ˆ<U+653C><U+3E62>…•<U+653C><U+3E64>•˜<U+653C><U+3E63>„¸<U+653C><U+3E63>š”"
class(s2)

is.character(s2)
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 4
{% endhighlight %}

***

### Boolean(ì§„ë¦¬ê°<92>)

`AND`<eb>Š” `&`, `OR`<ec><9d>€ `|`ë¡<9c> <ed>‘œ<ed>˜„<ed>•œ<eb>‹¤.


{% highlight r %}
TRUE & TRUE
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
TRUE | FALSE
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>•½<U+653C><U+3E63>–´ë¡œë„ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„<U+653C><U+3E64>•  <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
T & F
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}

<ed>•˜ì§€ë§<8c> <ec>•½<ec>–´ <ec>‚¬<ec>š©<ec><9d>€ ë³€<ec>ˆ˜ë¡<9c> <ec>„ <ec>–¸<eb>˜<ec>—ˆ<ec>œ¼ë©<b4> <ed>—·ê°ˆë¦´ <ec>ˆ˜ <ec>ˆ<eb>‹¤. ì²˜ë¦¬<ed>•˜<eb>Š” <ec>š°<ec>„ <ec>ˆœ<ec>œ„ê°€ ì§„ë¦¬ê°’ë³´<eb>‹¤ ë³€<ec>ˆ˜ê°€ <eb>” <eb>†’<ec>œ¼ë¯€ë¡<9c> <ec>•½<ec>–´ <ec>‚¬<ec>š©<ec>„ ì§€<ec>–‘<ed>•˜<ec>.

***

### NA(Not Available)

ê²°ì¸¡ì¹<98>(ê²°ì¸¡ê°<92>)<ec>œ¼ë¡<9c> <eb>°<ec>´<ed>„° <ec>…<eb> ¥ ì¤<91> <ec>‹¤<ec>ˆ˜ë¡<9c> ê°’ì´ <ec>…<eb> ¥<eb>˜ì§€ <ec>•Š<eb>Š” ê²½ìš°<ec>— ë°œìƒ<ed>•œ<eb>‹¤. (`NULL`ê³<bc> <eb>‹¤ë¦„ì„ ì£¼ì˜)


{% highlight r %}
a <- 100; b <- 90; c <- NA;
is.na(a)
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}



{% highlight r %}
is.na(c)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
# ê²°ì¸¡ê°’ì´ <U+653C><U+3E63>ˆ<U+653C><U+3E62>Š” ë³€<U+653C><U+3E63>ˆ˜ë¡<U+393C><U+3E63> <U+653C><U+3E63>—°<U+653C><U+3E63>‚° <U+653C><U+3E63>‘<U+653C><U+3E63>—…<U+653C><U+3E63>„ <U+653C><U+3E64>•˜ë©<U+623C><U+3E34> NAë¡<U+393C><U+3E63> <U+653C><U+3E64>‘œ<U+653C><U+3E63>‹œ<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.
a+b+c
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}

***

### NULL

`NULL`<ec><9d>€ Undefinedê°’ì„ <ed>‘œ<ed>˜„<ed>•œ<eb>‹¤. ë³€<ec>ˆ˜ê°€ ì´ˆê¸°<ed>™”<eb>˜ì§€ <ec>•Š<ec>„ <eb>•Œ <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. ì¦<89>, <ec>„ <ec>–¸ <ec>‹œ<ec>— <ec>ˆ«<ec>ë¥<bc> <eb>„£<ec>„ì§€ ë¬¸ìë¥<bc> <eb>„£<ec>„ì§€ ëª¨ë¥´ì§€ë§<8c> ë³€<ec>ˆ˜ë¥<bc> <ec>„ <ec>–¸<ed>•˜ê³<a0> <ec>‹¶<ec>„ <eb>•Œ <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. (`NA`ê³<bc> <eb>‹¤ë¦„ì„ ì£¼ì˜) 


{% highlight r %}
# R<U+653C><U+3E63><U+393C><U+3E64>€ <U+653C><U+3E62><U+383C><U+3E63>€<U+653C><U+3E63>†Œë¬¸ìë¥<U+623C><U+3E63> êµ¬ë¶„<U+653C><U+3E64>•˜ê¸°ì— <U+653C><U+3E62><U+383C><U+3E63>€ë¬¸ì NULL<U+653C><U+3E63>„ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•´<U+653C><U+3E63>•¼ <U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
x <- NULL

is.null(x)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
is.na(x)
{% endhighlight %}



{% highlight text %}
## logical(0)
{% endhighlight %}



{% highlight r %}
y <- 100

# <U+653C><U+3E63>•„<U+653C><U+3E62>˜ ê²°ê³¼ë¥<U+623C><U+3E63> ë³´ê³  <U+653C><U+3E64>•˜<U+653C><U+3E62>‚˜<U+653C><U+3E63>˜ ê°’ì´ <U+653C><U+3E63>—†<U+653C><U+3E62>‹¤<U+653C><U+3E62>Š” ê²ƒì„ <U+653C><U+3E63>•Œ<U+653C><U+3E63>•„<U+653C><U+3E63>•¼ <U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
x + y
{% endhighlight %}



{% highlight text %}
## numeric(0)
{% endhighlight %}

***

## <ec>—°<ec>‚°<ec>

### <ec>‚°<ec>ˆ <ec>—°<ec>‚°<ec>

ê¸°ë³¸ <ec>‚¬ì¹™ì—°<ec>‚°<ec>´ ê°€<eb>Š¥<ed>•˜<eb>‹¤. 


{% highlight r %}
# ëª«ë§Œ ì¶”ì¶œ<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63>„ <U+653C><U+3E63>‹œ
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚˜ë¨¸ìãå<U+3E37>€ë§<U+383C><U+3E63> ì¶”ì¶œ<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63>„ <U+653C><U+3E63>‹œ
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
# ê±°ë“­<U+653C><U+3E63> œê³<U+623C><U+3E31>(10**2ë¡œë„ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š© ê°€<U+653C><U+3E62>Š¥)(ì°¸ê³ , plsql<U+653C><U+3E63>—<U+653C><U+3E63>„œ<U+653C><U+3E62>Š” power(10,2))
10^2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}

***

### ë¹„êµ<ec>—°<ec>‚°<ec>

`==`(ê°™ë‹¤), `!=`(<eb>‹¤ë¥´ë‹¤), `>`(<ed>¬<eb>‹¤), `<`(<ec>‘<eb>‹¤) <eb>“±<ec>œ¼ë¡<9c> <ed>‘œ<ed>˜„ <ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
10 != 5 & 10>= 10
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
(10 < 15) | (10 == 5)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}

***
