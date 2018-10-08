---
layout: post
title: "[Python] str<ed>˜•<ec>˜ function"
date: "2018-09-01"
excerpt: "<ed>ŒŒ<ec>´<ec>¬<ec>—<ec>„œ<ec>˜ ë¬¸ì <ed>•¨<ec>ˆ˜"
output: github_document
tag:
    [python, str, function]
comments: true
categories:
  Python
---

<br>

***

## ë¬¸ì<ed>•¨<ec>ˆ˜

Python<ec>˜ `str`<ed><83>€<ec>…<ec>— <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤. 

***

## ë¬¸ì êµ¬ì¡° <ed>™•<ec>¸

### in <ec>—°<ec>‚°<ec>: ë¬¸ì<ec>—´ ì¡´ì¬<ec>—¬ë¶€ <ed>™•<ec>¸

`in`<ec>—°<ec>‚°<ec>ë¥<bc> <ec>´<ec>š©<ed>•´<ec>„œ ë¬¸ì<ec>—´<ec>˜ ì¡´ì¬<ec>—¬ë¶€ë¥<bc> <ed>™•<ec>¸<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight python %}
x = 'hello'
print('o' in x)
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### startswith(), endswith(): <ed>Š¹<ec> •ë¬¸ìë¡<9c> <ec>‹œ<ec>‘,<eb><eb>‚˜<eb>Š”ì§€ <ed>Œ<eb>‹¨

`startswith()`<eb>Š” <ec>›ë³<b8> ë¬¸ì<ec>—´<ec>´ ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´ë¡<9c> <ec>‹œ<ec>‘<eb>˜<eb>Š”ì§€ë¥<bc>, `endswith()`<eb>Š” <ec>›ë³<b8> ë¬¸ì<ec>—´<ec>´ <ed>Š¹<ec> • ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ìë¡<9c> <eb><eb>‚˜<eb>Š”ì§€ë¥<bc> <ed>Œ<eb>‹¨<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


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

### count(): <ed>Š¹<ec> • ë¬¸ì<ec>—´ ê°<af><ec>ˆ˜ ë¦¬í„´

<ec>›ë³<b8> ë¬¸ì<ec>—´<ec>•ˆ<ec>— ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´<ec>´ ëª‡ê°œ <ec>ˆ<eb>Š”ì§€ <ec>•Œ<eb> ¤ì£¼ëŠ” <ed>•¨<ec>ˆ˜


{% highlight python %}
x = 'datamining'
print(x.count('a'))
{% endhighlight %}



{% highlight text %}
## 2
{% endhighlight %}

<br>

***

## <eb><8c>€<ec>†Œë¬¸ì ê´€<eb> ¨ <ed>•¨<ec>ˆ˜

### upper(), lower(): <eb><8c>€ë¬¸ì, <ec>†Œë¬¸ìë¡<9c> ë³€<ed>™˜

<ec>›ë³<b8> ë¬¸ì<ec>—´<ec>„ <eb><8c>€ë¬¸ì <eb>˜<eb>Š” <ec>†Œë¬¸ìë¡<9c> ë³€<ed>™˜<ed>•´ì£¼ëŠ” <ed>•¨<ec>ˆ˜


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

### capitalize(), title(): ì²«ê<b8>€<ec>ë¥<bc> <eb><8c>€ë¬¸ìë¡<9c> ë³€<ed>™˜

`capitalize()`<eb>Š” <ec>›ë³<b8> ë¬¸ì<ec>—´<ec>˜ ì²«ê<b8>€<ec>ë¥<bc> <eb><8c>€ë¬¸ìë¡<9c> ë³€<ed>™˜<ed>•´ì¤€<eb>‹¤. <ed>•˜ì§€ë§<8c> `title()`<ec><9d>€ <eb>‹¨<ec>–´ ë³„ë¡œ ëª¨ë“  ë¬¸ì<ec>—´<ec>„ <eb><8c>€ë¬¸ìë¡<9c> ë³€<ed>™˜<ed>•´ì¤€<eb>‹¤.


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

