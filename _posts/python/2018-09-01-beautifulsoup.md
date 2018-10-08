---
layout: post
title: "[Python] BeautifulSoup"
date: "2018-10-01"
excerpt: "<ec>›¹ <ed>¬ë¡¤ë§<ec>„ <ed>•´ë³´ì"
output: github_document
tag:
    [python, beautifulsoup]
comments: true
categories:
  Python
---




## BeautifulSoup

`BeautifulSoup`<eb>Š” <ec>›¹<ec>— <ec>ˆ<eb>Š” <eb>°<ec>´<ed>„°ë¥<bc> <ed>¬ë¡¤ë§ <ed>˜¹<ec><9d>€ <ec>Š¤<ed>¬<eb>©<ed>•‘<ed>•  <eb>•Œ <ec>‚¬<ec>š©<ed>•˜<eb>Š” <eb>¼<ec>´ë¸ŒëŸ¬ë¦¬ì´<eb>‹¤. <ec>‚¬<ec>š©ë²•ì„ <ec>•Œ<ec>•„ë³´ê¸° <ec>•<ec>„œ <eb>¼<ec>´ë¸ŒëŸ¬ë¦¬ê<b0>€ <ec>„¤ì¹˜ë˜<ec>–´<ec>ˆì§€ <ec>•Š<eb>‹¤ë©<b4> <ec>„¤ì¹˜ë<b6>€<ed>„° <ed>•´ì£¼ì.

```
# Anaconda Prompt<ec>„œ <eb>‹¤<ec>Œ<ec>„ <ec>‹¤<ed>–‰<ec>‹œì¼œì<a4>€<eb>‹¤.
$ pip install beautifulsoup4
```

***

### tagë¡<9c> ì¶”ì¶œ<ed>•˜ê¸<b0>

 <ec>„¤ì¹˜ê<b0>€ <eb>˜<ec>—ˆ<eb>‹¤ë©<b4> <ec>‚¬<ec>š©ë²•ì— <eb><8c>€<ed>•´ <ec>•Œ<ec>•„ë³´ì.


{% highlight python %}
from bs4 import BeautifulSoup
# html <U+653C><U+3E63>˜ˆ<U+653C><U+3E63> œ <U+653C><U+3E63>ƒ<U+653C><U+3E63>„±
html = """
            <html>
                <body>
                    <h1> Data Science </h1>
                        <p> data analysis 1 </p>
                        <p> data analysis 2 </p>
                        <p> data analysis 3 </p>
                </body>
            </html>
        """
soup = BeautifulSoup(html,"html.parser") # html.parser<U+653C><U+3E62>¼<U+653C><U+3E62>Š” ë¶„ì„ê¸°ëãå<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©
# <U+653C><U+3E62>‹¨<U+653C><U+3E63> <U+653C><U+3E63><U+393C><U+3E64>€ <U+653C><U+3E63>›¹<U+653C><U+3E63>—<U+653C><U+3E63>„œ <U+653C><U+3E63>›<U+653C><U+3E64>•˜<U+653C><U+3E62>Š” <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„°ë¥<U+623C><U+3E63> ë°”ë¡œ <U+653C><U+3E62>Œê³ ì˜¤ì§€ ëª»í•˜ê³ãå<U+3E30> html<U+653C><U+3E63>„ <U+653C><U+3E62>“¤ê³ ì<U+393C><U+3E39>€<U+653C><U+3E63>„œ <U+653C><U+3E63>‘<U+653C><U+3E63>—…<U+653C><U+3E63>„ <U+653C><U+3E64>•´<U+653C><U+3E63>•¼<U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
#
# <U+653C><U+3E63>›<U+653C><U+3E64>•˜<U+653C><U+3E62>Š” <U+653C><U+3E64>ƒœê·<U+623C><U+3E38> <U+653C><U+3E62>‚´<U+653C><U+3E63>š©<U+653C><U+3E63>„ ê°€<U+653C><U+3E63> ¸<U+653C><U+3E63>˜¤ê¸<U+623C><U+3E30> 
## h1 <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„° ì¶”ì¶œ
h1 = soup.html.body.h1 # html -> body -> h1
print(h1.string) # ë¬¸ì<U+653C><U+3E63>—´ë§<U+383C><U+3E63> <U+653C><U+3E62>“¤ê³ ì˜¤ê¸<U+623C><U+3E30>
## p <U+653C><U+3E64>ƒœê·<U+623C><U+3E38> <U+653C><U+3E62>°<U+653C><U+3E63>´<U+653C><U+3E64>„° ì¶”ì¶œ
{% endhighlight %}



