---
layout: post
title: "[Python] Exception"
date: "2018-09-01"
excerpt: "<ed><ec>΄<ec>¬<ec><ec> <ec><ec>Έμ²λ¦¬λ₯<bc> <ed>΄λ³΄μ"
output: github_document
tag:
    [python, exception]
comments: true
categories:
  Python
---

## <ec><ec>Έ<ec>¬<ed>­ μ²λ¦¬

<ec>€<ed>μ€<91> λ°μ<ed> <ec>€λ₯μ <eb><8c><ed>΄<ec> μ²λ¦¬<ed>  <ec> <ec><eb> λ°©λ²<ec>΄<eb>€. κΈ°λ³Έ<ec> <ec>Όλ‘<9c> `try`<ec> κ³<bc> `except`<ec> λ‘<9c> λ§λ€ <ec> <ec><eb>€. `try`<ec> <ec> λ‘μ§<ec> κΈ°μ<ed>κ³<a0> <ec><ec>Έ<ec>¬<ed>­<ec> <eb><8c><ed>΄<ec><eb> `except`<ec> <ec> κ΅¬μ±<ed>λ©<b4> <eb><eb>€.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,5)
    print(z)
    
except:
    print("<U+653C><U+3E63>€λ₯κ<U+623C><U+3E30> λ°μ<U+653C><U+3E64><U+653C><U+3E63>΅<U+653C><U+3E62><U+653C><U+3E62>€.")
{% endhighlight %}



{% highlight text %}
## 2.0
{% endhighlight %}

<eb>€<ec>κ³<bc> κ°μ΄ <ec>€λ₯κ<b0> λ°μ<ed><ec> <eb><eb> `except`<ec> λ‘<9c> λΉ μ<a7>κ²<8c> <eb><eb>€.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,0)
    print(z)
    
except:
    print("<ec>€λ₯κ<b0> λ°μ<ed><ec>΅<eb><eb>€.")
{% endhighlight %}



{% highlight text %}
## Ώΐ·ω°‘ Ήί»ύΗί½ΐ΄Ο΄Ω.
{% endhighlight %}

***

### <ec>¬<eb>¬ <ec><ed>©<ec> <eb><8c><ed> <ec>€λ₯μ²λ¦<ac>

<ec><ec>Έ <ec>€λ₯μ <eb><8c><ed>΄<ec>(<ec>¬κΈ°μ<eb> <eb><eb><ec> <ed>¨<ec><ec> <eb><8c><ed>΄<ec>) κ°κ°<ec> <ec><ed>©<ec> λ§λ <ec><ec>Έμ²λ¦¬λ₯<bc> <ed>  <ec> <ec><eb>€. 


{% highlight python %}
def divide(x,y):
    return x/y
  
try:
    z = divide(10,0)
    print(z)
    
    z = divide(10,'<ec>Ό')
    print(z)
    
    
except TypeError:
    print("<ec>Έ<ec>κ°μ <ec>«<ec>λ‘<9c> <ec><eb> ₯<ed><ec>Έ<ec>")
except ZeroDivisionError:
    print("0κ°μΌλ‘<9c> <eb><eb> <ec> <ec><ec>΅<eb><eb>€.")
    
except: 
    print("<ec>€λ₯κ<b0> λ°μ<ed><ec>΅<eb><eb>€.")
else: # except<ec> <ec>΄ <eb><eb>λ©<b4> μΆλ ₯
    print("κ²°κ³Ό : {}".format(z))
finally: # <ec>€λ₯<98> λ°μ<ec>¬λΆ<ec><99> <ec>κ΄<ec><ec>΄ λ°λ<ec> μΆλ ₯
    print("<ed>λ‘κ·Έ<eb>¨ μ’λ£")
{% endhighlight %}



{% highlight text %}
## 0°ͺΐΈ·Ξ ³ͺ΄­ Όφ Ύψ½ΐ΄Ο΄Ω.
## ΗΑ·Ξ±Χ·₯ ΑΎ·α
{% endhighlight %}

