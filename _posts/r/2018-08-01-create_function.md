---
layout: post
title: "[R] <ed>¨<ec> <ec><ec>±"
date: "2018-08-01"
excerpt: "<ec>΄<ec>  μ§μ  <ed>¨<ec>λ₯<bc> λ§λ€<ec>΄ λ³΄μ"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## <ed>¨<ec>

-<ec>¬<ec>©<ec>κ° <ec> <ec><ed><eb> <ed>¨<ec>λ₯<bc> <ec><ec>±<ed>  <ec> <ec><eb>€.
-<ec>μ£<bc> λ°λ³΅<eb><ec>΄ <ec>¬<ec>©<ed><eb> κΈ°λ₯<ec> <ec> <ec><ed><eb> <ed>λ‘κ·Έ<eb>¨
-μ½λκ° κ°λ¨<ed>΄μ§λ€.
-DBκ° <ec><eb>κΈ°λλ¬Έμ <ec>¬<ec>©<ec>λ§λ€ λ§λ€<ec>΄μ£Όμ΄<ec>Ό <ed><eb>€.
-<eb>€<ec>κ³<bc> κ°μ΄ <ed>¨<ec>λ₯<bc> <ec> <ec>Έ<ed><eb>€.

```
<ed>¨<ec><ec>΄λ¦<84> <- function(){
              <ec><ed><ed>΄<ec>Ό <ed>  μ½λ
              return(λ³<ed>κ°<92>) # Optional
}
```
***

### <ed>¨<ec><ec> <ec><ec>±

κ°λ¨<ed> <ed>¨<ec>λ₯<bc> λ§λ€<ec>΄ λ³΄μ


{% highlight r %}
date1 <- function(){
  
  return(Sys.Date())

}

date1()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08"
{% endhighlight %}

<br>


{% highlight r %}
time <- function(){
  
  Sys.time()
  
}

time()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:34:28 KST"
{% endhighlight %}

<br>


{% highlight r %}
hap <- function(x,y){ # Parameter 2κ°<U+393C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63>Έ
  
  res <- x+y # Local variable <U+653C><U+3E63> <U+653C><U+3E63>Έ
  return(res)
  
}

hap(1,2)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}


***
  
### κ°λ³ <ec>Έ<ec><ec> <ed>¨<ec>

<ec><eb> <ec><ec>λ₯<bc> <ec>΄<ed>΄λ³΄μ. κ°λ³ <ec>Έ<ec><eb> `...`<ec>Όλ‘<9c> <ed><ed><ed><ec>¬ <ed>¨<ec>λ₯<bc> λ§λ€λ©<b4> <eb><eb>€.


{% highlight r %}
f <- function(...){
  x <- list(...) # Vectorλ‘<U+393C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63>Έ<U+653C><U+3E64><U+653C><U+3E63>¬<U+653C><U+3E62> <U+653C><U+3E63>κ΄ <U+653C><U+3E63><U+653C><U+3E63>
  for(i in x){
    print(i)
  }
}

f(1,2)
{% endhighlight %}



{% highlight text %}
## [1] 1
## [1] 2
{% endhighlight %}



{% highlight r %}
f(1,2,3)
{% endhighlight %}



{% highlight text %}
## [1] 1
## [1] 2
## [1] 3
{% endhighlight %}



{% highlight r %}
f('a','b','c','d')
{% endhighlight %}



{% highlight text %}
## [1] "a"
## [1] "b"
## [1] "c"
## [1] "d"
{% endhighlight %}

***

### μ€μ²© <ed>¨<ec>

<ed>¨<ec><ec><ec> <ed>¨<ec>λ₯<bc> λ§λ€<ec>΄<ec> <ec>¬<ec>©<ed>  <ec> <ec><eb>€.


{% highlight r %}
f <- function(x,y){
  print(x)
  f2 <- function(y){
    y <- x*y
    print(y)
  }
  f2(y)
}

f(10,20)
{% endhighlight %}



{% highlight text %}
## [1] 10
## [1] 200
{% endhighlight %}

***

### λ³<ec><ec> <eb>°λ₯<b8> <ed> <eb>Ή<ec>°<ec>°<ec> <ec>¬<ec>©


