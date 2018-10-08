---
layout: post
title: "[Python] str<ed>��<ec>�� function"
date: "2018-09-01"
excerpt: "<ed>��<ec>��<ec>��<ec>��<ec>��<ec>�� 문자 <ed>��<ec>��"
output: github_document
tag:
    [python, str, function]
comments: true
categories:
  Python
---

<br>

***

## 문자<ed>��<ec>��

Python<ec>�� `str`<ed><83>�<ec>��<ec>�� <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>�� <ed>��<ec>��<ec>��<eb>��. 

***

## 문자 구조 <ed>��<ec>��

### in <ec>��<ec>��<ec>��: 문자<ec>�� 존재<ec>��부 <ed>��<ec>��

`in`<ec>��<ec>��<ec>���<bc> <ec>��<ec>��<ed>��<ec>�� 문자<ec>��<ec>�� 존재<ec>��부�<bc> <ed>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight python %}
x = 'hello'
print('o' in x)
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### startswith(), endswith(): <ed>��<ec>��문자�<9c> <ec>��<ec>��,<eb>��<eb>��<eb>��지 <ed>��<eb>��

`startswith()`<eb>�� <ec>���<b8> 문자<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>���<9c> <ec>��<ec>��<eb>��<eb>��지�<bc>, `endswith()`<eb>�� <ec>���<b8> 문자<ec>��<ec>�� <ed>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자�<9c> <eb>��<eb>��<eb>��지�<bc> <ed>��<eb>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight python %}
x = 'python'
# startswith()
print(x.startswith('p'))
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(x.startswith('py'))
# endswith()
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(x.endswith('p'))
{% endhighlight %}



{% highlight text %}
## False
{% endhighlight %}



{% highlight python %}
print(x.endswith('on'))
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### count(): <ed>��<ec>�� 문자<ec>�� �<af><ec>�� 리턴

<ec>���<b8> 문자<ec>��<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>��<ec>�� 몇개 <ec>��<eb>��지 <ec>��<eb>��주는 <ed>��<ec>��


{% highlight python %}
x = 'datamining'
print(x.count('a'))
{% endhighlight %}



{% highlight text %}
## 2
{% endhighlight %}

<br>

***

## <eb><8c>�<ec>��문자 관<eb>�� <ed>��<ec>��

### upper(), lower(): <eb><8c>�문자, <ec>��문자�<9c> 변<ed>��

<ec>���<b8> 문자<ec>��<ec>�� <eb><8c>�문자 <eb>��<eb>�� <ec>��문자�<9c> 변<ed>��<ed>��주는 <ed>��<ec>��


{% highlight python %}
x = 'KoreA'
# upper()
print(x.upper())
# lower()
{% endhighlight %}



{% highlight text %}
## KOREA
{% endhighlight %}



{% highlight python %}
print(x.lower())
{% endhighlight %}



{% highlight text %}
## korea
{% endhighlight %}

<br>

### capitalize(), title(): 첫�<b8>�<ec>���<bc> <eb><8c>�문자�<9c> 변<ed>��

`capitalize()`<eb>�� <ec>���<b8> 문자<ec>��<ec>�� 첫�<b8>�<ec>���<bc> <eb><8c>�문자�<9c> 변<ed>��<ed>��준<eb>��. <ed>��지�<8c> `title()`<ec><9d>� <eb>��<ec>�� 별로 모든 문자<ec>��<ec>�� <eb><8c>�문자�<9c> 변<ed>��<ed>��준<eb>��.


{% highlight python %}
x = 'data science'
# capitalize()
print(x.capitalize())
# title()
{% endhighlight %}



{% highlight text %}
## Data science
{% endhighlight %}



{% highlight python %}
print(x.title())
{% endhighlight %}



{% highlight text %}
## Data Science
{% endhighlight %}

<br>

### swapcase(): <eb><8c>�<ec>��문자�<bc> 변<ed>��

문자<ec>��<ec>�� <eb><8c>�문자<eb>�� <ec>��문자�<9c>, <ec>��문자<eb>�� <eb><8c>�문자�<9c> 변<ed>��<ed>��준<eb>��.


{% highlight python %}
x = 'Hello world'
print(x.swapcase())
{% endhighlight %}



{% highlight text %}
## hELLO WORLD
{% endhighlight %}

<br>

***

## 문자<ec>�� 배치 <ed>��<ec>��

