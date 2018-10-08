---
layout: post
title: "[Python] <ec>��<ec>��변<ec>��<ec><99>� 지<ec>��변<ec>��"
date: "2018-09-01"
excerpt: "<ed>��<ec>��<ec>��<ec>�� <ec>��<ec>��변<ec>��, 지<ec>��변<ec>���<bc> <ed>��<eb>��<ed>��<eb>�� 방법"
output: github_document
tag:
    [python, variable]
comments: true
categories:
  Python
---

## <ec>��<ec>��변<ec>��/지<ec>��변<ec>��

-<ec>��<ec>��변<ec>��(global): <ed>��로그<eb>��<ec>�� 종료<eb>��<eb>��까�<a7>� <ec>��<eb>��<ec>��<eb>��지 <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>�� 변<ec>��
-지<ec>��변<ec>��(local): <ed>��<ec>�� <ec>��<ec>��<ec>���<8c> <ec>��<ec>��<ed>��<eb>�� 변<ec>��

<br>

<ec>��<eb>���<bc> 보고 지<ec>��변<ec>��<ec><99>� <ec>��<ec>��변<ec>���<bc> <ec>��<ed>��<ed>��보자.


{% highlight python %}
x = 10 # global 변<U+653C><U+3E63>��
def f(x): # parameter(매개변<U+653C><U+3E63>��)
    print("x = ", x)
    x = 20 # local 변<U+653C><U+3E63>��
    print("x = ", x)
f(x) # <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��변<U+653C><U+3E63>�� 10<U+653C><U+3E63>�� <U+653C><U+3E62>��<U+653C><U+3E63>��가���<U+3E30> 지<U+653C><U+3E63>��변<U+653C><U+3E63>��<U+653C><U+3E63>�� 10<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� 출력<U+653C><U+3E62>��<U+653C><U+3E62>��.
{% endhighlight %}



{% highlight text %}
## x =  10
## x =  20
{% endhighlight %}



{% highlight python %}
print(x) # <U+653C><U+3E63>��<U+653C><U+3E63>��변<U+653C><U+3E63>�� 출력
{% endhighlight %}



{% highlight text %}
## 10
{% endhighlight %}

<br>

<ec>��<ec>��변<ec>�� <ec>��<ec>��<ec><9d>� `global`<ec>�� <ec>��<ec>��<ed>��<ec>�� <ec>��<ec>��<ed>��<eb>��.


{% highlight python %}
x = 10
def f(arg):
    global x
    x = 20
    print('x = ',x)
f(x)
{% endhighlight %}



{% highlight text %}
## x =  20
{% endhighlight %}



{% highlight python %}
print(x) # <U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E62>�� x<U+653C><U+3E62>�� <U+653C><U+3E63>��<U+653C><U+3E63>��변<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>�� 것을 <U+653C><U+3E63>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��
{% endhighlight %}



{% highlight text %}
## 20
{% endhighlight %}
