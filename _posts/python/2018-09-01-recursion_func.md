---
layout: post
title: "[Python] Recursion"
date: "2018-09-01"
excerpt: "<ec>๊ธ<b0> <ec><ec> <ec> <eb>ค<ec> <ed>ธ์ถํ<eb> ๋ฐฉ๋ฒ"
output: github_document
tag:
    [python, recursion]
comments: true
categories:
  Python
---

## <ec>ฌ๊ท<ed>ธ์ถ<9c>

<ec>๊ธ<b0> <ec><ec> <ec> <eb>ค<ec> <ed>ธ์ถํ<eb> ๊ฒ์ <eb>ป<ed><eb>ค. <ed>จ<ec> <ec><ec><ec> <eb>ด <ed>จ<ec>๋ฅ<bc> <eb>ค<ec> <ed>ธ์ถํ๋ฏ๋ก<9c> `๋ฐ๋ณต๋ฌ<b8> + stack ๊ตฌ์กฐ`๊ฐ <ed><ec><ed><eb>ค. `stack`<ec><9d> FILO(First In Last Out, <ec> <ec><ed>์ถ<9c>) <ed>น<ec><9d> LIFO(Last In First Out, <ed><ec><ec> ์ถ<9c>)<ec> <ec>ฑ๊ฒฉ์ <eb><eb>ค.

<br>

- ์ฐธ๊ณ  <ec>ฉ<ec>ด
`Push`: Push stack<ec> ๊ตฌ์กฐ<ec> ๋ง์<a7>๋ง<89> <eb>ฐ<ec>ด<ed>ฐ <ec>์น์ <ec><eb> ฅ<eb><eb>ค. 
`Pop`: ๋ง์<a7>๋ง<89> <eb>ฐ<ec>ด<ed>ฐ <ec>์น์<ec> <eb>ฐ<ec>ด<ed>ฐ๋ฅ<bc> ๊บผ๋ด<eb> <ec><ec>(<ec>ญ<ec> )

<br>

<ec><eb><ec> ์กฐ๊ฑด<ec> ๋ง๋ <ed>จ<ec>๋ฅ<bc> ๋ง๋ค<ec>ด๋ณด์.

```
stack<ec> ๋ฆฌ์ค<ed>ธ <ed><83><ec>๋ก<9c> ๋ง๋ <eb>ค. 

push <ed>จ<ec><eb> stack๋ณ<ec><ec> ๊ฐ์ <eb>ฃ<eb><eb>ค. 
pop <ed>จ<ec><eb> stack๋ณ<ec><ec> ๊ฐ์ <ec>ญ<ec> <ed><eb>ค.
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

`Queue` <ed><ed>๋ก<9c> ๋ง๋ค๊ธ<b0> <ec><ed>ด<ec>  ๊ธฐ์กด ๊ฐ์ <eb>ด<ec> <ec> <ec><eb> ๊ณต๊ฐ<ec> ๋ง๋ค๊ณ<a0> ๋ง์<a7>๋ง<89> ๊ฐ์ ์ฐจ๋<a1><eb><8c>๋ก<9c> <ec>ฎ๊ธฐ๊ณ  ๋ง์<a7>๋ง<89> ๊ฒ์ ๋ฝ์ผ๋ฉ<b4> <eb><eb>ค. (<ed><eb>ธ<ec>ด<ed> <ec>๊ณ ๋ฆฌ์ฆ<98>)

***

### factorial 

factorial <ed>จ<ec>๋ฅ<bc> ๋ง๋ค๋ฉด์ <ec>ฌ๊ท<ed>ธ์ถ<9c> <ed>จ<ec>๋ฅ<bc> <ec>ด<ed>ด<ed>ด๋ณด์. <ec>ฐ<ec>  factorial<ec>ด <ec>ด<eb>ป๊ฒ<8c> <eb><ec>ด<ec><eb>์ง <ec><ec>๋ณด์.

```
factorial <ed>จ<ec>

n! = n * (n-1) * (n-2) * ... * 2 * 1
n! = n * (n-1)!
n! = n * (n-1) * (n-2)!
n! = n * (n-1) * (n-2) * ... * 2 * 1!
...
```

๊ทธ๋ <eb>ค๋ฉ<b4>, n<ec> ์กฐ๊ฑด<ec> <eb>ฐ๋ฅ<b8> <ed>จ<ec><ec><ec><9d> <eb>ค<ec>๊ณ<bc> ๊ฐ๋ค.

```
factorial ๊ณต๋ฆฌ
    n * factorial(n-1)  (n >= 1)
    factorial(n) = 1    (n = 0)