#### else<ec> κ³<bc> finally<ec> 

`else`<ec> <ec><9d> `except`<ec> <ec>΄ <eb><eb>λ©<b4> λ°λ‘ μΆλ ₯<ed>΄μ£Όκ³  `finally`<ec> <ec><9d> <ec>€λ₯<98> λ°μ<ec>¬λΆ<ec><99> <ec>κ΄<ec><ec>΄ <ed>λ‘κ·Έ<eb>¨ μ’λ£ <ec> μΆλ ₯<ed>΄μ€<eb>€.

***

### <ec> <ec><a0>κ° <ec><ec>Έ<ec>¬<ed>­ λ§λ€κΈ<b0>

<ec> <ec><a0>κ° μ§μ  <ec><ec>Έ<ec>¬<ed>­<ec> λ§λ€<ec>΄ `except`<ec> λ‘<9c> <ec>΄<eb> <ec> <ec><eb>€.


{% highlight python %}
def func(arg):
    try:
        if arg < 1 or arg > 10:
            raise Exception("<ec> <ed>¨<ed>μ§ <ec><ec><9d> <ec>«<ec><ec><eb><eb>€.:{}".format(arg))
        else:
            print("<ec><eb> ₯<ed> <ec><eb> {} <ec><eb><eb>€.".format(arg))
    except Exception as error:
        print("<ec>€λ₯κ<b0> λ°μ<ed><ec>΅<eb><eb>€.{}".format(error))
func(10)
{% endhighlight %}



{% highlight text %}
## ΐΤ·ΒΗΡ Όφ΄Β 10 ΐΤ΄Ο΄Ω.
{% endhighlight %}

<ec>¬κΈ°μ `as error`<eb> <ec>€λ₯<98> λ©μμ§λ₯<bc> μΆλ ₯<ed>  <ec> <ec>κ²<8c> <ed><eb>€. `SQL`<ec><ec> `sqlerrm`κ³<bc> κ°μ<9d> <ec>λ―Έμ΄<eb>€. μ’ <eb> <ec><ec>Έ<ed> <eb>΄<ec>©<ec><9d> <ec><eb>λ₯<bc> μ°Έκ³ <ed><ec>.

***

### <ec>€λ₯<98> λ©μμ§<ec><99> <ed>¨κ»<98> μΆλ ₯(as ~)


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except:
    print("<ec>€λ₯κ<b0> λ°μ<ed><ec>΅<eb><eb>€")
{% endhighlight %}



{% highlight text %}
## Ώΐ·ω°‘ Ήί»ύΗί½ΐ΄Ο΄Ω
{% endhighlight %}

λ¦¬μ€<ed>Έλ³<ec> `lst`<eb> index λ²νΈκ° 2λ²κΉμ§ λ°°μ <eb><ec>΄ <ec><ec>΄<ec> <ec>€λ₯κ<b0> <eb><eb>€. <ed>μ§λ§<8c> <ec>΄<eb>€ <ec>€λ₯κ<b0> λ°μ<ed><eb>μ§ μΆλ ₯<ed>μ§ λͺ»ν<eb>€.


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except Exception as error: # <ec>€<eb>Ό<ed>΄<ec><ec><ec> sqlerrmκ³<bc> κ°μ<9d> <ec>λ―<b8>
    print(error)
    print("<ec>€λ₯κ<b0> λ°μ<ed><ec>΅<eb><eb>€")
{% endhighlight %}



{% highlight text %}
## list index out of range
## Ώΐ·ω°‘ Ήί»ύΗί½ΐ΄Ο΄Ω
{% endhighlight %}

<ec><ec><99> κ°μ΄ `as error`λ₯<bc> <ec>¬<ec>©<ed><ec>¬ <ec>΄<eb>€ <ec>€λ₯κ<b0> λ°μ<ed>μ§κΉμ<a7> μΆλ ₯<ed>  <ec> <ec><eb>€.