### center(): 지<ec>�� 공간<ec>��<ec>�� 중앙 배치


{% highlight python %}
x = 'hello'
print(x.center(20))
{% endhighlight %}



{% highlight text %}
##        hello
{% endhighlight %}

<br>

### ljust(): 지<ec>�� 공간<ec>��<ec>�� 좌측 배치


{% highlight python %}
x = 'hello'
print(x.ljust(20))
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rjust(): 지<ec>�� 공간<ec>��<ec>�� <ec>���<a1> 배치


{% highlight python %}
x = 'hello'
print(x.rjust(20))
{% endhighlight %}



{% highlight text %}
##                hello
{% endhighlight %}

<br>

***

## 공백/문자 <ec>���<b0> <ed>��<ec>��

공백<ec>�� <ec>��거하�<a0> <ec>��<ec>�� <ec>�� <ed>��<ec>���<8c> <ec>��<eb>��<ed>���<b4> <eb>��지�<8c>,  문자�<bc> <ec>��거하�<a0> <ec>��<ec>�� <ec>��<ec>��<eb>�� <ed>��<ec>�� 문자�<bc> <ec>��<eb>��<ed>��<ec>�� <ec>��<ec>��<ed>���<b4> <eb>��<eb>��.

### strip(): 좌우 공백/문자 <ec>���<b0>