{% highlight text %}
##  Data Science
{% endhighlight %}



{% highlight python %}
p1 = soup.html.body.p 
print(p1.string) # p tagê°€ 3ê°<U+393C><U+3E63> <U+653C><U+3E63>ˆì§€ë§<U+383C><U+3E63> ì²«ë²ˆì§<U+623C><U+3E38> ê²ƒë§Œ ì¶”ì¶œ<U+653C><U+3E62>Œ
## 2ë²ˆì§¸ p tag ì¶”ì¶œ
{% endhighlight %}



{% highlight text %}
##  data analysis 1
{% endhighlight %}



{% highlight python %}
p2 = p1.next_sibling.next_sibling # next_siblingë§<U+383C><U+3E63> ì¶”ì¶œ<U+653C><U+3E64>•˜ë©<U+623C><U+3E34> /n<U+653C><U+3E63>´ ì¶”ì¶œ<U+653C><U+3E62>˜ë¯€ë¡<U+393C><U+3E63> 2ë²<U+383C><U+3E38> <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
print(p2.string)
# 3ë²ˆì§¸ p tag ì¶”ì¶œ
{% endhighlight %}



{% highlight text %}
##  data analysis 2
{% endhighlight %}



{% highlight python %}
p3 = p2.next_sibling.next_sibling 
print(p3.string)
{% endhighlight %}



{% highlight text %}
##  data analysis 3
{% endhighlight %}

***

### <ec>†<ec>„±ê°’ìœ¼ë¡<9c> ì¶”ì¶œ<ed>•˜ê¸<b0>

`html`<ec>—<eb>Š” id, class <eb>“±<ec>˜ <ec>—¬<eb>Ÿ¬ <ec>†<ec>„±<ec>„ ê°€ì§€ê³<a0> <ec>ˆ<eb>‹¤. <ec>†<ec>„±<ec>œ¼ë¡<9c> <eb>°<ec>´<ed>„°ë¥<bc> ì¶”ì¶œ<ed>•˜ë©<b4> <eb>” <ed>ƒœê·¸ë¡œ ì¶”ì¶œ<ed>•˜<eb>Š” ê²<83> ë³´ë‹¤ <eb>” <ed>¸ë¦¬í•  <ec>ˆ˜ <ec>ˆ<eb>‹¤. ê·¸ëŸ¼ <ec>†<ec>„±ê°’ìœ¼ë¡<9c> <ec>›¹<eb>°<ec>´<ed>„°ë¥<bc> ì¶”ì¶œ<ed>•´ë³´ì.


{% highlight python %}
from bs4 import BeautifulSoup
html = """
        <html>
            <body>
                <h1 id = 'title'> beautifulsoup </h1>
                <p id = 'subtitle'> web scraping </p>
                <p> web data extractionê¸<U+623C><U+3E30> </p>
            </body>
        </html>
       """
soup = BeautifulSoup(html,'html.parser')
# .find() <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©
## title ì¶”ì¶œ
title = soup.find(id = 'title')
print(title.string)
{% endhighlight %}



{% highlight text %}
##  beautifulsoup
{% endhighlight %}



{% highlight python %}
sub = soup.find(id = 'subtitle').string ## subtitle ì¶”ì¶œ
print(sub)
{% endhighlight %}



{% highlight text %}
##  web scraping
{% endhighlight %}

