---
layout: post
title: "[Python] BeautifulSoup"
date: "2018-10-01"
excerpt: "<ec>�� <ed>��롤링<ec>�� <ed>��보자"
output: github_document
tag:
    [python, beautifulsoup]
comments: true
categories:
  Python
---




## BeautifulSoup

`BeautifulSoup`<eb>�� <ec>��<ec>�� <ec>��<eb>�� <eb>��<ec>��<ed>���<bc> <ed>��롤링 <ed>��<ec><9d>� <ec>��<ed>��<eb>��<ed>��<ed>�� <eb>�� <ec>��<ec>��<ed>��<eb>�� <eb>��<ec>��브러리이<eb>��. <ec>��<ec>��법을 <ec>��<ec>��보기 <ec>��<ec>�� <eb>��<ec>��브러리�<b0>� <ec>��치되<ec>��<ec>��지 <ec>��<eb>���<b4> <ec>��치�<b6>�<ed>�� <ed>��주자.

```
# Anaconda Prompt<ec>�� <eb>��<ec>��<ec>�� <ec>��<ed>��<ec>��켜�<a4>�<eb>��.
$ pip install beautifulsoup4
```

***

### tag�<9c> 추출<ed>���<b0>

 <ec>��치�<b0>� <eb>��<ec>��<eb>���<b4> <ec>��<ec>��법에 <eb><8c>�<ed>�� <ec>��<ec>��보자.


{% highlight python %}
from bs4 import BeautifulSoup
# html <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��
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
soup = BeautifulSoup(html,"html.parser") # html.parser<U+653C><U+3E62>��<U+653C><U+3E62>�� 분석기���<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��
# <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63><U+393C><U+3E64>� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>�� <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>���<U+623C><U+3E63> 바로 <U+653C><U+3E62>��고오지 못하���<U+3E30> html<U+653C><U+3E63>�� <U+653C><U+3E62>��고�<U+393C><U+3E39>�<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>��.
#
# <U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>�� <U+653C><U+3E64>���<U+623C><U+3E38> <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63>�� 가<U+653C><U+3E63>��<U+653C><U+3E63>���<U+623C><U+3E30> 
## h1 <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>�� 추출
h1 = soup.html.body.h1 # html -> body -> h1
print(h1.string) # 문자<U+653C><U+3E63>���<U+383C><U+3E63> <U+653C><U+3E62>��고오�<U+623C><U+3E30>
## p <U+653C><U+3E64>���<U+623C><U+3E38> <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E64>�� 추출
{% endhighlight %}



{% highlight text %}
##  Data Science
{% endhighlight %}



{% highlight python %}
p1 = soup.html.body.p 
print(p1.string) # p tag가 3�<U+393C><U+3E63> <U+653C><U+3E63>��지�<U+383C><U+3E63> 첫번�<U+623C><U+3E38> 것만 추출<U+653C><U+3E62>��
## 2번째 p tag 추출
{% endhighlight %}



{% highlight text %}
##  data analysis 1
{% endhighlight %}



{% highlight python %}
p2 = p1.next_sibling.next_sibling # next_sibling�<U+383C><U+3E63> 추출<U+653C><U+3E64>���<U+623C><U+3E34> /n<U+653C><U+3E63>�� 추출<U+653C><U+3E62>��므�<U+393C><U+3E63> 2�<U+383C><U+3E38> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E62>��.
print(p2.string)
# 3번째 p tag 추출
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

### <ec>��<ec>��값으�<9c> 추출<ed>���<b0>

`html`<ec>��<eb>�� id, class <eb>��<ec>�� <ec>��<eb>�� <ec>��<ec>��<ec>�� 가지�<a0> <ec>��<eb>��. <ec>��<ec>��<ec>���<9c> <eb>��<ec>��<ed>���<bc> 추출<ed>���<b4> <eb>�� <ed>��그로 추출<ed>��<eb>�� �<83> 보다 <eb>�� <ed>��리할 <ec>�� <ec>��<eb>��. 그럼 <ec>��<ec>��값으�<9c> <ec>��<eb>��<ec>��<ed>���<bc> 추출<ed>��보자.


