---
layout: post
title: "[R] <ed>•¨<ec>ˆ˜ <ec>ƒ<ec>„±"
date: "2018-08-01"
excerpt: "<ec>´<ec> œ ì§ì ‘ <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤<ec>–´ ë³´ì"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## <ed>•¨<ec>ˆ˜

-<ec>‚¬<ec>š©<ec>ê°€ <ec> •<ec>˜<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜ë¥<bc> <ec>ƒ<ec>„±<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
-<ec>ì£<bc> ë°˜ë³µ<eb>˜<ec>–´ <ec>‚¬<ec>š©<ed>•˜<eb>Š” ê¸°ëŠ¥<ec>„ <ec> •<ec>˜<ed>•˜<eb>Š” <ed>”„ë¡œê·¸<eb>¨
-ì½”ë“œê°€ ê°„ë‹¨<ed>•´ì§„ë‹¤.
-DBê°€ <ec>•„<eb>‹ˆê¸°ë•Œë¬¸ì— <ec>‚¬<ec>š©<ec>‹œë§ˆë‹¤ ë§Œë“¤<ec>–´ì£¼ì–´<ec>•¼ <ed>•œ<eb>‹¤.
-<eb>‹¤<ec>Œê³<bc> ê°™ì´ <ed>•¨<ec>ˆ˜ë¥<bc> <ec>„ <ec>–¸<ed>•œ<eb>‹¤.

```
<ed>•¨<ec>ˆ˜<ec>´ë¦<84> <- function(){
              <ec>ˆ˜<ed>–‰<ed>•´<ec>•¼ <ed>•  ì½”ë“œ
              return(ë³€<ed>™˜ê°<92>) # Optional
}
```
***

### <ed>•¨<ec>ˆ˜<ec>˜ <ec>ƒ<ec>„±

ê°„ë‹¨<ed>•œ <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤<ec>–´ ë³´ì


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
hap <- function(x,y){ # Parameter 2ê°<U+393C><U+3E63> <U+653C><U+3E63>„ <U+653C><U+3E63>–¸
  
  res <- x+y # Local variable <U+653C><U+3E63>„ <U+653C><U+3E63>–¸
  return(res)
  
}

hap(1,2)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}


***
  
### ê°€ë³€ <ec>¸<ec>ˆ˜<ec>˜ <ed>•¨<ec>ˆ˜

<ec>•„<eb>˜ <ec>˜ˆ<ec>‹œë¥<bc> <ec>‚´<ed>´ë³´ì. ê°€ë³€ <ec>¸<ec>ˆ˜<eb>Š” `...`<ec>œ¼ë¡<9c> <ed>‘œ<ed>˜„<ed>•˜<ec>—¬ <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤ë©<b4> <eb>œ<eb>‹¤.


{% highlight r %}
f <- function(...){
  x <- list(...) # Vectorë¡<U+393C><U+3E63> <U+653C><U+3E63>„ <U+653C><U+3E63>–¸<U+653C><U+3E64>•˜<U+653C><U+3E63>—¬<U+653C><U+3E62>„ <U+653C><U+3E63>ƒê´€ <U+653C><U+3E63>—†<U+653C><U+3E63>Œ
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

### ì¤‘ì²© <ed>•¨<ec>ˆ˜

<ed>•¨<ec>ˆ˜<ec>•ˆ<ec>— <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤<ec>–´<ec>„œ <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


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

### ë³€<ec>ˆ˜<ec>— <eb>”°ë¥<b8> <ed>• <eb>‹¹<ec>—°<ec>‚°<ec> <ec>‚¬<ec>š©


`<ec> „<ec>—­ë³€<ec>ˆ˜(Global Variable)`: <ed>•¨<ec>ˆ˜<ec>— <ec>ƒê´€<ec>—†<ec>´ <ed>”„ë¡œê·¸<eb>¨ <ec> „ì²´ì—<ec>„œ <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>Š” ë³€<ec>ˆ˜

`ì§€<ec>—­ë³€<ec>ˆ˜(Local Variable)`: <ed>•¨<ec>ˆ˜<eb>‚´<ec>—<ec>„œ <ec> •<ec>˜<eb>˜ê³<a0> <ec>‚¬<ec>š©<ed>•˜<eb>Š” ë³€<ec>ˆ˜

`ë§¤ê°œë³€<ec>ˆ˜(Parameter Variable`: <ed>•¨<ec>ˆ˜<ec>˜ <ec>¸<ec>ˆ˜<ec>—<ec>„œ ë°›ì•„<ec>„œ <ec>‚¬<ec>š©<ed>•˜<eb>Š” ë³€<ec>ˆ˜

<br>

<ec>•„<eb>˜ ì½”ë“œë¥<bc> ë³´ê³  ì§€<ec>—­ë³€<ec>ˆ˜<ec><99>€ <ec> „<ec>—­ë³€<ec>ˆ˜ë¥<bc> êµ¬ë¶„<ed>•˜ê³<a0> <ed>• <eb>‹¹<ec>—°<ec>‚°<ec>ë¥<bc> <ec>‚¬<ec>š©<ec>‹œ ì£¼ì˜ë¥<bc> <ed>•˜<ec>.


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

<ed>• <eb>‹¹<ec>—°<ec>‚°<ec> `<-`<ec><99>€ `=`<eb>Š” ì§€<ec>—­ë³€<ec>ˆ˜<ec>— <ed>• <eb>‹¹<ec>„ <ed>•´ì£¼ì–´<ec>„œ <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. <ed>•˜ì§€ë§<8c> `<<-`ë¥<bc> <ec>‚¬<ec>š©<ed>•˜ë©<b4> <ec> „<ec>—­ë³€<ec>ˆ˜<ec>— <ed>• <eb>‹¹<eb>¨<ec>„ ì£¼ì˜<ed>•˜<ec>.


{% highlight r %}
x<-1; y<-2; z<-3;

f <- function(x){
  y <<- x*10 # Global variable y<U+653C><U+3E63>— <U+653C><U+3E63>˜<U+653C><U+3E64>–¥<U+653C><U+3E63>„ ì¤<U+383C><U+3E63>
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

#### ì°¸ê³ 

<eb>‹¤ë¥<b8> <ed>”„ë¡œê·¸<eb>¨ê³<bc> <eb>‹¬ë¦<ac> R<ec><9d>€ ì§€<ec>—­ë³€<ec>ˆ˜<ec><99>€ <ec> „<ec>—­ë³€<ec>ˆ˜ê°€ <ec>„ <ec>–¸<eb>  <eb>•Œ ì°¨ì´ê°€ <ec>ˆ<eb>‹¤.


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

`<-`<eb>Š” ì§€<ec>—­ë³€<ec>ˆ˜ <ed>• <eb>‹¹<ec><ec>´ì§€ë§<8c> `<<-`<ec><99>€ ê°™ì´ ë³€<ec>ˆ˜ë¥<bc> <ec>ƒ<ec>„±<ed>•´ì¤€<eb>‹¤. ë°˜ë©´ `=`<eb>Š” ê·¸ë ‡ì§€ <ec>•Š<eb>‹¤.


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

<ec>—<eb>Ÿ¬ê°€ ë°œìƒ<ed>•œ<eb>‹¤. `<-`ë³´ë‹¤ `=`ê°€ <eb>” ëª…í™•<ed>•œ ì§€<ec>—­ë³€<ec>ˆ˜ <ed>• <eb>‹¹<ec><eb>¼<eb>Š” <ec> <ec>„ ê¸°ì–µ<ed>•´<eb>‘<ec>.
