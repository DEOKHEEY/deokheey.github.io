---
layout: post
title: "[Python] Recursion"
date: "2018-09-01"
excerpt: "<ec>���<b0> <ec>��<ec>��<ec>�� <eb>��<ec>�� <ed>��출하<eb>�� 방법"
output: github_document
tag:
    [python, recursion]
comments: true
categories:
  Python
---

## <ec>��귀<ed>���<9c>

<ec>���<b0> <ec>��<ec>��<ec>�� <eb>��<ec>�� <ed>��출하<eb>�� 것을 <eb>��<ed>��<eb>��. <ed>��<ec>�� <ec>��<ec>��<ec>�� <eb>�� <ed>��<ec>���<bc> <eb>��<ec>�� <ed>��출하므�<9c> `반복�<b8> + stack 구조`가 <ed>��<ec>��<ed>��<eb>��. `stack`<ec><9d>� FILO(First In Last Out, <ec>��<ec>��<ed>���<9c>) <ed>��<ec><9d>� LIFO(Last In First Out, <ed>��<ec>��<ec>���<9c>)<ec>�� <ec>��격을 <eb>��<eb>��.

<br>

- 참고 <ec>��<ec>��
`Push`: Push stack<ec>�� 구조<ec>�� 마�<a7>��<89> <eb>��<ec>��<ed>�� <ec>��치에 <ec>��<eb>��<eb>��<eb>��. 
`Pop`: 마�<a7>��<89> <eb>��<ec>��<ed>�� <ec>��치에<ec>�� <eb>��<ec>��<ed>���<bc> 꺼내<eb>�� <ec>��<ec>��(<ec>��<ec>��)

<br>

<ec>��<eb>��<ec>�� 조건<ec>�� 맞는 <ed>��<ec>���<bc> 만들<ec>��보자.

```
stack<ec>�� 리스<ed>�� <ed><83>�<ec>���<9c> 만든<eb>��. 

push <ed>��<ec>��<eb>�� stack변<ec>��<ec>�� 값을 <eb>��<eb>��<eb>��. 
pop <ed>��<ec>��<eb>�� stack변<ec>��<ec>�� 값을 <ec>��<ec>��<ed>��<eb>��.
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

`Queue` <ed>��<ed>���<9c> 만들�<b0> <ec>��<ed>��<ec>�� 기존 값을 <eb>��<ec>�� <ec>�� <ec>��<eb>�� 공간<ec>�� 만들�<a0> 마�<a7>��<89> 값을 차�<a1>�<eb><8c>��<9c> <ec>��기고 마�<a7>��<89> 것을 뽑으�<b4> <eb>��<eb>��. (<ed>��<eb>��<ec>��<ed>�� <ec>��고리�<98>)

***

### factorial 

factorial <ed>��<ec>���<bc> 만들면서 <ec>��귀<ed>���<9c> <ed>��<ec>���<bc> <ec>��<ed>��<ed>��보자. <ec>��<ec>�� factorial<ec>�� <ec>��<eb>���<8c> <eb>��<ec>��<ec>��<eb>��지 <ec>��<ec>��보자.

```
factorial <ed>��<ec>��

n! = n * (n-1) * (n-2) * ... * 2 * 1
n! = n * (n-1)!
n! = n * (n-1) * (n-2)!
n! = n * (n-1) * (n-2) * ... * 2 * 1!
...
```

그렇<eb>���<b4>, n<ec>�� 조건<ec>�� <eb>���<b8> <ed>��<ec>��<ec>��<ec><9d>� <eb>��<ec>���<bc> 같다.

```
factorial 공리
    n * factorial(n-1)  (n >= 1)
    factorial(n) = 1    (n = 0)