```

> ์ฐธ๊ณ ๋ก<9c> factorial <ed>จ<ec><eb> ๋ฐ๋ณต๋ฌธ์ผ๋ก๋ ๋ง๋ค <ec> <ec><eb>ค. <ed>์ง๋ง<8c> <ec>ฌ๊ท<ed>จ<ec>๋ฅ<bc> <ec>ฌ<ec>ฉ<ed>ด<ec> ๋ง๋<eb> <ec>ด<ec> <eb> ์ฝ๋๊ฐ <eb> ๊ฐ๋จ<ed>ด์ง๊ณ<a0> ๊น๋<ed>ด ์ง<88> <ec> <ec>๊ธ<b0> <eb>๋ฌธ์ด<eb>ค. <ec>ฌ๊ท<ed>จ<ec>๋ฅ<bc> ๋ง๋ค <eb> <ec>ฑ<eb>ฅ<ec>ด <eb> <eb>จ<ec>ด์ง<88> <ec> <ec>๊ณ<a0>, ๋ฌดํ๋ฃจํ<ec> ๋น ์ง <ec> <ec><ec>ผ<eb> <ec>ด๋ฅ<bc> ์ฃผ์<ed>ด<ec> <ec>ฌ<ec>ฉ<ed><eb>๋ก<9d> <ed>ด<ec>ผ <ed><eb>ค.

<br>

๊ทธ๋ผ <ec>๋ฅ<bc> <ed> <eb><8c>๋ก<9c> factorial <ed>จ<ec>๋ฅ<bc> ๋ง๋ค<ec>ด๋ณด์


{% highlight python %}
# ๋ฐ๋ณต๋ฌ<U+623C><U+3E38>
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
# <U+653C><U+3E63>ฌ๊ท<U+653C><U+3E64>ธ์ถํจ<U+653C><U+3E63>
def factorial(n):
    if n == 1 or n == 0:
        return 1
        
    return n*factorial(n-1)
    
print(factorial(5))
{% endhighlight %}



{% highlight text %}
## 120
{% endhighlight %}

`factorial(5)`<eb> `5*factorial(4)`<ec>ด๋ฏ๋ก<9c> `factorial(4)`๋ฅ<bc> push<ed><eb>ค. <ec>ด<ed><ec><eb> `factorial(3)`<ec> push<ed>๋ฉด์ push๋ฅ<bc> ๋ฐ๋ณต<ed><eb>ค. ๊ทธ๋ฆฌ๊ณ<a0> `factorial(1)`<ec>ผ <eb> ์กฐ๊ฑด<ec> ๋ง์กฑ<ed><eb> `1`๊ฐ์ return<ed>ด์ฃผ๊ณ  `factorial(1)`<ec> pop<ed>๊ณ<a0> <ec>ด<ed><ec> `factorial(2)`๋ฅ<bc> pop<ed>๋ฉ<b0> ๋ฐ๋ณต<ed><ec>ฌ ๋ง์<a7>๋ง์<eb> <ec><ec>๊ฐ์ ๊ณฑํ<ec>ฌ ์ต์ข๊ฐ์ return<ed>ด์ค<eb>ค. 

***

### Greatest Common Divisor

์ต๋<8c>๊ณต์ฝ<ec><eb> <ec> <ed>ด๋ฆฌ๋ <ec>๊ณ ๋ฆฌ์ฆ์ผ๋ก<9c> ๊ตฌํ  <ec> <ec><eb>ค.

><ec> <ed>ด๋ฆฌ๋ <ec>๊ณ ๋ฆฌ์ฆ<98> : ์ฃผ์ด์ง<84> <eb> <ec> <ec>ฌ<ec>ด<ec> ์กด์ฌ<ed><eb> ์ต๋<8c>๊ณต์ฝ<ec>(GCD(Greatest Common Divisor))๋ฅ<bc> ๊ตฌํ<eb> <ec>๊ณ ๋ฆฌ์ฆ<98>

```
1. <eb> <ec> m, n (m > n)๋ฅ<bc> <ec><eb> ฅ<ec>ผ๋ก<9c> <eb>ค<ec>ด<ec>จ<eb>ค.
2. n<ec>ด 0<ec>ด๋ฉ<b4> m<ec> ์ถ๋ ฅ<ed>๊ณ<a0> <ec>๊ณ ๋ฆฌ์ฆ์<9d> ์ข๋ฃ<ed><eb>ค.
3. m<ec>ด n<ec>ผ๋ก<9c> <eb><eb><ec>ด <eb>จ<ec>ด์ง๋ฉ<b4>, n<ec> ์ถ๋ ฅ<ed>๊ณ<a0> <ec>๊ณ ๋ฆฌ์ฆ์<9d> ์ข๋ฃ<ed><eb>ค.
4. ๊ทธ๋ ์ง <ec><ec>ผ๋ฉ<b4>, m<ec> n<ec>ผ๋ก<9c> <eb><eb> <eb>๋จธ์<a7>๋ฅ<bc> <ec>๋ก<ad>๊ฒ<8c> m<ec> <eb><8c><ec><ed>๊ณ<a0> m๊ณ<bc> n<ec> ๋ฐ๊พธ๊ณ<a0> 3๋ฒ์ผ๋ก<9c> <eb><ec>๊ฐ๋ค.
```

<br>

<ec><ec> <ec>๊ณ ๋ฆฌ์ฆ๋<8c>๋ก<9c> ์ฝ๋๋ฅ<bc> ์ง๋ฉด <eb>ค<ec>๊ณ<bc> ๊ฐ๋ค.


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

<eb> ๊ฐ๋จ<ed>๊ฒ<8c> ๋ฐ๊<bf> <ec> <ec><eb>ค.


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

๋ฐ๋ณต๋ฌธ์ผ๋ก<9c> ๊ตฌํ<ed>๋ฉ<b4> <eb>ค<ec>๊ณ<bc> ๊ฐ๋ค.


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
