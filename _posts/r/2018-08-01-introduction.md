---
layout: post
title: "[R] Introduction"
date: "2018-08-01"
excerpt: "R? 그게 뭐야?"
output: 
  github_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: R
---

# R

<eb>��질랜<eb>�� AUKLAND <eb><8c>�<ed>��<ec>�� Ross Lhaka, Robert Clifford Gentleman가 1995<eb>��<ec>�� 개발<ed>�� <ec>��<ed>��<ed>��<ec>��<ec>��<ec>���<a0> <eb>��<ec>��<ed>�� 분석<ec>�� <ec>��<ed>�� <ed>���<84> �<8f> 그래<ed>��<ec>���<bc> 지<ec>��<ed>��<eb>�� 무료 <ec>��<ed>��<ed>��<ec>��<ec>��<ec>��<eb>��.

<br>

## R<ec>�� <ec>��<ec>��<ed>��<ec>�� <ed>��<eb>�� <ec>��<ec>��

1. R<ec><9d>� 무료<ec>��<ed>��<ed>��<ec>��<ec>��<ec>��<eb>��.
2. <eb>��<ec>��<ed>���<bc> 분석<ec>�� <ec>��<ed>��<ec>�� 가<ec>�� 많이 <ec>��<eb>�� <ed>���<84> <ed>��<eb>��<ed>��<ec>��<eb>��.
3. 복잡<ed>�� <eb>��<ec>��<ed>���<bc> <eb>��<ec>��<ed>�� 그래<ed>���<9c> <ed>��<ed>��<ed>�� <ec>��가 <ec>��<eb>��.
4. 분석<ec>�� <ec>��<ed>�� <eb>��<ec>��<ed>���<bc> <ec>���<8c> <ec><a0>�<ec>��<ed>���<a0> 조작<ed>�� <ec>�� <ec>��<eb>��.
5. <eb>��구든지 <ec>��<ec>��<ed>�� <ed>��<ed>��지�<bc> <ec>��<ec>��<ed>��<ec>�� 공유<ed>�� <ec>�� <ec>���<a0> <ec>��로운 기능<ec>�� <eb><8c>�<ed>�� <ec>��<eb>��<ec>�� 빠르<eb>��.
6. <ec>��<eb>��<ed>�� OS<ec>��<ec>��<eb>�� <ec>��치�<b0>� 가<eb>��<ed>��<eb>��. 

<br>

## R <ec>���<98>

