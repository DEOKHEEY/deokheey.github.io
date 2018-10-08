---
layout: post
title: "[Python] Exception"
date: "2018-09-01"
excerpt: "<ed>ŒŒ<ec>´<ec>¬<ec>—<ec>„œ <ec>˜ˆ<ec>™¸ì²˜ë¦¬ë¥<bc> <ed>•´ë³´ì"
output: github_document
tag:
    [python, exception]
comments: true
categories:
  Python
---

## <ec>˜ˆ<ec>™¸<ec>‚¬<ed>•­ ì²˜ë¦¬

<ec>‹¤<ed>–‰ì¤<91> ë°œìƒ<ed>•œ <ec>˜¤ë¥˜ì— <eb><8c>€<ed>•´<ec>„œ ì²˜ë¦¬<ed>•  <ec>ˆ˜ <ec>ˆ<eb>Š” ë°©ë²•<ec>´<eb>‹¤. ê¸°ë³¸<ec> <ec>œ¼ë¡<9c> `try`<ec> ˆê³<bc> `except`<ec> ˆë¡<9c> ë§Œë“¤ <ec>ˆ˜ <ec>ˆ<eb>‹¤. `try`<ec> ˆ<ec>— ë¡œì§<ec>„ ê¸°ì…<ed>•˜ê³<a0> <ec>˜ˆ<ec>™¸<ec>‚¬<ed>•­<ec>— <eb><8c>€<ed>•´<ec>„œ<eb>Š” `except`<ec> ˆ<ec>— êµ¬ì„±<ed>•˜ë©<b4> <eb>œ<eb>‹¤.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,5)
    print(z)
    
except:
    print("<U+653C><U+3E63>˜¤ë¥˜ê<U+623C><U+3E30>€ ë°œìƒ<U+653C><U+3E64>–ˆ<U+653C><U+3E63>Šµ<U+653C><U+3E62>‹ˆ<U+653C><U+3E62>‹¤.")
{% endhighlight %}



{% highlight text %}
## 2.0
{% endhighlight %}

<eb>‹¤<ec>Œê³<bc> ê°™ì´ <ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>„ <eb>•Œ<eb>Š” `except`<ec> ˆë¡<9c> ë¹ ì<a7>€ê²<8c> <eb>œ<eb>‹¤.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,0)
    print(z)
    
except:
    print("<ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>Šµ<eb>‹ˆ<eb>‹¤.")
{% endhighlight %}



{% highlight text %}
## ¿À·ù°¡ ¹ß»ıÇß½À´Ï´Ù.
{% endhighlight %}

***

### <ec>—¬<eb>Ÿ¬ <ec>ƒ<ed>™©<ec>— <eb><8c>€<ed>•œ <ec>˜¤ë¥˜ì²˜ë¦<ac>

<ec>ƒ<ec>„¸ <ec>˜¤ë¥˜ì— <eb><8c>€<ed>•´<ec>„œ(<ec>—¬ê¸°ì„œ<eb>Š” <eb>‚˜<eb>ˆ—<ec>…ˆ <ed>•¨<ec>ˆ˜<ec>— <eb><8c>€<ed>•´<ec>„œ) ê°ê°<ec>˜ <ec>ƒ<ed>™©<ec>— ë§ëŠ” <ec>˜ˆ<ec>™¸ì²˜ë¦¬ë¥<bc> <ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤. 


{% highlight python %}
def divide(x,y):
    return x/y
  
try:
    z = divide(10,0)
    print(z)
    
    z = divide(10,'<ec>¼')
    print(z)
    
    
except TypeError:
    print("<ec>¸<ec>ˆ˜ê°’ì„ <ec>ˆ«<ec>ë¡<9c> <ec>…<eb> ¥<ed>•˜<ec>„¸<ec>š”")
except ZeroDivisionError:
    print("0ê°’ìœ¼ë¡<9c> <eb>‚˜<eb>ˆŒ <ec>ˆ˜ <ec>—†<ec>Šµ<eb>‹ˆ<eb>‹¤.")
    
except: 
    print("<ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>Šµ<eb>‹ˆ<eb>‹¤.")
else: # except<ec> ˆ<ec>´ <eb><eb>‚˜ë©<b4> ì¶œë ¥
    print("ê²°ê³¼ : {}".format(z))
finally: # <ec>˜¤ë¥<98> ë°œìƒ<ec>—¬ë¶€<ec><99>€ <ec>ƒê´€<ec>—†<ec>´ ë°˜ë“œ<ec>‹œ ì¶œë ¥
    print("<ed>”„ë¡œê·¸<eb>¨ ì¢…ë£Œ")
{% endhighlight %}