### swapcase(): <eb><8c>€<ec>†Œë¬¸ìë¥<bc> ë³€<ed>™˜

ë¬¸ì<ec>—´<ec>˜ <eb><8c>€ë¬¸ì<eb>Š” <ec>†Œë¬¸ìë¡<9c>, <ec>†Œë¬¸ì<eb>Š” <eb><8c>€ë¬¸ìë¡<9c> ë³€<ed>™˜<ed>•´ì¤€<eb>‹¤.


{% highlight python %}
x = 'Hello world'
print(x.swapcase())
{% endhighlight %}



{% highlight text %}
## hELLO WORLD
{% endhighlight %}

<br>

***

## ë¬¸ì<ec>—´ ë°°ì¹˜ <ed>•¨<ec>ˆ˜

### center(): ì§€<ec> • ê³µê°„<ec>—<ec>„œ ì¤‘ì•™ ë°°ì¹˜


{% highlight python %}
x = 'hello'
print(x.center(20))
{% endhighlight %}



{% highlight text %}
##        hello
{% endhighlight %}

<br>

### ljust(): ì§€<ec> • ê³µê°„<ec>—<ec>„œ ì¢Œì¸¡ ë°°ì¹˜


{% highlight python %}
x = 'hello'
print(x.ljust(20))
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rjust(): ì§€<ec> • ê³µê°„<ec>—<ec>„œ <ec>š°ì¸<a1> ë°°ì¹˜


{% highlight python %}
x = 'hello'
print(x.rjust(20))
{% endhighlight %}



{% highlight text %}
##                hello
{% endhighlight %}

<br>

***

## ê³µë°±/ë¬¸ì <ec> œê±<b0> <ed>•¨<ec>ˆ˜

ê³µë°±<ec>„ <ec> œê±°í•˜ê³<a0> <ec>‹¶<ec>„ <ec>‹œ <ed>•¨<ec>ˆ˜ë§<8c> <ec>…<eb> ¥<ed>•˜ë©<b4> <eb>˜ì§€ë§<8c>,  ë¬¸ìë¥<bc> <ec> œê±°í•˜ê³<a0> <ec>‹¶<ec>„ <ec>‹œ<ec>—<eb>Š” <ed>Š¹<ec> • ë¬¸ìë¥<bc> <ec>…<eb> ¥<ed>•´<ec>„œ <ec>‚¬<ec>š©<ed>•˜ë©<b4> <eb>œ<eb>‹¤.

### strip(): ì¢Œìš° ê³µë°±/ë¬¸ì <ec> œê±<b0>


{% highlight python %}
x = '      hello     '
print(x.strip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

ë¬¸ì<eb>Š” <eb>‹¤<ec>Œê³<bc> ê°™ì´ <ec> œê±°í•œ<eb>‹¤.


{% highlight python %}
x = 'helloh'
print(x.strip('h'))
{% endhighlight %}



{% highlight text %}
## ello
{% endhighlight %}

<ec>•„<eb>˜ `lstrip()`ê³<bc> `rstrip()`<eb>„ <ec>´<ec><99>€ê°™ì´ <ec>‚¬<ec>š©<ed>•˜ë©<b4> <eb>œ<eb>‹¤.

<br>

### lstrip()

<ec>›ë³¸ë¬¸<ec><ec>—´ <ec>™¼ìª½ì— ê³µë°±<ec>„ <ec> œê±°í•œ<eb>‹¤.


{% highlight python %}
x = '      hello     '
print(x.lstrip())
{% endhighlight %}



{% highlight text %}
## hello
{% endhighlight %}

<br>

### rstrip()

<ec>›ë³¸ë¬¸<ec><ec>—´ <ec>˜¤ë¥¸ìª½<ec>— ê³µë°±<ec>„ <ec> œê±°í•œ<eb>‹¤.


{% highlight python %}
x = '      hello     '
print(x.rstrip())
{% endhighlight %}



{% highlight text %}
##       hello
{% endhighlight %}

<br>

***

## ë¬¸ì<ec>—´ <ed><83>€<ec>… <ed>™•<ec>¸

### isalpha(): <ec>•Œ<ed>ŒŒë²<b3>,<ed>•œê¸€<ec>¸ì§€ <ed>™•<ec>¸

<ec>›ë³<b8> ë¬¸ì<ec>—´<ec>´ <ec>ˆ«<ec>, ê¸°í˜¸ë¥<bc> <ec> œ<ec>™¸<ed>•œ <ec>•Œ<ed>ŒŒë²<b3>, <ed>•œê¸€ë¡œë§Œ <ec>´ë£¨ì–´ì¡ŒëŠ”ì§€ <ed>™•<ec>¸<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


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
print('<U+653C><U+3E63>•ˆ<U+653C><U+3E62>…•<U+653C><U+3E64>•˜<U+653C><U+3E63>„¸<U+653C><U+3E63>š”'.isalpha())
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}

