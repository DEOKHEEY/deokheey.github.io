---
layout: post
title: "[Python] str<ed><ec> function"
date: "2018-09-01"
excerpt: "<ed><ec>΄<ec>¬<ec><ec><ec> λ¬Έμ <ed>¨<ec>"
output: github_document
tag:
    [python, str, function]
comments: true
categories:
  Python
---

<br>

***

## λ¬Έμ<ed>¨<ec>

Python<ec> `str`<ed><83><ec><ec> <ec>¬<ec>©<ed>  <ec> <ec><eb> <ed>¨<ec><ec>΄<eb>€. 

***

## λ¬Έμ κ΅¬μ‘° <ed><ec>Έ

### in <ec>°<ec>°<ec>: λ¬Έμ<ec>΄ μ‘΄μ¬<ec>¬λΆ <ed><ec>Έ

`in`<ec>°<ec>°<ec>λ₯<bc> <ec>΄<ec>©<ed>΄<ec> λ¬Έμ<ec>΄<ec> μ‘΄μ¬<ec>¬λΆλ₯<bc> <ed><ec>Έ<ed>  <ec> <ec><eb>€.


{% highlight python %}
x = 'hello'
print('o' in x)
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### startswith(), endswith(): <ed>Ή<ec> λ¬Έμλ‘<9c> <ec><ec>,<eb><eb><eb>μ§ <ed><eb>¨

`startswith()`<eb> <ec>λ³<b8> λ¬Έμ<ec>΄<ec>΄ λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄λ‘<9c> <ec><ec><eb><eb>μ§λ₯<bc>, `endswith()`<eb> <ec>λ³<b8> λ¬Έμ<ec>΄<ec>΄ <ed>Ή<ec>  λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμλ‘<9c> <eb><eb><eb>μ§λ₯<bc> <ed><eb>¨<ed>  <ec> <ec><eb>€.


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

### count(): <ed>Ή<ec>  λ¬Έμ<ec>΄ κ°<af><ec> λ¦¬ν΄

<ec>λ³<b8> λ¬Έμ<ec>΄<ec><ec> λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄<ec>΄ λͺκ° <ec><eb>μ§ <ec><eb> €μ£Όλ <ed>¨<ec>


{% highlight python %}
x = 'datamining'
print(x.count('a'))
{% endhighlight %}



{% highlight text %}
## 2
{% endhighlight %}

<br>

***

## <eb><8c><ec>λ¬Έμ κ΄<eb> ¨ <ed>¨<ec>

### upper(), lower(): <eb><8c>λ¬Έμ, <ec>λ¬Έμλ‘<9c> λ³<ed>

<ec>λ³<b8> λ¬Έμ<ec>΄<ec> <eb><8c>λ¬Έμ <eb><eb> <ec>λ¬Έμλ‘<9c> λ³<ed><ed>΄μ£Όλ <ed>¨<ec>


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

### capitalize(), title(): μ²«κ<b8><ec>λ₯<bc> <eb><8c>λ¬Έμλ‘<9c> λ³<ed>

`capitalize()`<eb> <ec>λ³<b8> λ¬Έμ<ec>΄<ec> μ²«κ<b8><ec>λ₯<bc> <eb><8c>λ¬Έμλ‘<9c> λ³<ed><ed>΄μ€<eb>€. <ed>μ§λ§<8c> `title()`<ec><9d> <eb>¨<ec>΄ λ³λ‘ λͺ¨λ  λ¬Έμ<ec>΄<ec> <eb><8c>λ¬Έμλ‘<9c> λ³<ed><ed>΄μ€<eb>€.


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

### swapcase(): <eb><8c><ec>λ¬Έμλ₯<bc> λ³<ed>

λ¬Έμ<ec>΄<ec> <eb><8c>λ¬Έμ<eb> <ec>λ¬Έμλ‘<9c>, <ec>λ¬Έμ<eb> <eb><8c>λ¬Έμλ‘<9c> λ³<ed><ed>΄μ€<eb>€.


{% highlight python %}
x = 'Hello world'
print(x.swapcase())
{% endhighlight %}



{% highlight text %}
## hELLO WORLD
{% endhighlight %}

<br>

***

## λ¬Έμ<ec>΄ λ°°μΉ <ed>¨<ec>

### center(): μ§<ec>  κ³΅κ°<ec><ec> μ€μ λ°°μΉ


{% highlight python %}
x = 'hello'
print(x.center(20))
{% endhighlight %}



{% highlight text %}
##        hello
{% endhighlight %}

<br>

### ljust(): μ§<ec>  κ³΅κ°<ec><ec> μ’μΈ‘ λ°°μΉ