```

> 참고�<9c> factorial <ed>��<ec>��<eb>�� 반복문으로도 만들 <ec>�� <ec>��<eb>��. <ed>��지�<8c> <ec>��귀<ed>��<ec>���<bc> <ec>��<ec>��<ed>��<ec>�� 만드<eb>�� <ec>��<ec>��<eb>�� 코드가 <eb>�� 간단<ed>��지�<a0> 깔끔<ed>�� �<88> <ec>�� <ec>���<b0> <eb>��문이<eb>��. <ec>��귀<ed>��<ec>���<bc> 만들 <eb>�� <ec>��<eb>��<ec>�� <eb>�� <eb>��<ec>���<88> <ec>�� <ec>���<a0>, 무한루프<ec>�� 빠질 <ec>�� <ec>��<ec>��<eb>�� <ec>���<bc> 주의<ed>��<ec>�� <ec>��<ec>��<ed>��<eb>���<9d> <ed>��<ec>�� <ed>��<eb>��.

<br>

그럼 <ec>���<bc> <ed>��<eb><8c>��<9c> factorial <ed>��<ec>���<bc> 만들<ec>��보자


{% highlight python %}
# 반복�<U+623C><U+3E38>
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
# <U+653C><U+3E63>��귀<U+653C><U+3E64>��출함<U+653C><U+3E63>��
def factorial(n):
    if n == 1 or n == 0:
        return 1
        
    return n*factorial(n-1)
    
print(factorial(5))
{% endhighlight %}



{% highlight text %}
## 120
{% endhighlight %}

`factorial(5)`<eb>�� `5*factorial(4)`<ec>��므�<9c> `factorial(4)`�<bc> push<ed>��<eb>��. <ec>��<ed>��<ec>��<eb>�� `factorial(3)`<ec>�� push<ed>��면서 push�<bc> 반복<ed>��<eb>��. 그리�<a0> `factorial(1)`<ec>�� <eb>�� 조건<ec>�� 만족<ed>��<eb>�� `1`값을 return<ed>��주고 `factorial(1)`<ec>�� pop<ed>���<a0> <ec>��<ed>��<ec>�� `factorial(2)`�<bc> pop<ed>���<b0> 반복<ed>��<ec>�� 마�<a7>�막에<eb>�� <ec>��<ec>��값을 곱하<ec>�� 최종값을 return<ed>��준<eb>��. 

***

### Greatest Common Divisor

최�<8c>�공약<ec>��<eb>�� <ec>��<ed>��리드 <ec>��고리즘으�<9c> 구할 <ec>�� <ec>��<eb>��.

><ec>��<ed>��리드 <ec>��고리�<98> : 주어�<84> <eb>�� <ec>�� <ec>��<ec>��<ec>�� 존재<ed>��<eb>�� 최�<8c>�공약<ec>��(GCD(Greatest Common Divisor))�<bc> 구하<eb>�� <ec>��고리�<98>

```
1. <eb>�� <ec>�� m, n (m > n)�<bc> <ec>��<eb>��<ec>���<9c> <eb>��<ec>��<ec>��<eb>��.
2. n<ec>�� 0<ec>���<b4> m<ec>�� 출력<ed>���<a0> <ec>��고리즘�<9d>� 종료<ed>��<eb>��.
3. m<ec>�� n<ec>���<9c> <eb>��<eb>��<ec>�� <eb>��<ec>��지�<b4>, n<ec>�� 출력<ed>���<a0> <ec>��고리즘�<9d>� 종료<ed>��<eb>��.
4. 그렇지 <ec>��<ec>���<b4>, m<ec>�� n<ec>���<9c> <eb>��<eb>�� <eb>��머�<a7>��<bc> <ec>���<ad>�<8c> m<ec>�� <eb><8c>�<ec>��<ed>���<a0> m�<bc> n<ec>�� 바꾸�<a0> 3번으�<9c> <eb>��<ec>��간다.
```

<br>

<ec>��<ec>�� <ec>��고리즘�<8c>��<9c> 코드�<bc> 짜면 <eb>��<ec>���<bc> 같다.


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

<eb>�� 간단<ed>���<8c> 바�<bf>� <ec>�� <ec>��<eb>��.


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

반복문으�<9c> 구현<ed>���<b4> <eb>��<ec>���<bc> 같다.


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
