---
layout: post
title: "[Python] Recursion"
date: "2018-09-01"
excerpt: "<ec>ê¸<b0> <ec><ec>‹ <ec>„ <eb>‹¤<ec>‹œ <ed>˜¸ì¶œí•˜<eb>Š” ë°©ë²•"
output: github_document
tag:
    [python, recursion]
comments: true
categories:
  Python
---

## <ec>¬ê·€<ed>˜¸ì¶<9c>

<ec>ê¸<b0> <ec><ec>‹ <ec>„ <eb>‹¤<ec>‹œ <ed>˜¸ì¶œí•˜<eb>Š” ê²ƒì„ <eb>œ»<ed>•œ<eb>‹¤. <ed>•¨<ec>ˆ˜ <ec>•ˆ<ec>—<ec>„œ <eb>‚´ <ed>•¨<ec>ˆ˜ë¥<bc> <eb>‹¤<ec>‹œ <ed>˜¸ì¶œí•˜ë¯€ë¡<9c> `ë°˜ë³µë¬<b8> + stack êµ¬ì¡°`ê°€ <ed>•„<ec>š”<ed>•˜<eb>‹¤. `stack`<ec><9d>€ FILO(First In Last Out, <ec>„ <ec>…<ed>›„ì¶<9c>) <ed>˜¹<ec><9d>€ LIFO(Last In First Out, <ed>›„<ec>…<ec>„ ì¶<9c>)<ec>˜ <ec>„±ê²©ì„ <eb>ˆ<eb>‹¤.

<br>

- ì°¸ê³  <ec>š©<ec>–´
`Push`: Push stack<ec>˜ êµ¬ì¡°<ec>ƒ ë§ˆì<a7>€ë§<89> <eb>°<ec>´<ed>„° <ec>œ„ì¹˜ì— <ec>…<eb> ¥<eb>œ<eb>‹¤. 
`Pop`: ë§ˆì<a7>€ë§<89> <eb>°<ec>´<ed>„° <ec>œ„ì¹˜ì—<ec>„œ <eb>°<ec>´<ed>„°ë¥<bc> êº¼ë‚´<eb>Š” <ec>‘<ec>—…(<ec>‚­<ec> œ)

<br>

<ec>•„<eb>˜<ec>˜ ì¡°ê±´<ec>— ë§ëŠ” <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤<ec>–´ë³´ì.

```
stack<ec>„ ë¦¬ìŠ¤<ed>Š¸ <ed><83>€<ec>…ë¡<9c> ë§Œë“ <eb>‹¤. 

push <ed>•¨<ec>ˆ˜<eb>Š” stackë³€<ec>ˆ˜<ec>— ê°’ì„ <eb>„£<eb>Š”<eb>‹¤. 
pop <ed>•¨<ec>ˆ˜<eb>Š” stackë³€<ec>ˆ˜<ec>— ê°’ì„ <ec>‚­<ec> œ<ed>•œ<eb>‹¤.
```


{% highlight python %}
stack = []
def push(x):
    global stack
    return stack.append(x)
def pop():
    global stack
    if len(stack) == 0:
        return None
    return stack.pop()
push(1)
print(stack)
{% endhighlight %}



{% highlight text %}
## [1]
{% endhighlight %}



{% highlight python %}
push(2)
print(stack)
{% endhighlight %}



{% highlight text %}
## [1, 2]
{% endhighlight %}



{% highlight python %}
pop()
print(stack)
{% endhighlight %}



{% highlight text %}
## [1]
{% endhighlight %}

`Queue` <ed>˜•<ed>ƒœë¡<9c> ë§Œë“¤ê¸<b0> <ec>œ„<ed>•´<ec>„  ê¸°ì¡´ ê°’ì„ <eb>‹´<ec>„ <ec>ˆ˜ <ec>ˆ<eb>Š” ê³µê°„<ec>„ ë§Œë“¤ê³<a0> ë§ˆì<a7>€ë§<89> ê°’ì„ ì°¨ë<a1>€<eb><8c>€ë¡<9c> <ec>˜®ê¸°ê³  ë§ˆì<a7>€ë§<89> ê²ƒì„ ë½‘ìœ¼ë©<b4> <eb>œ<eb>‹¤. (<ed>•˜<eb>…¸<ec>´<ed>ƒ‘ <ec>•Œê³ ë¦¬ì¦<98>)