<br>

### isalnum(): <ec>•Œ<ed>ŒŒë²<b3>, <ed>•œê¸€, <ec>ˆ«<ec><ec>¸ì§€ <ed>™•<ec>¸

<ec>›ë³¸ë¬¸<ec><ec>—´<ec>´ <ec>•Œ<ed>ŒŒë²<b3>, <ed>•œê¸€, <ec>ˆ«<ec>ë¡œë§Œ <ec>´ë£¨ì–´<ec> ¸<ec>ˆ<eb>Š”ì§€ <ed>™•<ec>¸


{% highlight python %}
x = 'hello'
y = 'hello2018'
z = '<U+653C><U+3E63>•ˆ<U+653C><U+3E62>…•<U+653C><U+3E64>•˜<U+653C><U+3E63>„¸<U+653C><U+3E63>š”'
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

### isnumeric(): <ec>ˆ«<ec>ë¡œë§Œ <ec>´ë£¨ì–´ì§„ì<a7>€ <ed>™•<ec>¸

<ec>›ë³¸ë¬¸<ec><ec>—´<ec>´ <ec>ˆ«<ec>ë¡œë§Œ <ec>´ë£¨ì–´<ec> ¸<ec>ˆ<eb>Š”ì§€ <ed>™•<ec>¸. ë§Œì•½ <ed><83>€<ec>…<ec>´ <ec>ˆ«<ec><ec>´ë©<b4> <ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>•œ<eb>‹¤. 


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

## ë¬¸ì<ec>—´ <ec>œ„ì¹<98> ê²€<ec>ƒ‰

### index(): index<ec>œ„ì¹<98> ë°˜í™˜(<ec>—†<ec>„<ec>‹œ <ec>˜¤ë¥<98>)

<ec>›ë³<b8> ë¬¸ì<ec>—´<ec>•ˆ<ec>— ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´<ec>´ ì¡´ì¬<ed>•˜<eb>Š” <ec>œ„ì¹˜ë<a5><bc> <ec>•<ec>—<ec>„œë¶€<ed>„° ì°¾ëŠ”<eb>‹¤. <ec>—†<ec>œ¼ë©<b4> **<ec>˜¤ë¥<98>**ê°€ ë°œìƒ<ed>•œ<eb>‹¤. <ec>´<eb>Š” `find()`<ec><99>€ <eb>‹¤ë¥<b8> <ec> <ec>´<eb>‹¤.


{% highlight python %}
x = 'hello'
print(x.index('e'))
{% endhighlight %}



{% highlight text %}
## 1
{% endhighlight %}

<br>

### find(): index <ec>œ„ì¹<98> ë°˜í™˜(<ec>—†<ec>„<ec>‹œ -1)

<ec>›ë³<b8> ë¬¸ì<ec>—´<ec>•ˆ<ec>— ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´<ec>´ ì¡´ì¬<ed>•˜<eb>Š”ì§€ <ec>œ„ì¹˜ë<a5><bc> <ec>•<ec>—<ec>„œë¶€<ed>„° ì°¾ëŠ”<eb>‹¤. ë§Œì•½ ì¡´ì¬<ed>•˜ì§€ <ec>•Š<ec>œ¼ë©<b4> `-1`ë¡<9c> <eb>‚˜<ec>˜¨<eb>‹¤.


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