{% highlight python %}
from bs4 import BeautifulSoup
html = """
        <html>
            <body>
                <h1 id = 'title'> beautifulsoup </h1>
                <p id = 'subtitle'> web scraping </p>
                <p> web data extraction�<U+623C><U+3E30> </p>
            </body>
        </html>
       """
soup = BeautifulSoup(html,'html.parser')
# .find() <U+653C><U+3E63>��<U+653C><U+3E63>��
## title 추출
title = soup.find(id = 'title')
print(title.string)
{% endhighlight %}



{% highlight text %}
##  beautifulsoup
{% endhighlight %}



{% highlight python %}
sub = soup.find(id = 'subtitle').string ## subtitle 추출
print(sub)
{% endhighlight %}



{% highlight text %}
##  web scraping
{% endhighlight %}

<eb>���<b8> <ec>��<ec>��<ec>�� 가�<84> `html` <ec>��<ec>���<bc> 만들<ec>�� 값을 추출<ed>��보자.


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
# tag�<U+393C><U+3E63> 찾기
a_tag = soup.html.body.ul.li.a
print(a_tag.string) # 1번째 anchor tag가 추출<U+653C><U+3E62>��
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find('a').string) # find<U+653C><U+3E62>�� 마찬가지 첫번째만 찾아주고 2번째 a�<U+623C><U+3E63> 찾���<U+3E37>� 못한<U+653C><U+3E62>��
{% endhighlight %}



{% highlight text %}
##  Google
{% endhighlight %}



{% highlight python %}
print(soup.find_all('a')) # .find_aLl() <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� 모든 achor tag 추출
{% endhighlight %}



{% highlight text %}
## [<a href="http://www.google.com"> Google </a>, <a href="http://www.amazon.com"> Amazon </a>]
{% endhighlight %}



{% highlight python %}
for i in soup.find_all('a'): # 루프 구조�<U+393C><U+3E63> string�<U+383C><U+3E63> 추출<U+653C><U+3E64>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
  print(i.string)
{% endhighlight %}



{% highlight text %}
##  Google 
##  Amazon
{% endhighlight %}

<ec>��<ec>�� <ec>��<ec>��<ec>��<ec>�� url 주소�<8c> 추출<ed>��보자


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
# a tag 추출(첫번째만 추출<U+653C><U+3E62>��<U+653C><U+3E62>��)
a = soup.a
print('href' in a.attrs) # a tag<U+653C><U+3E63>�� href <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��지 <U+653C><U+3E64>��<U+653C><U+3E63>��
{% endhighlight %}



{% highlight text %}
## True
{% endhighlight %}



{% highlight python %}
print(a.attrs) # a tag<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>���<U+393C><U+3E32> <U+653C><U+3E64>��<U+653C><U+3E63>��
{% endhighlight %}



{% highlight text %}
## {'href': 'http://www.google.com'}
{% endhighlight %}



{% highlight python %}
print(a['href']) # value(url �<U+393C><U+3E32>)�<U+383C><U+3E63> <U+653C><U+3E64>��<U+653C><U+3E63>�� 1
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
print(a.attrs['href']) # value(url �<U+393C><U+3E32>)�<U+383C><U+3E63> <U+653C><U+3E64>��<U+653C><U+3E63>�� 2
{% endhighlight %}



{% highlight text %}
## http://www.google.com
{% endhighlight %}



{% highlight python %}
lnk = soup.find_all('a') # <U+653C><U+3E63>���<U+623C><U+3E34> url 값을 추출
for i in lnk:
  print(i.attrs['href'])
{% endhighlight %}



{% highlight text %}
## http://www.google.com
## http://www.amazon.com
{% endhighlight %}