`<ec> <ec>­λ³<ec>(Global Variable)`: <ed>¨<ec><ec> <ec>κ΄<ec><ec>΄ <ed>λ‘κ·Έ<eb>¨ <ec> μ²΄μ<ec> <ec>¬<ec>©<ed>  <ec> <ec><eb> λ³<ec>

`μ§<ec>­λ³<ec>(Local Variable)`: <ed>¨<ec><eb>΄<ec><ec> <ec> <ec><eb>κ³<a0> <ec>¬<ec>©<ed><eb> λ³<ec>

`λ§€κ°λ³<ec>(Parameter Variable`: <ed>¨<ec><ec> <ec>Έ<ec><ec><ec> λ°μ<ec> <ec>¬<ec>©<ed><eb> λ³<ec>

<br>

<ec><eb> μ½λλ₯<bc> λ³΄κ³  μ§<ec>­λ³<ec><ec><99> <ec> <ec>­λ³<ec>λ₯<bc> κ΅¬λΆ<ed>κ³<a0> <ed> <eb>Ή<ec>°<ec>°<ec>λ₯<bc> <ec>¬<ec>©<ec> μ£Όμλ₯<bc> <ed><ec>.


{% highlight r %}
x<-1; y<-2; z<-3;

f <- function(x){
  y <- x*10 # Local variable
  print(x); print(y); print(z)
}

f(x)
{% endhighlight %}



{% highlight text %}
## [1] 1
## [1] 10
## [1] 3
{% endhighlight %}



{% highlight r %}
x; y; z
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}


{% highlight r %}
x<-1; y<-2; z<-3;

f <- function(x){
  y = x*10 # Local variable
  print(x); print(y); print(z)
}

f(x)
{% endhighlight %}



{% highlight text %}
## [1] 1
## [1] 10
## [1] 3
{% endhighlight %}



{% highlight r %}
x; y; z
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

<ed> <eb>Ή<ec>°<ec>°<ec> `<-`<ec><99> `=`<eb> μ§<ec>­λ³<ec><ec> <ed> <eb>Ή<ec> <ed>΄μ£Όμ΄<ec> <ec>¬<ec>©<ed><eb>€. <ed>μ§λ§<8c> `<<-`λ₯<bc> <ec>¬<ec>©<ed>λ©<b4> <ec> <ec>­λ³<ec><ec> <ed> <eb>Ή<eb>¨<ec> μ£Όμ<ed><ec>.


{% highlight r %}
x<-1; y<-2; z<-3;

f <- function(x){
  y <<- x*10 # Global variable y<U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E64>₯<U+653C><U+3E63> μ€<U+383C><U+3E63>
  print(x); print(y); print(z)
}

f(x)
{% endhighlight %}



{% highlight text %}
## [1] 1
## [1] 10
## [1] 3
{% endhighlight %}



{% highlight r %}
x; y; z
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight text %}
## [1] 10
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

<br>

#### μ°Έκ³ 

<eb>€λ₯<b8> <ed>λ‘κ·Έ<eb>¨κ³<bc> <eb>¬λ¦<ac> R<ec><9d> μ§<ec>­λ³<ec><ec><99> <ec> <ec>­λ³<ec>κ° <ec> <ec>Έ<eb>  <eb> μ°¨μ΄κ° <ec><eb>€.


{% highlight r %}
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
sum(x <- c(1,2,3,4,5))
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
y
{% endhighlight %}



{% highlight text %}
## [1] 10
{% endhighlight %}

`<-`<eb> μ§<ec>­λ³<ec> <ed> <eb>Ή<ec><ec>΄μ§λ§<8c> `<<-`<ec><99> κ°μ΄ λ³<ec>λ₯<bc> <ec><ec>±<ed>΄μ€<eb>€. λ°λ©΄ `=`<eb> κ·Έλ μ§ <ec><eb>€.


{% highlight r %}
sum(x <- c(1,2,3,4,5))
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
z
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

<ec><eb>¬κ° λ°μ<ed><eb>€. `<-`λ³΄λ€ `=`κ° <eb> λͺν<ed> μ§<ec>­λ³<ec> <ed> <eb>Ή<ec><eb>Ό<eb> <ec> <ec> κΈ°μ΅<ed>΄<eb><ec>.