### rfind(): index <ec>œ„ì¹<98> ë°˜í™˜(<eb>’¤<ec>—<ec>„œ ê²€<ec>ƒ‰)

<ec>›ë³¸ë¬¸<ec><ec>—´<ec>•ˆ<ec>— ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´<ec>´ ì¡´ì¬<ed>•˜<eb>Š” <ec>œ„ì¹˜ë<a5><bc> <eb>’¤<ec>—<ec>„œë¶€<ed>„° ì°¾ëŠ”<eb>‹¤. 


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

ê²°ê³¼ë¥<bc> ë³´ë©´ `find()`<ec><99>€ ê°™ì<9d>€ ê²€<ec>ƒ‰ê²°ê³¼ë¥<bc> ë°˜í™˜<ed>•œ<eb>‹¤.

<br>

***

## ê¸°í<83>€ ë¬¸ì <ed>•¨<ec>ˆ˜

### replace(): <ed>Š¹<ec> • ë¬¸ì<ec>—´<ec>„ ì°¾ì•„ ë³€ê²<bd>

<ec>›ë³¸ë¬¸<ec><ec>—´<ec>—<ec>„œ <ec>–´<eb>–¤ ë¬¸ì<ec>—´<ec>„ ì°¾ì•„<ec>„œ <ec>ƒˆë¡œìš´ ë¬¸ì<ec>—´ë¡<9c> ë³€ê²<bd>


{% highlight python %}
x = 'hello world'
x = x.replace('hello','python') # ë³€ê²½ê°’<U+653C><U+3E63>„ <U+653C><U+3E64>• <U+653C><U+3E62>‹¹<U+653C><U+3E64>•´ì£¼ì–´<U+653C><U+3E63>•¼ <U+653C><U+3E64>•¨
print(x) 
{% endhighlight %}



{% highlight text %}
## python world
{% endhighlight %}

<br>

### split(): ë¬¸ì<ec>—´ ë¶„í• 

<ec>›ë³¸ë¬¸<ec><ec>—´<ec>— ë§¤ê°œë³€<ec>ˆ˜ë¡<9c> <ec>…<eb> ¥<ed>•œ ë¬¸ì<ec>—´<ec>„ ê¸°ì<a4>€<ec>œ¼ë¡<9c> <ec>›ë³¸ë¬¸<ec><ec>—´<ec>„ <eb>‚˜<eb>ˆ  ë¦¬ìŠ¤<ed>Š¸ë¡<9c> ë§Œë“ <eb>‹¤.


{% highlight python %}
x = 'hello,world'
x = x.split(',')
print(x)
{% endhighlight %}



{% highlight text %}
## ['hello', 'world']
{% endhighlight %}

<br>

### join(): <ec>›ë³¸ë¬¸<ec> <ec>‚¬<ec>´<ec>— <ed>Š¹<ec>¥ ë¬¸ì ì¶”ê<b0>€

<ec>›ë³<b8> ê¸€<ec> <ec>‚¬<ec>´<ec>— <ed>Š¹<ec> •<ed>•œ ë¬¸ì<ec>—´<ec>„ ì¶”ê<b0>€<ed>•œ<eb>‹¤.


{% highlight python %}
x = 'abcdefg'
x = ','.join(x)
print(x)
{% endhighlight %}



{% highlight text %}
## a,b,c,d,e,f,g
{% endhighlight %}

<br>

### input(): <ec>…<eb> ¥ê°’ì„ ë¬¸ìë¡<9c> ë°›ìŒ

<ec>…<eb> ¥ê°’ì„ ë¬¸ì<ec>—´ë¡<9c> ë°›ëŠ” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤.

```
x = input()

x = int(input()) # <ec>ˆ«<ec>ë¥<bc> <ec>…<eb> ¥<ed>•  <ec>‹œ
```

***