[R-project](https://www.r-project.org/)
[Rstudio](https://www.rstudio.com/)

***

<br>

## R<ec>�� 기본 변<ec>��

- 변<ec>�� <ec>��름�<9d>� <ec>��<ed>���<b3>, <ec>��<ec>��, _, .(마침<ed>��) <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.
- 변<ec>�� <ec>��림의 첫�<b8>�<ec>��<eb>�� <ec>��<ed>���<b3> <eb>��<eb>�� .(마침<ed>��)�<9c> <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.
- .(마침<ed>��)�<9c> <ec>��<ec>�� <ed>�� 경우<ec>��<eb>�� 바로 <eb>��<ec>�� <ec>��<ec>���<bc> <ec>��<eb>��<ed>�� <ec>�� <ec>��<eb>��.
    - 변<ec>�� <ec>��름으�<9c> 가<eb>��<ed>�� <ec>��: `a`, `i`, `x2`, `.y`
    - 변<ec>��<ec>��름으�<9c> <ec>��<ec>��<ec>�� 불�<b0>�<eb>��<ed>�� <ec>��: `1a`, `.2`, `k-j`


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
# <U+653C><U+3E63>��<U+653C><U+3E63>��변<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E64>�� 방식(x변<U+653C><U+3E63>��<U+653C><U+3E62>�� 글로벌변<U+653C><U+3E63>��처럼 처리<U+653C><U+3E62>��<U+653C><U+3E62>��.)
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
# 지<U+653C><U+3E63>��변<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E64>�� 방식(y변<U+653C><U+3E63>��<U+653C><U+3E62>�� 로컬변<U+653C><U+3E63>��처럼 처리<U+653C><U+3E62>��<U+653C><U+3E62>��.)
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

### <ec>��<ec>��(<ec>��<ec>��, <ec>��<ec>��)


{% highlight r %}
x <- 2
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
# 변<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64><U+383C><U+3E33>�<U+653C><U+3E63>��<U+653C><U+3E63>�� return<U+653C><U+3E64>��주는 method
class(x)
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

R<ec>��<ec>��<eb>�� 기본<ec>��<ec>���<9c> <ec>��<ec>���<bc> <ec>��<ec>���<9c> <ed>��<ed>��<ed>��<eb>��.


{% highlight r %}
y <- 2L
class(y)
{% endhighlight %}



{% highlight text %}
## [1] "integer"
{% endhighlight %}

<eb><8c>�문자 `L`(RESERVED WORD)<ec>�� <ec>��<ec>��<ed>���<b4> <ec>��<ed>��<ed>���<8c> <ec>��<ec>���<9c> <ed>��<ed>��<eb>��<eb>��.


{% highlight r %}
z <- x+y
# class<U+653C><U+3E63><U+393C><U+3E39>� 비슷<U+653C><U+3E64>���<U+383C><U+3E63> <U+653C><U+3E64><U+383C><U+3E33>�<U+653C><U+3E63>���<U+623C><U+3E63> 값을 <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63>�� return<U+653C><U+3E64>��준<U+653C><U+3E62>��.
str(z)
{% endhighlight %}



{% highlight text %}
##  num 4
{% endhighlight %}

`is.type`<ec><99>� 같�<9d>� <ed>��<ec>��(`is.numeric`,`is.integer`,`is.character`,`is.logical` <eb>��)<ec><9d>� 변<ec>��<ec>�� <ed><83>�<ec>��<ec>�� <ed>��<ec>��<ed>��<eb>�� 방법<ec>���<9c> BOOLEAN<ed>��<ec>��<ec>���<9c> <ed>��<ed>��<ed>��준<eb>��.


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

### <ec>��<ec>��(지<ec>��<ed>��기법)


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

### 문자<ec>��

문자<ec>��<ec>�� <ec>��<eb>��<ed>�� <eb>��<eb>�� ''(Single quation mark)<eb>�� ""(double quation mark)�<bc> <ec>��<ec>��<ed>���<b4> <eb>��<eb>��.


{% highlight r %}
s1 <- 'hello'
class(s1)

s2 <- "<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E63>��"
class(s2)

is.character(s2)
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 4
{% endhighlight %}

***

### Boolean(진리�<92>)

`AND`<eb>�� `&`, `OR`<ec><9d>� `|`�<9c> <ed>��<ed>��<ed>��<eb>��.


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
# <U+653C><U+3E63>��<U+653C><U+3E63>��로도 <U+653C><U+3E64>��<U+653C><U+3E64>��<U+653C><U+3E64>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
T & F
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}

<ed>��지�<8c> <ec>��<ec>�� <ec>��<ec>��<ec><9d>� 변<ec>���<9c> <ec>��<ec>��<eb>��<ec>��<ec>���<b4> <ed>��갈릴 <ec>�� <ec>��<eb>��. 처리<ed>��<eb>�� <ec>��<ec>��<ec>��<ec>��가 진리값보<eb>�� 변<ec>��가 <eb>�� <eb>��<ec>��므�<9c> <ec>��<ec>�� <ec>��<ec>��<ec>�� 지<ec>��<ed>��<ec>��.

***

### NA(Not Available)

결측�<98>(결측�<92>)<ec>���<9c> <eb>��<ec>��<ed>�� <ec>��<eb>�� �<91> <ec>��<ec>���<9c> 값이 <ec>��<eb>��<eb>��지 <ec>��<eb>�� 경우<ec>�� 발생<ed>��<eb>��. (`NULL`�<bc> <eb>��름을 주의)


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
# 결측값이 <U+653C><U+3E63>��<U+653C><U+3E62>�� 변<U+653C><U+3E63>���<U+393C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64>���<U+623C><U+3E34> NA�<U+393C><U+3E63> <U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>��.
a+b+c
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}

***

### NULL

`NULL`<ec><9d>� Undefined값을 <ed>��<ed>��<ed>��<eb>��. 변<ec>��가 초기<ed>��<eb>��지 <ec>��<ec>�� <eb>�� <ec>��<ec>��<ed>��<eb>��. �<89>, <ec>��<ec>�� <ec>��<ec>�� <ec>��<ec>���<bc> <eb>��<ec>��지 문자�<bc> <eb>��<ec>��지 모르지�<8c> 변<ec>���<bc> <ec>��<ec>��<ed>���<a0> <ec>��<ec>�� <eb>�� <ec>��<ec>��<ed>��<eb>��. (`NA`�<bc> <eb>��름을 주의) 


{% highlight r %}
# R<U+653C><U+3E63><U+393C><U+3E64>� <U+653C><U+3E62><U+383C><U+3E63>�<U+653C><U+3E63>��문자�<U+623C><U+3E63> 구분<U+653C><U+3E64>��기에 <U+653C><U+3E62><U+383C><U+3E63>�문자 NULL<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E62>��.
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

# <U+653C><U+3E63>��<U+653C><U+3E62>�� 결과�<U+623C><U+3E63> 보고 <U+653C><U+3E64>��<U+653C><U+3E62>��<U+653C><U+3E63>�� 값이 <U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>�� 것을 <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E62>��.
x + y
{% endhighlight %}



{% highlight text %}
## numeric(0)
{% endhighlight %}

***

## <ec>��<ec>��<ec>��

### <ec>��<ec>��<ec>��<ec>��<ec>��

기본 <ec>��칙연<ec>��<ec>�� 가<eb>��<ed>��<eb>��. 


{% highlight r %}
# 몫만 추출<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>��머���<U+3E37>��<U+383C><U+3E63> 추출<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
# 거듭<U+653C><U+3E63>���<U+623C><U+3E31>(10**2로도 <U+653C><U+3E63>��<U+653C><U+3E63>�� 가<U+653C><U+3E62>��)(참고, plsql<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E62>�� power(10,2))
10^2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}

***

### 비교<ec>��<ec>��<ec>��

`==`(같다), `!=`(<eb>��르다), `>`(<ed>��<eb>��), `<`(<ec>��<eb>��) <eb>��<ec>���<9c> <ed>��<ed>�� <ed>�� <ec>�� <ec>��<eb>��.


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
