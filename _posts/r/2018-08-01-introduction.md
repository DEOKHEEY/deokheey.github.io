---
layout: post
title: "[R] Introduction"
date: "2018-08-01"
excerpt: "R? κ·Έκ² λ­μΌ?"
output: 
  github_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: R
---

# R

<eb>΄μ§λ<eb> AUKLAND <eb><8c><ed><ec> Ross Lhaka, Robert Clifford Gentlemanκ° 1995<eb><ec> κ°λ°<ed> <ec><ed><ed>Έ<ec>¨<ec>΄<ec>΄κ³<a0> <eb>°<ec>΄<ed>° λΆμ<ec> <ec><ed> <ed>΅κ³<84> λ°<8f> κ·Έλ<ed>½<ec>€λ₯<bc> μ§<ec><ed><eb> λ¬΄λ£ <ec><ed><ed>Έ<ec>¨<ec>΄<ec>΄<eb>€.

<br>

## R<ec> <ec>¬<ec>©<ed>΄<ec>Ό <ed><eb> <ec>΄<ec> 

1. R<ec><9d> λ¬΄λ£<ec><ed><ed>Έ<ec>¨<ec>΄<ec>΄<eb>€.
2. <eb>°<ec>΄<ed>°λ₯<bc> λΆμ<ec> <ec><ed>΄<ec> κ°<ec>₯ λ§μ΄ <ec>°<eb> <ed>΅κ³<84> <ed><eb>«<ed>Ό<ec>΄<eb>€.
3. λ³΅μ‘<ed> <eb>°<ec>΄<ed>°λ₯<bc> <eb>€<ec><ed> κ·Έλ<ed>λ‘<9c> <ed><ed><ed>  <ec>κ° <ec><eb>€.
4. λΆμ<ec> <ec><ed> <eb>°<ec>΄<ed>°λ₯<bc> <ec>½κ²<8c> <ec><a0><ec>₯<ed>κ³<a0> μ‘°μ<ed>  <ec> <ec><eb>€.
5. <eb>κ΅¬λ μ§ <ec> <ec>©<ed> <ed>¨<ed>€μ§λ₯<bc> <ec><ec>±<ed>΄<ec> κ³΅μ <ed>  <ec> <ec>κ³<a0> <ec>λ‘μ΄ κΈ°λ₯<ec> <eb><8c><ed> <ec> <eb>¬<ec>΄ λΉ λ₯΄<eb>€.
6. <ec>΄<eb> <ed> OS<ec><ec><eb> <ec>€μΉκ<b0> κ°<eb>₯<ed><eb>€. 

<br>

## R <ec>€μΉ<98>