<eb>‹¤ë¥<b8> <ec>†<ec>„±<ec>„ ê°€ì§<84> `html` <ec>˜ˆ<ec> œë¥<bc> ë§Œë“¤<ec>–´ ê°’ì„ ì¶”ì¶œ<ed>•´ë³´ì.


{% highlight python %}
from bs4 import BeautifulSoup
html = """
        <html>
            <body>
                <ul>
                    <li><a href='http://www.google.com'> Google </a></li>
                    <li><a href='http://www.amazon.com'> Amazon </a></li>
            <body>
        </html>
       """
soup = BeautifulSoup(html,'html.parser')
# tagë¡<U+393C><U+3E63> ì°¾ê¸°
a_tag = soup.html.body.ul.li.a
print(a_tag.string) # 1ë²ˆì§¸ anchor tagê°€ ì¶”ì¶œ<U+653C><U+3E62>Œ
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find('a').string) # find<U+653C><U+3E62>„ ë§ˆì°¬ê°€ì§€ ì²«ë²ˆì§¸ë§Œ ì°¾ì•„ì£¼ê³  2ë²ˆì§¸ aë¥<U+623C><U+3E63> ì°¾ìãå<U+3E37>€ ëª»í•œ<U+653C><U+3E62>‹¤
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find_all('a')) # .find_aLl() <U+653C><U+3E63>„ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•˜<U+653C><U+3E63>—¬ ëª¨ë“  achor tag ì¶”ì¶œ
{% endhighlight %}



{% highlight text %}
## [<a href="http://www.google.com"> Google </a>, <a href="http://www.amazon.com"> Amazon </a>]
{% endhighlight %}



{% highlight python %}
for i in soup.find_all('a'): # ë£¨í”„ êµ¬ì¡°ë¡<U+393C><U+3E63> stringë§<U+383C><U+3E63> ì¶”ì¶œ<U+653C><U+3E64>•  <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
  print(i.string)
{% endhighlight %}



{% highlight text %}
##  Google 
##  Amazon
{% endhighlight %}

<ec>œ„<ec>˜ <ec>˜ˆ<ec> œ<ec>—<ec>„œ url ì£¼ì†Œë§<8c> ì¶”ì¶œ<ed>•´ë³´ì


{% highlight python %}
from bs4 import BeautifulSoup
html = """
        <html>
            <body>
                <ul>
                    <li><a href='http://www.google.com'> Google </a></li>
                    <li><a href='http://www.amazon.com'> Amazon </a></li>
            <body>
        </html>
       """
soup = BeautifulSoup(html,'html.parser')
# a tag ì¶”ì¶œ(ì²«ë²ˆì§¸ë§Œ ì¶”ì¶œ<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤)
a = soup.a
print('href' in a.attrs) # a tag<U+653C><U+3E63>— href <U+653C><U+3E63>†<U+653C><U+3E63>„±<U+653C><U+3E63>´ <U+653C><U+3E63>ˆ<U+653C><U+3E62>Š”ì§€ <U+653C><U+3E64>™•<U+653C><U+3E63>¸
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(a.attrs) # a tag<U+653C><U+3E63>˜ <U+653C><U+3E63>†<U+653C><U+3E63>„±ê°<U+393C><U+3E32> <U+653C><U+3E64>™•<U+653C><U+3E63>¸
{% endhighlight %}



{% highlight text %}
## {'href': 'http://www.google.com'}
{% endhighlight %}



{% highlight python %}
print(a['href']) # value(url ê°<U+393C><U+3E32>)ë§<U+383C><U+3E63> <U+653C><U+3E64>™•<U+653C><U+3E63>¸ 1
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
print(a.attrs['href']) # value(url ê°<U+393C><U+3E32>)ë§<U+383C><U+3E63> <U+653C><U+3E64>™•<U+653C><U+3E63>¸ 2
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
lnk = soup.find_all('a') # <U+653C><U+3E63> „ì²<U+623C><U+3E34> url ê°’ì„ ì¶”ì¶œ
for i in lnk:
  print(i.attrs['href'])
{% endhighlight %}



{% highlight text %}
## http://www.google.com
## http://www.amazon.com
{% endhighlight %}