{% highlight python %}
x = '      hello     '
print(x.strip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

문자<eb>�� <eb>��<ec>���<bc> 같이 <ec>��거한<eb>��.


{% highlight python %}
x = 'helloh'
print(x.strip('h'))
{% endhighlight %}



{% highlight text %}
## ello
{% endhighlight %}

<ec>��<eb>�� `lstrip()`�<bc> `rstrip()`<eb>�� <ec>��<ec><99>�같이 <ec>��<ec>��<ed>���<b4> <eb>��<eb>��.

<br>

### lstrip()

<ec>��본문<ec>��<ec>�� <ec>��쪽에 공백<ec>�� <ec>��거한<eb>��.


{% highlight python %}
x = '      hello     '
print(x.lstrip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rstrip()

<ec>��본문<ec>��<ec>�� <ec>��른쪽<ec>�� 공백<ec>�� <ec>��거한<eb>��.


{% highlight python %}
x = '      hello     '
print(x.rstrip())
{% endhighlight %}



{% highlight text %}
##       hello
{% endhighlight %}

<br>

***

## 문자<ec>�� <ed><83>�<ec>�� <ed>��<ec>��

### isalpha(): <ec>��<ed>���<b3>,<ed>��글<ec>��지 <ed>��<ec>��

<ec>���<b8> 문자<ec>��<ec>�� <ec>��<ec>��, 기호�<bc> <ec>��<ec>��<ed>�� <ec>��<ed>���<b3>, <ed>��글로만 <ec>��루어졌는지 <ed>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight python %}
print('hello'.isalpha())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
x = 'hello2018'
print(x.isalpha()) 
{% endhighlight %}



{% highlight text %}
## False
{% endhighlight %}



{% highlight python %}
print('<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E63>��'.isalpha())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### isalnum(): <ec>��<ed>���<b3>, <ed>��글, <ec>��<ec>��<ec>��지 <ed>��<ec>��

<ec>��본문<ec>��<ec>��<ec>�� <ec>��<ed>���<b3>, <ed>��글, <ec>��<ec>��로만 <ec>��루어<ec>��<ec>��<eb>��지 <ed>��<ec>��


{% highlight python %}
x = 'hello'
y = 'hello2018'
z = '<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E63>��'
print(x.isalnum())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(y.isalnum())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(z.isalnum())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### isnumeric(): <ec>��<ec>��로만 <ec>��루어진�<a7>� <ed>��<ec>��

<ec>��본문<ec>��<ec>��<ec>�� <ec>��<ec>��로만 <ec>��루어<ec>��<ec>��<eb>��지 <ed>��<ec>��. 만약 <ed><83>�<ec>��<ec>�� <ec>��<ec>��<ec>���<b4> <ec>��류�<b0>� 발생<ed>��<eb>��. 


{% highlight python %}
x = 'hello2018'
y = '2018'
print(x.isnumeric())
{% endhighlight %}



{% highlight text %}
## False
{% endhighlight %}



{% highlight python %}
print(y.isnumeric())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

***

## 문자<ec>�� <ec>���<98> 검<ec>��

### index(): index<ec>���<98> 반환(<ec>��<ec>��<ec>�� <ec>���<98>)

<ec>���<b8> 문자<ec>��<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>��<ec>�� 존재<ed>��<eb>�� <ec>��치�<a5><bc> <ec>��<ec>��<ec>��부<ed>�� 찾는<eb>��. <ec>��<ec>���<b4> **<ec>���<98>**가 발생<ed>��<eb>��. <ec>��<eb>�� `find()`<ec><99>� <eb>���<b8> <ec>��<ec>��<eb>��.


{% highlight python %}
x = 'hello'
print(x.index('e'))
{% endhighlight %}



{% highlight text %}
## 1
{% endhighlight %}

<br>

### find(): index <ec>���<98> 반환(<ec>��<ec>��<ec>�� -1)

<ec>���<b8> 문자<ec>��<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>��<ec>�� 존재<ed>��<eb>��지 <ec>��치�<a5><bc> <ec>��<ec>��<ec>��부<ed>�� 찾는<eb>��. 만약 존재<ed>��지 <ec>��<ec>���<b4> `-1`�<9c> <eb>��<ec>��<eb>��.


{% highlight python %}
x = 'hello'
print(x.find('h'))
{% endhighlight %}



{% highlight text %}
## 0
{% endhighlight %}



{% highlight python %}
print(x.find('H'))
{% endhighlight %}



{% highlight text %}
## -1
{% endhighlight %}

<br>

### rfind(): index <ec>���<98> 반환(<eb>��<ec>��<ec>�� 검<ec>��)

<ec>��본문<ec>��<ec>��<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>��<ec>�� 존재<ed>��<eb>�� <ec>��치�<a5><bc> <eb>��<ec>��<ec>��부<ed>�� 찾는<eb>��. 


{% highlight python %}
x = 'hello'
print(x.rfind('h'))
{% endhighlight %}



{% highlight text %}
## 0
{% endhighlight %}



{% highlight python %}
print(x.rfind('H'))
{% endhighlight %}



{% highlight text %}
## -1
{% endhighlight %}

결과�<bc> 보면 `find()`<ec><99>� 같�<9d>� 검<ec>��결과�<bc> 반환<ed>��<eb>��.

<br>

***

## 기�<83>� 문자 <ed>��<ec>��

### replace(): <ed>��<ec>�� 문자<ec>��<ec>�� 찾아 변�<bd>

<ec>��본문<ec>��<ec>��<ec>��<ec>�� <ec>��<eb>�� 문자<ec>��<ec>�� 찾아<ec>�� <ec>��로운 문자<ec>���<9c> 변�<bd>


{% highlight python %}
x = 'hello world'
x = x.replace('hello','python') # 변경값<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E62>��<U+653C><U+3E64>��주어<U+653C><U+3E63>�� <U+653C><U+3E64>��
print(x) 
{% endhighlight %}



{% highlight text %}
## python world
{% endhighlight %}

<br>

### split(): 문자<ec>�� 분할

<ec>��본문<ec>��<ec>��<ec>�� 매개변<ec>���<9c> <ec>��<eb>��<ed>�� 문자<ec>��<ec>�� 기�<a4>�<ec>���<9c> <ec>��본문<ec>��<ec>��<ec>�� <eb>��<eb>�� 리스<ed>���<9c> 만든<eb>��.


{% highlight python %}
x = 'hello,world'
x = x.split(',')
print(x)
{% endhighlight %}



{% highlight text %}
## ['hello', 'world']
{% endhighlight %}

<br>

### join(): <ec>��본문<ec>�� <ec>��<ec>��<ec>�� <ed>��<ec>�� 문자 추�<b0>�

<ec>���<b8> 글<ec>�� <ec>��<ec>��<ec>�� <ed>��<ec>��<ed>�� 문자<ec>��<ec>�� 추�<b0>�<ed>��<eb>��.


{% highlight python %}
x = 'abcdefg'
x = ','.join(x)
print(x)
{% endhighlight %}



{% highlight text %}
## a,b,c,d,e,f,g
{% endhighlight %}

<br>

### input(): <ec>��<eb>��값을 문자�<9c> 받음

<ec>��<eb>��값을 문자<ec>���<9c> 받는 <ed>��<ec>��<ec>��<eb>��.

```
x = input()

x = int(input()) # <ec>��<ec>���<bc> <ec>��<eb>��<ed>�� <ec>��
```

***