[R-project](https://www.r-project.org/)
[Rstudio](https://www.rstudio.com/)

***

<br>

## R<ec> κΈ°λ³Έ λ³<ec>

- λ³<ec> <ec>΄λ¦μ<9d> <ec><ed>λ²<b3>, <ec>«<ec>, _, .(λ§μΉ¨<ed>) <ec>¬<ec>©<ed>  <ec> <ec><eb>€.
- λ³<ec> <ec>΄λ¦Όμ μ²«κ<b8><ec><eb> <ec><ed>λ²<b3> <eb><eb> .(λ§μΉ¨<ed>)λ‘<9c> <ec><ec><ed>  <ec> <ec><eb>€.
- .(λ§μΉ¨<ed>)λ‘<9c> <ec><ec> <ed>  κ²½μ°<ec><eb> λ°λ‘ <eb>€<ec> <ec>«<ec>λ₯<bc> <ec><eb> ₯<ed>  <ec> <ec><eb>€.
    - λ³<ec> <ec>΄λ¦μΌλ‘<9c> κ°<eb>₯<ed> <ec>: `a`, `i`, `x2`, `.y`
    - λ³<ec><ec>΄λ¦μΌλ‘<9c> <ec>¬<ec>©<ec>΄ λΆκ<b0><eb>₯<ed> <ec>: `1a`, `.2`, `k-j`


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
# <U+653C><U+3E63> <U+653C><U+3E63>­λ³<U+653C><U+3E63> <U+653C><U+3E64><U+653C><U+3E64> λ°©μ(xλ³<U+653C><U+3E63><U+653C><U+3E62> κΈλ‘λ²λ³<U+653C><U+3E63>μ²λΌ μ²λ¦¬<U+653C><U+3E62><U+653C><U+3E62>€.)
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
# μ§<U+653C><U+3E63>­λ³<U+653C><U+3E63> <U+653C><U+3E64><U+653C><U+3E64> λ°©μ(yλ³<U+653C><U+3E63><U+653C><U+3E62> λ‘μ»¬λ³<U+653C><U+3E63>μ²λΌ μ²λ¦¬<U+653C><U+3E62><U+653C><U+3E62>€.)
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

### <ec>«<ec>(<ec> <ec>, <ec>€<ec>)


{% highlight r %}
x <- 2
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
# λ³<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E64><U+383C><U+3E33><U+653C><U+3E63><U+653C><U+3E63> return<U+653C><U+3E64>΄μ£Όλ method
class(x)
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

R<ec><ec><eb> κΈ°λ³Έ<ec> <ec>Όλ‘<9c> <ec>«<ec>λ₯<bc> <ec>€<ec>λ‘<9c> <ed><ed><ed><eb>€.


{% highlight r %}
y <- 2L
class(y)
{% endhighlight %}



{% highlight text %}
## [1] "integer"
{% endhighlight %}

<eb><8c>λ¬Έμ `L`(RESERVED WORD)<ec> <ec>¬<ec>©<ed>λ©<b4> <ec> <ed><ed>κ²<8c> <ec> <ec>λ‘<9c> <ed><ed><eb><eb>€.


{% highlight r %}
z <- x+y
# class<U+653C><U+3E63><U+393C><U+3E39> λΉμ·<U+653C><U+3E64>κ²<U+383C><U+3E63> <U+653C><U+3E64><U+383C><U+3E33><U+653C><U+3E63>κ³<U+623C><U+3E63> κ°μ <U+653C><U+3E62><U+653C><U+3E63><U+653C><U+3E63> return<U+653C><U+3E64>΄μ€<U+653C><U+3E62>€.
str(z)
{% endhighlight %}



{% highlight text %}
##  num 4
{% endhighlight %}

`is.type`<ec><99> κ°μ<9d> <ed><ec>(`is.numeric`,`is.integer`,`is.character`,`is.logical` <eb>±)<ec><9d> λ³<ec><ec> <ed><83><ec><ec> <ed><ec>Έ<ed><eb> λ°©λ²<ec>Όλ‘<9c> BOOLEAN<ed><ec><ec>Όλ‘<9c> <ed><ed><ed>΄μ€<eb>€.


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

### <ec>«<ec>(μ§<ec><ed>κΈ°λ²)


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

### λ¬Έμ<ec>΄

λ¬Έμ<ec>΄<ec> <ec><eb> ₯<ed>  <eb><eb> ''(Single quation mark)<eb> ""(double quation mark)λ₯<bc> <ec>¬<ec>©<ed>λ©<b4> <eb><eb>€.


{% highlight r %}
s1 <- 'hello'
class(s1)

s2 <- "<U+653C><U+3E63><U+653C><U+3E62><U+653C><U+3E64><U+653C><U+3E63>Έ<U+653C><U+3E63>"
class(s2)

is.character(s2)
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 4
{% endhighlight %}

***

### Boolean(μ§λ¦¬κ°<92>)

`AND`<eb> `&`, `OR`<ec><9d> `|`λ‘<9c> <ed><ed><ed><eb>€.


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
# <U+653C><U+3E63>½<U+653C><U+3E63>΄λ‘λ <U+653C><U+3E64><U+653C><U+3E64><U+653C><U+3E64>  <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E62>€.
T & F
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}

<ed>μ§λ§<8c> <ec>½<ec>΄ <ec>¬<ec>©<ec><9d> λ³<ec>λ‘<9c> <ec> <ec>Έ<eb><ec><ec>Όλ©<b4> <ed>·κ°λ¦΄ <ec> <ec><eb>€. μ²λ¦¬<ed><eb> <ec>°<ec> <ec><ec>κ° μ§λ¦¬κ°λ³΄<eb>€ λ³<ec>κ° <eb> <eb><ec>Όλ―λ‘<9c> <ec>½<ec>΄ <ec>¬<ec>©<ec> μ§<ec><ed><ec>.

***

### NA(Not Available)

κ²°μΈ‘μΉ<98>(κ²°μΈ‘κ°<92>)<ec>Όλ‘<9c> <eb>°<ec>΄<ed>° <ec><eb> ₯ μ€<91> <ec>€<ec>λ‘<9c> κ°μ΄ <ec><eb> ₯<eb>μ§ <ec><eb> κ²½μ°<ec> λ°μ<ed><eb>€. (`NULL`κ³<bc> <eb>€λ¦μ μ£Όμ)


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
# κ²°μΈ‘κ°μ΄ <U+653C><U+3E63><U+653C><U+3E62> λ³<U+653C><U+3E63>λ‘<U+393C><U+3E63> <U+653C><U+3E63>°<U+653C><U+3E63>° <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E64>λ©<U+623C><U+3E34> NAλ‘<U+393C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63><U+653C><U+3E62><U+653C><U+3E62>€.
a+b+c
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}