{% highlight text %}
## 0°ªÀ¸·Î ³ª´­ ¼ö ¾ø½À´Ï´Ù.
## ÇÁ·Î±×·¥ Á¾·á
{% endhighlight %}

#### else<ec> ˆê³<bc> finally<ec> ˆ

`else`<ec> ˆ<ec><9d>€ `except`<ec> ˆ<ec>´ <eb><eb>‚˜ë©<b4> ë°”ë¡œ ì¶œë ¥<ed>•´ì£¼ê³  `finally`<ec> ˆ<ec><9d>€ <ec>˜¤ë¥<98> ë°œìƒ<ec>—¬ë¶€<ec><99>€ <ec>ƒê´€<ec>—†<ec>´ <ed>”„ë¡œê·¸<eb>¨ ì¢…ë£Œ <ec>‹œ ì¶œë ¥<ed>•´ì¤€<eb>‹¤.

***

### <ec>œ <ec><a0>€ê°€ <ec>˜ˆ<ec>™¸<ec>‚¬<ed>•­ ë§Œë“¤ê¸<b0>

<ec>œ <ec><a0>€ê°€ ì§ì ‘ <ec>˜ˆ<ec>™¸<ec>‚¬<ed>•­<ec>„ ë§Œë“¤<ec>–´ `except`<ec> ˆë¡<9c> <ec>´<eb>Œ <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight python %}
def func(arg):
    try:
        if arg < 1 or arg > 10:
            raise Exception("<ec>œ <ed>š¨<ed>•˜ì§€ <ec>•Š<ec><9d>€ <ec>ˆ«<ec><ec>…<eb>‹ˆ<eb>‹¤.:{}".format(arg))
        else:
            print("<ec>…<eb> ¥<ed>•œ <ec>ˆ˜<eb>Š” {} <ec>…<eb>‹ˆ<eb>‹¤.".format(arg))
    except Exception as error:
        print("<ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>Šµ<eb>‹ˆ<eb>‹¤.{}".format(error))
func(10)
{% endhighlight %}



{% highlight text %}
## ÀÔ·ÂÇÑ ¼ö´Â 10 ÀÔ´Ï´Ù.
{% endhighlight %}

<ec>—¬ê¸°ì„œ `as error`<eb>Š” <ec>˜¤ë¥<98> ë©”ì‹œì§€ë¥<bc> ì¶œë ¥<ed>•  <ec>ˆ˜ <ec>ˆê²<8c> <ed>•œ<eb>‹¤. `SQL`<ec>—<ec>„œ `sqlerrm`ê³<bc> ê°™ì<9d>€ <ec>˜ë¯¸ì´<eb>‹¤. ì¢€ <eb>” <ec><ec>„¸<ed>•œ <eb>‚´<ec>š©<ec><9d>€ <ec>•„<eb>˜ë¥<bc> ì°¸ê³ <ed>•˜<ec>.

***

### <ec>˜¤ë¥<98> ë©”ì‹œì§€<ec><99>€ <ed>•¨ê»<98> ì¶œë ¥(as ~)


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except:
    print("<ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>Šµ<eb>‹ˆ<eb>‹¤")
{% endhighlight %}



{% highlight text %}
## ¿À·ù°¡ ¹ß»ıÇß½À´Ï´Ù
{% endhighlight %}

ë¦¬ìŠ¤<ed>Š¸ë³€<ec>ˆ˜ `lst`<eb>Š” index ë²ˆí˜¸ê°€ 2ë²ˆê¹Œì§€ ë°°ì •<eb>˜<ec>–´ <ec>ˆ<ec>–´<ec>„œ <ec>˜¤ë¥˜ê<b0>€ <eb>‚œ<eb>‹¤. <ed>•˜ì§€ë§<8c> <ec>–´<eb>–¤ <ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<eb>Š”ì§€ ì¶œë ¥<ed>•˜ì§€ ëª»í•œ<eb>‹¤.


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except Exception as error: # <ec>˜¤<eb>¼<ed>´<ec>—<ec>„œ<ec>˜ sqlerrmê³<bc> ê°™ì<9d>€ <ec>˜ë¯<b8>
    print(error)
    print("<ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>–ˆ<ec>Šµ<eb>‹ˆ<eb>‹¤")
{% endhighlight %}



{% highlight text %}
## list index out of range
## ¿À·ù°¡ ¹ß»ıÇß½À´Ï´Ù
{% endhighlight %}

<ec>œ„<ec><99>€ ê°™ì´ `as error`ë¥<bc> <ec>‚¬<ec>š©<ed>•˜<ec>—¬ <ec>–´<eb>–¤ <ec>˜¤ë¥˜ê<b0>€ ë°œìƒ<ed>•œì§€ê¹Œì<a7>€ ì¶œë ¥<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.
