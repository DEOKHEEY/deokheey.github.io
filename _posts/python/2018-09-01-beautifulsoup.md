---
layout: post
title: "[Python] BeautifulSoup"
date: "2018-10-01"
excerpt: "<ec>Ή <ed>¬λ‘€λ§<ec> <ed>΄λ³΄μ"
output: github_document
tag:
    [python, beautifulsoup]
comments: true
categories:
  Python
---




## BeautifulSoup

`BeautifulSoup`<eb> <ec>Ή<ec> <ec><eb> <eb>°<ec>΄<ed>°λ₯<bc> <ed>¬λ‘€λ§ <ed>Ή<ec><9d> <ec>€<ed>¬<eb>©<ed><ed>  <eb> <ec>¬<ec>©<ed><eb> <eb>Ό<ec>΄λΈλ¬λ¦¬μ΄<eb>€. <ec>¬<ec>©λ²μ <ec><ec>λ³΄κΈ° <ec><ec> <eb>Ό<ec>΄λΈλ¬λ¦¬κ<b0> <ec>€μΉλ<ec>΄<ec>μ§ <ec><eb>€λ©<b4> <ec>€μΉλ<b6><ed>° <ed>΄μ£Όμ.

```
# Anaconda Prompt<ec> <eb>€<ec><ec> <ec>€<ed><ec>μΌμ<a4><eb>€.
$ pip install beautifulsoup4
```

***

### tagλ‘<9c> μΆμΆ<ed>κΈ<b0>

 <ec>€μΉκ<b0> <eb><ec><eb>€λ©<b4> <ec>¬<ec>©λ²μ <eb><8c><ed>΄ <ec><ec>λ³΄μ.


{% highlight python %}
from bs4 import BeautifulSoup
# html <U+653C><U+3E63><U+653C><U+3E63>  <U+653C><U+3E63><U+653C><U+3E63>±
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
soup = BeautifulSoup(html,"html.parser") # html.parser<U+653C><U+3E62>Ό<U+653C><U+3E62> λΆμκΈ°λγε<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>¬<U+653C><U+3E63>©
# <U+653C><U+3E62>¨<U+653C><U+3E63> <U+653C><U+3E63><U+393C><U+3E64> <U+653C><U+3E63>Ή<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E64><U+653C><U+3E62> <U+653C><U+3E62>°<U+653C><U+3E63>΄<U+653C><U+3E64>°λ₯<U+623C><U+3E63> λ°λ‘ <U+653C><U+3E62>κ³ μ€μ§ λͺ»νκ³γε<U+3E30> html<U+653C><U+3E63> <U+653C><U+3E62>€κ³ μ<U+393C><U+3E39><U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E64>΄<U+653C><U+3E63>Ό<U+653C><U+3E64><U+653C><U+3E62>€.
#
# <U+653C><U+3E63><U+653C><U+3E64><U+653C><U+3E62> <U+653C><U+3E64>κ·<U+623C><U+3E38> <U+653C><U+3E62>΄<U+653C><U+3E63>©<U+653C><U+3E63> κ°<U+653C><U+3E63> Έ<U+653C><U+3E63>€κΈ<U+623C><U+3E30> 
## h1 <U+653C><U+3E62>°<U+653C><U+3E63>΄<U+653C><U+3E64>° μΆμΆ
h1 = soup.html.body.h1 # html -> body -> h1
print(h1.string) # λ¬Έμ<U+653C><U+3E63>΄λ§<U+383C><U+3E63> <U+653C><U+3E62>€κ³ μ€κΈ<U+623C><U+3E30>
## p <U+653C><U+3E64>κ·<U+623C><U+3E38> <U+653C><U+3E62>°<U+653C><U+3E63>΄<U+653C><U+3E64>° μΆμΆ
{% endhighlight %}



{% highlight text %}
##  Data Science
{% endhighlight %}



{% highlight python %}
p1 = soup.html.body.p 
print(p1.string) # p tagκ° 3κ°<U+393C><U+3E63> <U+653C><U+3E63>μ§λ§<U+383C><U+3E63> μ²«λ²μ§<U+623C><U+3E38> κ²λ§ μΆμΆ<U+653C><U+3E62>
## 2λ²μ§Έ p tag μΆμΆ
{% endhighlight %}



{% highlight text %}
##  data analysis 1
{% endhighlight %}



{% highlight python %}
p2 = p1.next_sibling.next_sibling # next_siblingλ§<U+383C><U+3E63> μΆμΆ<U+653C><U+3E64>λ©<U+623C><U+3E34> /n<U+653C><U+3E63>΄ μΆμΆ<U+653C><U+3E62>λ―λ‘<U+393C><U+3E63> 2λ²<U+383C><U+3E38> <U+653C><U+3E63>¬<U+653C><U+3E63>©<U+653C><U+3E64><U+653C><U+3E62>€.
print(p2.string)
# 3λ²μ§Έ p tag μΆμΆ
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

