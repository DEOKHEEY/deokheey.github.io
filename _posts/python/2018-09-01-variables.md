---
layout: post
title: "[Python] <ec> „<ec>—­ë³€<ec>ˆ˜<ec><99>€ ì§€<ec>—­ë³€<ec>ˆ˜"
date: "2018-09-01"
excerpt: "<ed>ŒŒ<ec>´<ec>¬<ec>— <ec> „<ec>—­ë³€<ec>ˆ˜, ì§€<ec>—­ë³€<ec>ˆ˜ë¥<bc> <ed>• <eb>‹¹<ed>•˜<eb>Š” ë°©ë²•"
output: github_document
tag:
    [python, variable]
comments: true
categories:
  Python
---

## <ec> „<ec>—­ë³€<ec>ˆ˜/ì§€<ec>—­ë³€<ec>ˆ˜

-<ec> „<ec>—­ë³€<ec>ˆ˜(global): <ed>”„ë¡œê·¸<eb>¨<ec>´ ì¢…ë£Œ<eb> <eb>•Œê¹Œì<a7>€ <ec>–´<eb>””<ec>„œ<eb>“ ì§€ <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>Š” ë³€<ec>ˆ˜
-ì§€<ec>—­ë³€<ec>ˆ˜(local): <ed>•¨<ec>ˆ˜ <ec>•ˆ<ec>—<ec>„œë§<8c> <ec>‚¬<ec>š©<ed>•˜<eb>Š” ë³€<ec>ˆ˜

<br>

<ec>•„<eb>˜ë¥<bc> ë³´ê³  ì§€<ec>—­ë³€<ec>ˆ˜<ec><99>€ <ec> „<ec>—­ë³€<ec>ˆ˜ë¥<bc> <ec>´<ed>•´<ed>•´ë³´ì.


{% highlight python %}
x = 10 # global ë³€<U+653C><U+3E63>ˆ˜
def f(x): # parameter(ë§¤ê°œë³€<U+653C><U+3E63>ˆ˜)
    print("x = ", x)
    x = 20 # local ë³€<U+653C><U+3E63>ˆ˜
    print("x = ", x)
f(x) # <U+653C><U+3E63>š°<U+653C><U+3E63>„  <U+653C><U+3E63> „<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜ 10<U+653C><U+3E63>´ <U+653C><U+3E62>“¤<U+653C><U+3E63>–´ê°€ê³ãå<U+3E30> ì§€<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜<U+653C><U+3E63>˜ 10<U+653C><U+3E63>´ <U+653C><U+3E63>´<U+653C><U+3E64>›„<U+653C><U+3E63>— ì¶œë ¥<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.
{% endhighlight %}



{% highlight text %}
## x =  10
## x =  20
{% endhighlight %}



{% highlight python %}
print(x) # <U+653C><U+3E63> „<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜ ì¶œë ¥
{% endhighlight %}



{% highlight text %}
## 10
{% endhighlight %}

<br>

<ec> „<ec>—­ë³€<ec>ˆ˜ <ec>„ <ec>–¸<ec><9d>€ `global`<ec>„ <ec>‚¬<ec>š©<ed>•˜<ec>—¬ <ec>„ <ec>–¸<ed>•œ<eb>‹¤.


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
print(x) # <U+653C><U+3E64>•¨<U+653C><U+3E63>ˆ˜ <U+653C><U+3E62>‚´<U+653C><U+3E63>—<U+653C><U+3E63>„œ <U+653C><U+3E63>„ <U+653C><U+3E63>–¸<U+653C><U+3E62>œ x<U+653C><U+3E62>Š” <U+653C><U+3E63> „<U+653C><U+3E63>—­ë³€<U+653C><U+3E63>ˆ˜<U+653C><U+3E62>¼<U+653C><U+3E62>Š” ê²ƒì„ <U+653C><U+3E63>•Œ <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E63>Œ
{% endhighlight %}



{% highlight text %}
## 20
{% endhighlight %}