{% highlight python %}
x = 'hello'
print(x.ljust(20))
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rjust(): μ§<ec>  κ³΅κ°<ec><ec> <ec>°μΈ<a1> λ°°μΉ


{% highlight python %}
x = 'hello'
print(x.rjust(20))
{% endhighlight %}



{% highlight text %}
##                hello
{% endhighlight %}

<br>

***

## κ³΅λ°±/λ¬Έμ <ec> κ±<b0> <ed>¨<ec>

κ³΅λ°±<ec> <ec> κ±°νκ³<a0> <ec>Ά<ec> <ec> <ed>¨<ec>λ§<8c> <ec><eb> ₯<ed>λ©<b4> <eb>μ§λ§<8c>,  λ¬Έμλ₯<bc> <ec> κ±°νκ³<a0> <ec>Ά<ec> <ec><ec><eb> <ed>Ή<ec>  λ¬Έμλ₯<bc> <ec><eb> ₯<ed>΄<ec> <ec>¬<ec>©<ed>λ©<b4> <eb><eb>€.

### strip(): μ’μ° κ³΅λ°±/λ¬Έμ <ec> κ±<b0>


{% highlight python %}
x = '      hello     '
print(x.strip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

λ¬Έμ<eb> <eb>€<ec>κ³<bc> κ°μ΄ <ec> κ±°ν<eb>€.


{% highlight python %}
x = 'helloh'
print(x.strip('h'))
{% endhighlight %}



{% highlight text %}
## ello
{% endhighlight %}

<ec><eb> `lstrip()`κ³<bc> `rstrip()`<eb> <ec>΄<ec><99>κ°μ΄ <ec>¬<ec>©<ed>λ©<b4> <eb><eb>€.

<br>

### lstrip()

<ec>λ³Έλ¬Έ<ec><ec>΄ <ec>Όμͺ½μ κ³΅λ°±<ec> <ec> κ±°ν<eb>€.


{% highlight python %}
x = '      hello     '
print(x.lstrip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rstrip()

<ec>λ³Έλ¬Έ<ec><ec>΄ <ec>€λ₯Έμͺ½<ec> κ³΅λ°±<ec> <ec> κ±°ν<eb>€.


{% highlight python %}
x = '      hello     '
print(x.rstrip())
{% endhighlight %}



{% highlight text %}
##       hello
{% endhighlight %}

<br>

***

## λ¬Έμ<ec>΄ <ed><83><ec> <ed><ec>Έ

### isalpha(): <ec><ed>λ²<b3>,<ed>κΈ<ec>Έμ§ <ed><ec>Έ

<ec>λ³<b8> λ¬Έμ<ec>΄<ec>΄ <ec>«<ec>, κΈ°νΈλ₯<bc> <ec> <ec>Έ<ed> <ec><ed>λ²<b3>, <ed>κΈλ‘λ§ <ec>΄λ£¨μ΄μ‘λμ§ <ed><ec>Έ<ed>  <ec> <ec><eb>€.


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
print('<U+653C><U+3E63><U+653C><U+3E62><U+653C><U+3E64><U+653C><U+3E63>Έ<U+653C><U+3E63>'.isalpha())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### isalnum(): <ec><ed>λ²<b3>, <ed>κΈ, <ec>«<ec><ec>Έμ§ <ed><ec>Έ

<ec>λ³Έλ¬Έ<ec><ec>΄<ec>΄ <ec><ed>λ²<b3>, <ed>κΈ, <ec>«<ec>λ‘λ§ <ec>΄λ£¨μ΄<ec> Έ<ec><eb>μ§ <ed><ec>Έ


{% highlight python %}
x = 'hello'
y = 'hello2018'
z = '<U+653C><U+3E63><U+653C><U+3E62><U+653C><U+3E64><U+653C><U+3E63>Έ<U+653C><U+3E63>'
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

### isnumeric(): <ec>«<ec>λ‘λ§ <ec>΄λ£¨μ΄μ§μ<a7> <ed><ec>Έ

<ec>λ³Έλ¬Έ<ec><ec>΄<ec>΄ <ec>«<ec>λ‘λ§ <ec>΄λ£¨μ΄<ec> Έ<ec><eb>μ§ <ed><ec>Έ. λ§μ½ <ed><83><ec><ec>΄ <ec>«<ec><ec>΄λ©<b4> <ec>€λ₯κ<b0> λ°μ<ed><eb>€. 


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

## λ¬Έμ<ec>΄ <ec>μΉ<98> κ²<ec>

### index(): index<ec>μΉ<98> λ°ν(<ec><ec><ec> <ec>€λ₯<98>)

<ec>λ³<b8> λ¬Έμ<ec>΄<ec><ec> λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄<ec>΄ μ‘΄μ¬<ed><eb> <ec>μΉλ<a5><bc> <ec><ec><ec>λΆ<ed>° μ°Ύλ<eb>€. <ec><ec>Όλ©<b4> **<ec>€λ₯<98>**κ° λ°μ<ed><eb>€. <ec>΄<eb> `find()`<ec><99> <eb>€λ₯<b8> <ec> <ec>΄<eb>€.


{% highlight python %}
x = 'hello'
print(x.index('e'))
{% endhighlight %}



{% highlight text %}
## 1
{% endhighlight %}

<br>

### find(): index <ec>μΉ<98> λ°ν(<ec><ec><ec> -1)

<ec>λ³<b8> λ¬Έμ<ec>΄<ec><ec> λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄<ec>΄ μ‘΄μ¬<ed><eb>μ§ <ec>μΉλ<a5><bc> <ec><ec><ec>λΆ<ed>° μ°Ύλ<eb>€. λ§μ½ μ‘΄μ¬<ed>μ§ <ec><ec>Όλ©<b4> `-1`λ‘<9c> <eb><ec>¨<eb>€.


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

### rfind(): index <ec>μΉ<98> λ°ν(<eb>€<ec><ec> κ²<ec>)

<ec>λ³Έλ¬Έ<ec><ec>΄<ec><ec> λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄<ec>΄ μ‘΄μ¬<ed><eb> <ec>μΉλ<a5><bc> <eb>€<ec><ec>λΆ<ed>° μ°Ύλ<eb>€. 


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

κ²°κ³Όλ₯<bc> λ³΄λ©΄ `find()`<ec><99> κ°μ<9d> κ²<ec>κ²°κ³Όλ₯<bc> λ°ν<ed><eb>€.

<br>

***

## κΈ°ν<83> λ¬Έμ <ed>¨<ec>

### replace(): <ed>Ή<ec>  λ¬Έμ<ec>΄<ec> μ°Ύμ λ³κ²<bd>

<ec>λ³Έλ¬Έ<ec><ec>΄<ec><ec> <ec>΄<eb>€ λ¬Έμ<ec>΄<ec> μ°Ύμ<ec> <ec>λ‘μ΄ λ¬Έμ<ec>΄λ‘<9c> λ³κ²<bd>


{% highlight python %}
x = 'hello world'
x = x.replace('hello','python') # λ³κ²½κ°<U+653C><U+3E63> <U+653C><U+3E64> <U+653C><U+3E62>Ή<U+653C><U+3E64>΄μ£Όμ΄<U+653C><U+3E63>Ό <U+653C><U+3E64>¨
print(x) 
{% endhighlight %}



{% highlight text %}
## python world
{% endhighlight %}

<br>

### split(): λ¬Έμ<ec>΄ λΆν 

<ec>λ³Έλ¬Έ<ec><ec>΄<ec> λ§€κ°λ³<ec>λ‘<9c> <ec><eb> ₯<ed> λ¬Έμ<ec>΄<ec> κΈ°μ<a4><ec>Όλ‘<9c> <ec>λ³Έλ¬Έ<ec><ec>΄<ec> <eb><eb>  λ¦¬μ€<ed>Έλ‘<9c> λ§λ <eb>€.


{% highlight python %}
x = 'hello,world'
x = x.split(',')
print(x)
{% endhighlight %}



{% highlight text %}
## ['hello', 'world']
{% endhighlight %}

<br>

### join(): <ec>λ³Έλ¬Έ<ec> <ec>¬<ec>΄<ec> <ed>Ή<ec>₯ λ¬Έμ μΆκ<b0>

<ec>λ³<b8> κΈ<ec> <ec>¬<ec>΄<ec> <ed>Ή<ec> <ed> λ¬Έμ<ec>΄<ec> μΆκ<b0><ed><eb>€.


{% highlight python %}
x = 'abcdefg'
x = ','.join(x)
print(x)
{% endhighlight %}



{% highlight text %}
## a,b,c,d,e,f,g
{% endhighlight %}

<br>

### input(): <ec><eb> ₯κ°μ λ¬Έμλ‘<9c> λ°μ

<ec><eb> ₯κ°μ λ¬Έμ<ec>΄λ‘<9c> λ°λ <ed>¨<ec><ec>΄<eb>€.

```
x = input()

x = int(input()) # <ec>«<ec>λ₯<bc> <ec><eb> ₯<ed>  <ec>
```

***
