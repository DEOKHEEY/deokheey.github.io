---
layout: post
title: "[Python] <ec> <ec>­λ³<ec><ec><99> μ§<ec>­λ³<ec>"
date: "2018-09-01"
excerpt: "<ed><ec>΄<ec>¬<ec> <ec> <ec>­λ³<ec>, μ§<ec>­λ³<ec>λ₯<bc> <ed> <eb>Ή<ed><eb> λ°©λ²"
output: github_document
tag:
    [python, variable]
comments: true
categories:
  Python
---

## <ec> <ec>­λ³<ec>/μ§<ec>­λ³<ec>

-<ec> <ec>­λ³<ec>(global): <ed>λ‘κ·Έ<eb>¨<ec>΄ μ’λ£<eb> <eb>κΉμ<a7> <ec>΄<eb><ec><eb> μ§ <ec>¬<ec>©<ed>  <ec> <ec><eb> λ³<ec>
-μ§<ec>­λ³<ec>(local): <ed>¨<ec> <ec><ec><ec>λ§<8c> <ec>¬<ec>©<ed><eb> λ³<ec>

<br>

<ec><eb>λ₯<bc> λ³΄κ³  μ§<ec>­λ³<ec><ec><99> <ec> <ec>­λ³<ec>λ₯<bc> <ec>΄<ed>΄<ed>΄λ³΄μ.


{% highlight python %}
x = 10 # global λ³<U+653C><U+3E63>
def f(x): # parameter(λ§€κ°λ³<U+653C><U+3E63>)
    print("x = ", x)
    x = 20 # local λ³<U+653C><U+3E63>
    print("x = ", x)
f(x) # <U+653C><U+3E63>°<U+653C><U+3E63>  <U+653C><U+3E63> <U+653C><U+3E63>­λ³<U+653C><U+3E63> 10<U+653C><U+3E63>΄ <U+653C><U+3E62>€<U+653C><U+3E63>΄κ°κ³γε<U+3E30> μ§<U+653C><U+3E63>­λ³<U+653C><U+3E63><U+653C><U+3E63> 10<U+653C><U+3E63>΄ <U+653C><U+3E63>΄<U+653C><U+3E64><U+653C><U+3E63> μΆλ ₯<U+653C><U+3E62><U+653C><U+3E62>€.
{% endhighlight %}



{% highlight text %}
## x =  10
## x =  20
{% endhighlight %}



{% highlight python %}
print(x) # <U+653C><U+3E63> <U+653C><U+3E63>­λ³<U+653C><U+3E63> μΆλ ₯
{% endhighlight %}



{% highlight text %}
## 10
{% endhighlight %}

<br>

<ec> <ec>­λ³<ec> <ec> <ec>Έ<ec><9d> `global`<ec> <ec>¬<ec>©<ed><ec>¬ <ec> <ec>Έ<ed><eb>€.


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
print(x) # <U+653C><U+3E64>¨<U+653C><U+3E63> <U+653C><U+3E62>΄<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63>Έ<U+653C><U+3E62> x<U+653C><U+3E62> <U+653C><U+3E63> <U+653C><U+3E63>­λ³<U+653C><U+3E63><U+653C><U+3E62>Ό<U+653C><U+3E62> κ²μ <U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63>
{% endhighlight %}



{% highlight text %}
## 20
{% endhighlight %}