***

### NULL

`NULL`<ec><9d> Undefinedκ°μ <ed><ed><ed><eb>€. λ³<ec>κ° μ΄κΈ°<ed><eb>μ§ <ec><ec> <eb> <ec>¬<ec>©<ed><eb>€. μ¦<89>, <ec> <ec>Έ <ec><ec> <ec>«<ec>λ₯<bc> <eb>£<ec>μ§ λ¬Έμλ₯<bc> <eb>£<ec>μ§ λͺ¨λ₯΄μ§λ§<8c> λ³<ec>λ₯<bc> <ec> <ec>Έ<ed>κ³<a0> <ec>Ά<ec> <eb> <ec>¬<ec>©<ed><eb>€. (`NA`κ³<bc> <eb>€λ¦μ μ£Όμ) 


{% highlight r %}
# R<U+653C><U+3E63><U+393C><U+3E64> <U+653C><U+3E62><U+383C><U+3E63><U+653C><U+3E63>λ¬Έμλ₯<U+623C><U+3E63> κ΅¬λΆ<U+653C><U+3E64>κΈ°μ <U+653C><U+3E62><U+383C><U+3E63>λ¬Έμ NULL<U+653C><U+3E63> <U+653C><U+3E63>¬<U+653C><U+3E63>©<U+653C><U+3E64>΄<U+653C><U+3E63>Ό <U+653C><U+3E64><U+653C><U+3E62>€.
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

# <U+653C><U+3E63><U+653C><U+3E62> κ²°κ³Όλ₯<U+623C><U+3E63> λ³΄κ³  <U+653C><U+3E64><U+653C><U+3E62><U+653C><U+3E63> κ°μ΄ <U+653C><U+3E63><U+653C><U+3E62>€<U+653C><U+3E62> κ²μ <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63>Ό <U+653C><U+3E64><U+653C><U+3E62>€.
x + y
{% endhighlight %}



{% highlight text %}
## numeric(0)
{% endhighlight %}

***

## <ec>°<ec>°<ec>

### <ec>°<ec> <ec>°<ec>°<ec>

κΈ°λ³Έ <ec>¬μΉμ°<ec>°<ec>΄ κ°<eb>₯<ed><eb>€. 


{% highlight r %}
# λͺ«λ§ μΆμΆ<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63> <U+653C><U+3E63>
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>λ¨Έμγε<U+3E37>λ§<U+383C><U+3E63> μΆμΆ<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63> <U+653C><U+3E63>
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
# κ±°λ­<U+653C><U+3E63> κ³<U+623C><U+3E31>(10**2λ‘λ <U+653C><U+3E63>¬<U+653C><U+3E63>© κ°<U+653C><U+3E62>₯)(μ°Έκ³ , plsql<U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E62> power(10,2))
10^2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}

***

### λΉκ΅<ec>°<ec>°<ec>

`==`(κ°λ€), `!=`(<eb>€λ₯΄λ€), `>`(<ed>¬<eb>€), `<`(<ec><eb>€) <eb>±<ec>Όλ‘<9c> <ed><ed> <ed>  <ec> <ec><eb>€.


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
