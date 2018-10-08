---
layout: post
title: "[R] <ed>��<ec>�� <ec>��<ec>��"
date: "2018-08-01"
excerpt: "<ec>��<ec>�� 직접 <ed>��<ec>���<bc> 만들<ec>�� 보자"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## <ed>��<ec>��

-<ec>��<ec>��<ec>��가 <ec>��<ec>��<ed>��<eb>�� <ed>��<ec>���<bc> <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.
-<ec>���<bc> 반복<eb>��<ec>�� <ec>��<ec>��<ed>��<eb>�� 기능<ec>�� <ec>��<ec>��<ed>��<eb>�� <ed>��로그<eb>��
-코드가 간단<ed>��진다.
-DB가 <ec>��<eb>��기때문에 <ec>��<ec>��<ec>��마다 만들<ec>��주어<ec>�� <ed>��<eb>��.
-<eb>��<ec>���<bc> 같이 <ed>��<ec>���<bc> <ec>��<ec>��<ed>��<eb>��.

```
<ed>��<ec>��<ec>���<84> <- function(){
              <ec>��<ed>��<ed>��<ec>�� <ed>�� 코드
              return(변<ed>���<92>) # Optional
}
```
***

### <ed>��<ec>��<ec>�� <ec>��<ec>��

간단<ed>�� <ed>��<ec>���<bc> 만들<ec>�� 보자


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
hap <- function(x,y){ # Parameter 2�<U+393C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��
  
  res <- x+y # Local variable <U+653C><U+3E63>��<U+653C><U+3E63>��
  return(res)
  
}

hap(1,2)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}


***
  
### 가변 <ec>��<ec>��<ec>�� <ed>��<ec>��

<ec>��<eb>�� <ec>��<ec>���<bc> <ec>��<ed>��보자. 가변 <ec>��<ec>��<eb>�� `...`<ec>���<9c> <ed>��<ed>��<ed>��<ec>�� <ed>��<ec>���<bc> 만들�<b4> <eb>��<eb>��.


{% highlight r %}
f <- function(...){
  x <- list(...) # Vector�<U+393C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E62>�� <U+653C><U+3E63>��관 <U+653C><U+3E63>��<U+653C><U+3E63>��
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

### 중첩 <ed>��<ec>��

<ed>��<ec>��<ec>��<ec>�� <ed>��<ec>���<bc> 만들<ec>��<ec>�� <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.


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

### 변<ec>��<ec>�� <eb>���<b8> <ed>��<eb>��<ec>��<ec>��<ec>�� <ec>��<ec>��


`<ec>��<ec>��변<ec>��(Global Variable)`: <ed>��<ec>��<ec>�� <ec>��관<ec>��<ec>�� <ed>��로그<eb>�� <ec>��체에<ec>�� <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>�� 변<ec>��

`지<ec>��변<ec>��(Local Variable)`: <ed>��<ec>��<eb>��<ec>��<ec>�� <ec>��<ec>��<eb>���<a0> <ec>��<ec>��<ed>��<eb>�� 변<ec>��

`매개변<ec>��(Parameter Variable`: <ed>��<ec>��<ec>�� <ec>��<ec>��<ec>��<ec>�� 받아<ec>�� <ec>��<ec>��<ed>��<eb>�� 변<ec>��

<br>

<ec>��<eb>�� 코드�<bc> 보고 지<ec>��변<ec>��<ec><99>� <ec>��<ec>��변<ec>���<bc> 구분<ed>���<a0> <ed>��<eb>��<ec>��<ec>��<ec>���<bc> <ec>��<ec>��<ec>�� 주의�<bc> <ed>��<ec>��.


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

<ed>��<eb>��<ec>��<ec>��<ec>�� `<-`<ec><99>� `=`<eb>�� 지<ec>��변<ec>��<ec>�� <ed>��<eb>��<ec>�� <ed>��주어<ec>�� <ec>��<ec>��<ed>��<eb>��. <ed>��지�<8c> `<<-`�<bc> <ec>��<ec>��<ed>���<b4> <ec>��<ec>��변<ec>��<ec>�� <ed>��<eb>��<eb>��<ec>�� 주의<ed>��<ec>��.


{% highlight r %}
x<-1; y<-2; z<-3;

f <- function(x){
  y <<- x*10 # Global variable y<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� �<U+383C><U+3E63>
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

#### 참고

<eb>���<b8> <ed>��로그<eb>���<bc> <eb>���<ac> R<ec><9d>� 지<ec>��변<ec>��<ec><99>� <ec>��<ec>��변<ec>��가 <ec>��<ec>��<eb>�� <eb>�� 차이가 <ec>��<eb>��.


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

`<-`<eb>�� 지<ec>��변<ec>�� <ed>��<eb>��<ec>��<ec>��지�<8c> `<<-`<ec><99>� 같이 변<ec>���<bc> <ec>��<ec>��<ed>��준<eb>��. 반면 `=`<eb>�� 그렇지 <ec>��<eb>��.


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

<ec>��<eb>��가 발생<ed>��<eb>��. `<-`보다 `=`가 <eb>�� 명확<ed>�� 지<ec>��변<ec>�� <ed>��<eb>��<ec>��<eb>��<eb>�� <ec>��<ec>�� 기억<ed>��<eb>��<ec>��.