***

### factorial 

factorial <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤ë©´ì„œ <ec>¬ê·€<ed>˜¸ì¶<9c> <ed>•¨<ec>ˆ˜ë¥<bc> <ec>´<ed>•´<ed>•´ë³´ì. <ec>š°<ec>„  factorial<ec>´ <ec>–´<eb>–»ê²<8c> <eb>˜<ec>–´<ec>ˆ<eb>Š”ì§€ <ec>•Œ<ec>•„ë³´ì.

```
factorial <ed>•¨<ec>ˆ˜

n! = n * (n-1) * (n-2) * ... * 2 * 1
n! = n * (n-1)!
n! = n * (n-1) * (n-2)!
n! = n * (n-1) * (n-2) * ... * 2 * 1!
...
```

ê·¸ë ‡<eb>‹¤ë©<b4>, n<ec>˜ ì¡°ê±´<ec>— <eb>”°ë¥<b8> <ed>•¨<ec>ˆ˜<ec>‹<ec><9d>€ <eb>‹¤<ec>Œê³<bc> ê°™ë‹¤.

```
factorial ê³µë¦¬
    n * factorial(n-1)  (n >= 1)
    factorial(n) = 1    (n = 0)
```

> ì°¸ê³ ë¡<9c> factorial <ed>•¨<ec>ˆ˜<eb>Š” ë°˜ë³µë¬¸ìœ¼ë¡œë„ ë§Œë“¤ <ec>ˆ˜ <ec>ˆ<eb>‹¤. <ed>•˜ì§€ë§<8c> <ec>¬ê·€<ed>•¨<ec>ˆ˜ë¥<bc> <ec>‚¬<ec>š©<ed>•´<ec>„œ ë§Œë“œ<eb>Š” <ec>´<ec>œ <eb>Š” ì½”ë“œê°€ <eb>” ê°„ë‹¨<ed>•´ì§€ê³<a0> ê¹”ë”<ed>•´ ì§<88> <ec>ˆ˜ <ec>ˆê¸<b0> <eb>•Œë¬¸ì´<eb>‹¤. <ec>¬ê·€<ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤ <eb>•Œ <ec>„±<eb>Š¥<ec>´ <eb>” <eb>–¨<ec>–´ì§<88> <ec>ˆ˜ <ec>ˆê³<a0>, ë¬´í•œë£¨í”„<ec>— ë¹ ì§ˆ <ec>ˆ˜ <ec>ˆ<ec>œ¼<eb>‹ˆ <ec>´ë¥<bc> ì£¼ì˜<ed>•´<ec>„œ <ec>‚¬<ec>š©<ed>•˜<eb>„ë¡<9d> <ed>•´<ec>•¼ <ed>•œ<eb>‹¤.

<br>

ê·¸ëŸ¼ <ec>œ„ë¥<bc> <ed>† <eb><8c>€ë¡<9c> factorial <ed>•¨<ec>ˆ˜ë¥<bc> ë§Œë“¤<ec>–´ë³´ì


{% highlight python %}
# ë°˜ë³µë¬<U+623C><U+3E38>
def factorial(n):
    f = 1
    for i in range(n,0,-1):
        f *= i
    return f
    
print(factorial(5))
{% endhighlight %}



{% highlight text %}
## 120
{% endhighlight %}

<br>


{% highlight python %}
# <U+653C><U+3E63>¬ê·€<U+653C><U+3E64>˜¸ì¶œí•¨<U+653C><U+3E63>ˆ˜
def factorial(n):
    if n == 1 or n == 0:
        return 1
        
    return n*factorial(n-1)
    
print(factorial(5))
{% endhighlight %}



{% highlight text %}
## 120
{% endhighlight %}

`factorial(5)`<eb>Š” `5*factorial(4)`<ec>´ë¯€ë¡<9c> `factorial(4)`ë¥<bc> push<ed>•œ<eb>‹¤. <ec>´<ed>›„<ec>—<eb>Š” `factorial(3)`<ec>„ push<ed>•˜ë©´ì„œ pushë¥<bc> ë°˜ë³µ<ed>•œ<eb>‹¤. ê·¸ë¦¬ê³<a0> `factorial(1)`<ec>¼ <eb>•Œ ì¡°ê±´<ec>— ë§Œì¡±<ed>•˜<eb>‹ˆ `1`ê°’ì„ return<ed>•´ì£¼ê³  `factorial(1)`<ec>„ pop<ed>•˜ê³<a0> <ec>´<ed>›„<ec>— `factorial(2)`ë¥<bc> pop<ed>•˜ë©<b0> ë°˜ë³µ<ed>•˜<ec>—¬ ë§ˆì<a7>€ë§‰ì—<eb>Š” <ec>ƒ<ec>ˆ˜ê°’ì„ ê³±í•˜<ec>—¬ ìµœì¢…ê°’ì„ return<ed>•´ì¤€<eb>‹¤. 