### <ec><ec>±κ°μΌλ‘<9c> μΆμΆ<ed>κΈ<b0>

`html`<ec><eb> id, class <eb>±<ec> <ec>¬<eb>¬ <ec><ec>±<ec> κ°μ§κ³<a0> <ec><eb>€. <ec><ec>±<ec>Όλ‘<9c> <eb>°<ec>΄<ed>°λ₯<bc> μΆμΆ<ed>λ©<b4> <eb> <ed>κ·Έλ‘ μΆμΆ<ed><eb> κ²<83> λ³΄λ€ <eb> <ed>Έλ¦¬ν  <ec> <ec><eb>€. κ·ΈλΌ <ec><ec>±κ°μΌλ‘<9c> <ec>Ή<eb>°<ec>΄<ed>°λ₯<bc> μΆμΆ<ed>΄λ³΄μ.


{% highlight python %}
from bs4 import BeautifulSoup
html = """
        <html>
            <body>
                <h1 id = 'title'> beautifulsoup </h1>
                <p id = 'subtitle'> web scraping </p>
                <p> web data extractionκΈ<U+623C><U+3E30> </p>
            </body>
        </html>
       """
soup = BeautifulSoup(html,'html.parser')
# .find() <U+653C><U+3E63>¬<U+653C><U+3E63>©
## title μΆμΆ
title = soup.find(id = 'title')
print(title.string)
{% endhighlight %}



{% highlight text %}
##  beautifulsoup
{% endhighlight %}



{% highlight python %}
sub = soup.find(id = 'subtitle').string ## subtitle μΆμΆ
print(sub)
{% endhighlight %}



{% highlight text %}
##  web scraping
{% endhighlight %}

<eb>€λ₯<b8> <ec><ec>±<ec> κ°μ§<84> `html` <ec><ec> λ₯<bc> λ§λ€<ec>΄ κ°μ μΆμΆ<ed>΄λ³΄μ.


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
# tagλ‘<U+393C><U+3E63> μ°ΎκΈ°
a_tag = soup.html.body.ul.li.a
print(a_tag.string) # 1λ²μ§Έ anchor tagκ° μΆμΆ<U+653C><U+3E62>
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find('a').string) # find<U+653C><U+3E62> λ§μ°¬κ°μ§ μ²«λ²μ§Έλ§ μ°Ύμμ£Όκ³  2λ²μ§Έ aλ₯<U+623C><U+3E63> μ°Ύμγε<U+3E37> λͺ»ν<U+653C><U+3E62>€
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find_all('a')) # .find_aLl() <U+653C><U+3E63> <U+653C><U+3E63>¬<U+653C><U+3E63>©<U+653C><U+3E64><U+653C><U+3E63>¬ λͺ¨λ  achor tag μΆμΆ
{% endhighlight %}



{% highlight text %}
## [<a href="http://www.google.com"> Google </a>, <a href="http://www.amazon.com"> Amazon </a>]
{% endhighlight %}



{% highlight python %}
for i in soup.find_all('a'): # λ£¨ν κ΅¬μ‘°λ‘<U+393C><U+3E63> stringλ§<U+383C><U+3E63> μΆμΆ<U+653C><U+3E64>  <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E62>€.
  print(i.string)
{% endhighlight %}



{% highlight text %}
##  Google 
##  Amazon
{% endhighlight %}

<ec><ec> <ec><ec> <ec><ec> url μ£Όμλ§<8c> μΆμΆ<ed>΄λ³΄μ


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
# a tag μΆμΆ(μ²«λ²μ§Έλ§ μΆμΆ<U+653C><U+3E62><U+653C><U+3E62>€)
a = soup.a
print('href' in a.attrs) # a tag<U+653C><U+3E63> href <U+653C><U+3E63><U+653C><U+3E63>±<U+653C><U+3E63>΄ <U+653C><U+3E63><U+653C><U+3E62>μ§ <U+653C><U+3E64><U+653C><U+3E63>Έ
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(a.attrs) # a tag<U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63>±κ°<U+393C><U+3E32> <U+653C><U+3E64><U+653C><U+3E63>Έ
{% endhighlight %}



{% highlight text %}
## {'href': 'http://www.google.com'}
{% endhighlight %}



{% highlight python %}
print(a['href']) # value(url κ°<U+393C><U+3E32>)λ§<U+383C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63>Έ 1
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
print(a.attrs['href']) # value(url κ°<U+393C><U+3E32>)λ§<U+383C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63>Έ 2
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
lnk = soup.find_all('a') # <U+653C><U+3E63> μ²<U+623C><U+3E34> url κ°μ μΆμΆ
for i in lnk:
  print(i.attrs['href'])
{% endhighlight %}



{% highlight text %}
## http://www.google.com
## http://www.amazon.com
{% endhighlight %}


