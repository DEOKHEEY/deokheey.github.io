---
layout: post
title: "[Python] Exception"
date: "2018-09-01"
excerpt: "<ed>��<ec>��<ec>��<ec>��<ec>�� <ec>��<ec>��처리�<bc> <ed>��보자"
output: github_document
tag:
    [python, exception]
comments: true
categories:
  Python
---

## <ec>��<ec>��<ec>��<ed>�� 처리

<ec>��<ed>���<91> 발생<ed>�� <ec>��류에 <eb><8c>�<ed>��<ec>�� 처리<ed>�� <ec>�� <ec>��<eb>�� 방법<ec>��<eb>��. 기본<ec>��<ec>���<9c> `try`<ec>���<bc> `except`<ec>���<9c> 만들 <ec>�� <ec>��<eb>��. `try`<ec>��<ec>�� 로직<ec>�� 기입<ed>���<a0> <ec>��<ec>��<ec>��<ed>��<ec>�� <eb><8c>�<ed>��<ec>��<eb>�� `except`<ec>��<ec>�� 구성<ed>���<b4> <eb>��<eb>��.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,5)
    print(z)
    
except:
    print("<U+653C><U+3E63>��류�<U+623C><U+3E30>� 발생<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>��.")
{% endhighlight %}



{% highlight text %}
## 2.0
{% endhighlight %}

<eb>��<ec>���<bc> 같이 <ec>��류�<b0>� 발생<ed>��<ec>�� <eb>��<eb>�� `except`<ec>���<9c> 빠�<a7>��<8c> <eb>��<eb>��.


{% highlight python %}
def divide(x,y):
    return x/y
    
try:
    z = divide(10,0)
    print(z)
    
except:
    print("<ec>��류�<b0>� 발생<ed>��<ec>��<eb>��<eb>��.")
{% endhighlight %}



{% highlight text %}
## ������ �߻��߽��ϴ�.
{% endhighlight %}

***

### <ec>��<eb>�� <ec>��<ed>��<ec>�� <eb><8c>�<ed>�� <ec>��류처�<ac>

<ec>��<ec>�� <ec>��류에 <eb><8c>�<ed>��<ec>��(<ec>��기서<eb>�� <eb>��<eb>��<ec>�� <ed>��<ec>��<ec>�� <eb><8c>�<ed>��<ec>��) 각각<ec>�� <ec>��<ed>��<ec>�� 맞는 <ec>��<ec>��처리�<bc> <ed>�� <ec>�� <ec>��<eb>��. 


{% highlight python %}
def divide(x,y):
    return x/y
  
try:
    z = divide(10,0)
    print(z)
    
    z = divide(10,'<ec>��')
    print(z)
    
    
except TypeError:
    print("<ec>��<ec>��값을 <ec>��<ec>���<9c> <ec>��<eb>��<ed>��<ec>��<ec>��")
except ZeroDivisionError:
    print("0값으�<9c> <eb>��<eb>�� <ec>�� <ec>��<ec>��<eb>��<eb>��.")
    
except: 
    print("<ec>��류�<b0>� 발생<ed>��<ec>��<eb>��<eb>��.")
else: # except<ec>��<ec>�� <eb>��<eb>���<b4> 출력
    print("결과 : {}".format(z))
finally: # <ec>���<98> 발생<ec>��부<ec><99>� <ec>��관<ec>��<ec>�� 반드<ec>�� 출력
    print("<ed>��로그<eb>�� 종료")
{% endhighlight %}



{% highlight text %}
## 0������ ���� �� �����ϴ�.
## ���α׷� ����
{% endhighlight %}

#### else<ec>���<bc> finally<ec>��

`else`<ec>��<ec><9d>� `except`<ec>��<ec>�� <eb>��<eb>���<b4> 바로 출력<ed>��주고 `finally`<ec>��<ec><9d>� <ec>���<98> 발생<ec>��부<ec><99>� <ec>��관<ec>��<ec>�� <ed>��로그<eb>�� 종료 <ec>�� 출력<ed>��준<eb>��.

***

### <ec>��<ec><a0>�가 <ec>��<ec>��<ec>��<ed>�� 만들�<b0>

<ec>��<ec><a0>�가 직접 <ec>��<ec>��<ec>��<ed>��<ec>�� 만들<ec>�� `except`<ec>���<9c> <ec>��<eb>�� <ec>�� <ec>��<eb>��.


{% highlight python %}
def func(arg):
    try:
        if arg < 1 or arg > 10:
            raise Exception("<ec>��<ed>��<ed>��지 <ec>��<ec><9d>� <ec>��<ec>��<ec>��<eb>��<eb>��.:{}".format(arg))
        else:
            print("<ec>��<eb>��<ed>�� <ec>��<eb>�� {} <ec>��<eb>��<eb>��.".format(arg))
    except Exception as error:
        print("<ec>��류�<b0>� 발생<ed>��<ec>��<eb>��<eb>��.{}".format(error))
func(10)
{% endhighlight %}



{% highlight text %}
## �Է��� ���� 10 �Դϴ�.
{% endhighlight %}

<ec>��기서 `as error`<eb>�� <ec>���<98> 메시지�<bc> 출력<ed>�� <ec>�� <ec>���<8c> <ed>��<eb>��. `SQL`<ec>��<ec>�� `sqlerrm`�<bc> 같�<9d>� <ec>��미이<eb>��. 좀 <eb>�� <ec>��<ec>��<ed>�� <eb>��<ec>��<ec><9d>� <ec>��<eb>���<bc> 참고<ed>��<ec>��.

***

### <ec>���<98> 메시지<ec><99>� <ed>���<98> 출력(as ~)


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except:
    print("<ec>��류�<b0>� 발생<ed>��<ec>��<eb>��<eb>��")
{% endhighlight %}



{% highlight text %}
## ������ �߻��߽��ϴ�
{% endhighlight %}

리스<ed>��변<ec>�� `lst`<eb>�� index 번호가 2번까지 배정<eb>��<ec>�� <ec>��<ec>��<ec>�� <ec>��류�<b0>� <eb>��<eb>��. <ed>��지�<8c> <ec>��<eb>�� <ec>��류�<b0>� 발생<ed>��<eb>��지 출력<ed>��지 못한<eb>��.


{% highlight python %}
lst = [1,2,3]
try:
    print(lst[3])
except Exception as error: # <ec>��<eb>��<ed>��<ec>��<ec>��<ec>�� sqlerrm�<bc> 같�<9d>� <ec>���<b8>
    print(error)
    print("<ec>��류�<b0>� 발생<ed>��<ec>��<eb>��<eb>��")
{% endhighlight %}



{% highlight text %}
## list index out of range
## ������ �߻��߽��ϴ�
{% endhighlight %}

<ec>��<ec><99>� 같이 `as error`�<bc> <ec>��<ec>��<ed>��<ec>�� <ec>��<eb>�� <ec>��류�<b0>� 발생<ed>��지까�<a7>� 출력<ed>�� <ec>�� <ec>��<eb>��.