***

### Greatest Common Divisor

ìµœë<8c>€ê³µì•½<ec>ˆ˜<eb>Š” <ec>œ <ed>´ë¦¬ë“œ <ec>•Œê³ ë¦¬ì¦˜ìœ¼ë¡<9c> êµ¬í•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.

><ec>œ <ed>´ë¦¬ë“œ <ec>•Œê³ ë¦¬ì¦<98> : ì£¼ì–´ì§<84> <eb>‘ <ec>ˆ˜ <ec>‚¬<ec>´<ec>— ì¡´ì¬<ed>•˜<eb>Š” ìµœë<8c>€ê³µì•½<ec>ˆ˜(GCD(Greatest Common Divisor))ë¥<bc> êµ¬í•˜<eb>Š” <ec>•Œê³ ë¦¬ì¦<98>

```
1. <eb>‘ <ec>ˆ˜ m, n (m > n)ë¥<bc> <ec>…<eb> ¥<ec>œ¼ë¡<9c> <eb>“¤<ec>–´<ec>˜¨<eb>‹¤.
2. n<ec>´ 0<ec>´ë©<b4> m<ec>„ ì¶œë ¥<ed>•˜ê³<a0> <ec>•Œê³ ë¦¬ì¦˜ì<9d>€ ì¢…ë£Œ<ed>•œ<eb>‹¤.
3. m<ec>´ n<ec>œ¼ë¡<9c> <eb>‚˜<eb>ˆ„<ec>–´ <eb>–¨<ec>–´ì§€ë©<b4>, n<ec>„ ì¶œë ¥<ed>•˜ê³<a0> <ec>•Œê³ ë¦¬ì¦˜ì<9d>€ ì¢…ë£Œ<ed>•œ<eb>‹¤.
4. ê·¸ë ‡ì§€ <ec>•Š<ec>œ¼ë©<b4>, m<ec>„ n<ec>œ¼ë¡<9c> <eb>‚˜<eb>ˆˆ <eb>‚˜ë¨¸ì<a7>€ë¥<bc> <ec>ƒˆë¡<ad>ê²<8c> m<ec>— <eb><8c>€<ec>…<ed>•˜ê³<a0> mê³<bc> n<ec>„ ë°”ê¾¸ê³<a0> 3ë²ˆìœ¼ë¡<9c> <eb>Œ<ec>•„ê°„ë‹¤.
```

<br>

<ec>œ„<ec>˜ <ec>•Œê³ ë¦¬ì¦˜ë<8c>€ë¡<9c> ì½”ë“œë¥<bc> ì§œë©´ <eb>‹¤<ec>Œê³<bc> ê°™ë‹¤.


{% highlight python %}
def gcd(m,n):
    if m < n:
        m = n
        n = m
    
    if n == 0:
        return m
    elif m % n == 0:
        return n
    else:
        m = m % n
        return gcd(m,n)
        
print(18,12)
{% endhighlight %}



{% highlight text %}
## 18 12
{% endhighlight %}

<eb>” ê°„ë‹¨<ed>•˜ê²<8c> ë°”ê<bf>€ <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight python %}
def gcd(x,y):
    if y == 0:
        return x
    return gcd(y,x%y)
  
print(18,12)
{% endhighlight %}



{% highlight text %}
## 18 12
{% endhighlight %}

ë°˜ë³µë¬¸ìœ¼ë¡<9c> êµ¬í˜„<ed>•˜ë©<b4> <eb>‹¤<ec>Œê³<bc> ê°™ë‹¤.


{% highlight python %}
def gcd(x,y):
    if x < y:
        x,y = y,x # switching
    while(y != 0):
        n = x%y
        x = y
        y = n
    return x
    
print(18,12)
{% endhighlight %}



{% highlight text %}
## 18 12
{% endhighlight %}
