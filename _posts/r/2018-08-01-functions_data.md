---
layout: post
title: "[R] Function"
date: "2018-07-01"
excerpt: "R<ec>��<ec>��<ec>�� <ed>��<ec>��"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## 문자<ed>��<ec>��

### grep(): 문자<ec>�� <ed>��<ed>�� 검<ec>�� <ed>��<ec>��

문자 <ed>��<ed>��<ec>�� 찾을 <eb>�� <ec>��<ec>��<eb>��<eb>�� <ed>��<ec>��<ec>��<eb>��. <eb>��<ec>�� <ed>��<ec>��문자<ec><99>� option<ec>�� <ec>��<ec>��<ed>�� <ec>�� <ec>��<eb>��.

    ^ : 첫번�<b8> 
    $ : 마�<a7>��<89>
    . : <ed>��<ec>�� <ec>��리수
    * : wild card

`ignore.case`
- `ignore.case = TRUE`: <eb><8c>�<ec>��문자 구분<ec>��<ed>��<eb>��.  
- `ignore.case = FALSE`: <eb><8c>�<ec>��문자 구분<ed>��<eb>��.


{% highlight r %}
setwd("C:/data")
emp <- read.csv('emp.csv',stringsAsFactors = F)

emp[grep("aa", emp$LAST_NAME),c("LAST_NAME","SALARY")]
{% endhighlight %}



{% highlight text %}
##    LAST_NAME SALARY
## 12   De Haan  17000
{% endhighlight %}



{% highlight r %}
emp[grep("[x-z]", emp$LAST_NAME, ignore.case = TRUE),c("LAST_NAME","SALARY")]
{% endhighlight %}



{% highlight text %}
##     LAST_NAME SALARY
## 5         Fay   6000
## 9       Gietz   8300
## 17    Lorentz   4200
## 24   Raphaely  11000
## 35      Nayer   3200
## 37     Landry   2400
## 57  Errazuriz  12000
## 59    Zlotkey  10500
## 67      Sully   9500
## 72    Vishney  10500
## 78       Ozer  11500
## 80        Fox   9600
## 86     Taylor   8600
## 90     Taylor   3200
## 99      Dilly   3600
## 107    Feeney   3000
{% endhighlight %}

***

### nchar(): 문자 <ec>���<bc> return<ed>��<eb>�� <ed>��<ec>��

공백까�<a7>� <ed>��<ed>��<ed>�� 문자<ec>�� <ec>���<bc> return<ed>��준<eb>��. option<ec>���<9c> `type`<ec>�� <ec>��<ec>��<ed>��<ec>�� �<b8> <ed><83>�<ec>��<ec>�� 맞게 <ec>��<ec>�� �<84> <ec>�� <ec>��<eb>��.


{% highlight r %}
nchar('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# char�<U+393C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E62>��
nchar('R Developer', type = "chars")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# byte값으�<U+393C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E62>��.
nchar('R Developer', type = "bytes")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}

***

### strsplit(): 부분문<ec>���<9c> 분리<ed>��<eb>�� <ed>��<ec>��

문자�<bc> 분리<ed>��준<eb>��. <ec>�� <ed>��<ec>��<eb>�� `split`<ec>��<eb>��<eb>�� option<ec>�� 반드<ec>�� <ec>��<ec>��<ed>��<ec>�� <ed>��<eb>��. <ec>��<eb>��<ed>�� 글<ec>��가 <ec>���<bc> <eb>��<ec>��<ed>��<eb>��지 <ed>��<ec>��<ed>�� <eb>�� <eb>��<ec><9b>�<ec>�� <eb>��<eb>��.


{% highlight r %}
# split<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>�� option<U+653C><U+3E63>�� 반드<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E62>��.
# <U+653C><U+3E64>��글<U+653C><U+3E63>��<U+653C><U+3E63>�� 분리(character<U+653C><U+3E63>��<U+653C><U+3E63>�� 값을 바꾸<U+653C><U+3E63>��<U+653C><U+3E62>�� 결과<U+653C><U+3E62>�� 같음)
strsplit('R Developer',split = character(0))
{% endhighlight %}



{% highlight text %}
## [[1]]
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}



{% highlight r %}
# 공백<U+653C><U+3E63>�� 기���<U+3E34>�<U+653C><U+3E63>���<U+393C><U+3E63> 분리
strsplit('R Developer',split =" ")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}



{% highlight r %}
# ,�<U+623C><U+3E63> 기���<U+3E34>�<U+653C><U+3E63>���<U+393C><U+3E63> 분리
strsplit('R,Developer',split =",")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}

결과<eb>�� list type<ec>���<9c> 출력<eb>��<ec>�� <ec>�� <ec>�� <ec>��<eb>��. <ec>��<eb>�� <ed>��<ec>���<bc> 참고<ed>��<ec>��.

### unlist(): list<ed>��<ec>�� vector<ed>��<ec>���<9c> 변<ed>�� <ed>��<ec>��

<ec>��<ec>�� <ec>��<ec>��<ec>��, 만약 Vector type<ec>���<9c> 바꾸�<a0> <ec>��<eb>���<b4> `unlist(strsplit())`<ec>�� <ec>��<ec>��<ed>���<b4> <ed>���<b4> <eb>��<eb>��.


{% highlight r %}
unlist(strsplit('R Developer',split = character(0)))
{% endhighlight %}



{% highlight text %}
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}

***

### toupper()/tolower(): <eb><8c>�<ec>��문자 변<ed>��<ed>��<eb>�� <ed>��<ec>��

<ec>��<ed>��벳을 <eb><8c>�<ec>��문자�<9c> 변<ed>��<ed>��<eb>�� <ed>��<ec>��<ec>��<eb>��.


{% highlight r %}
# <U+653C><U+3E62><U+383C><U+3E63>�문자�<U+393C><U+3E63> 변<U+653C><U+3E64>��
toupper('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "R DEVELOPER"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��문자�<U+393C><U+3E63> 변<U+653C><U+3E64>��
tolower('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "r developer"
{% endhighlight %}

***

### substr(): 문자<ec>�� 추출 <ed>��<ec>��

`substr(' ',<ec>��<ec>��<ec>��,<eb>��<ec>��)`<ec>��<eb>��. sql<ec>��<ec>��<ec><99>� `substr()`<ec><99>� <eb>��름을 주의<ed>��<ec>��.


{% highlight r %}
# 첫번째�<U+623C><U+3E36>�<U+653C><U+3E64>�� 첫번째까지 추출
substr('R Developer',1,1)
{% endhighlight %}



{% highlight text %}
## [1] "R"
{% endhighlight %}



{% highlight r %}
# 첫번째�<U+623C><U+3E36>�<U+653C><U+3E64>�� <U+653C><U+3E63>��번째까���<U+3E37>� 추출
substr('R Developer',1,3)
{% endhighlight %}



{% highlight text %}
## [1] "R D"
{% endhighlight %}



{% highlight r %}
# 5번째부<U+653C><U+3E64>�� 11번째 추출
substr('R Developer',5,11)
{% endhighlight %}



{% highlight text %}
## [1] "veloper"
{% endhighlight %}

***

### sub(): 첫번�<b8> <ec>��치하<eb>�� 문자�<8c> 바꾸<eb>�� <ed>��<ec>��

`sub('찾아<ec>�� <ed>�� 글<ec>��','바꿔<ec>�� <ed>�� 글<ec>��','<ed>��<eb>�� <eb>��<ec>��<ed>��')`�<9c> <ec>��<ec>��<ed>��<eb>��. <ed>��지�<8c> 찾아<ec>�� <ed>�� 글<ec>��가 많다�<b4> 첫번째로 <ec>��치하<eb>�� 글<ec>���<8c> 바꿔<ec>�� <ed>�� 글<ec>���<9c> 바꾸<ec>��준<eb>��.


{% highlight r %}
# 3번째<U+653C><U+3E63>�� 값에<U+653C><U+3E63>�� R<U+653C><U+3E63>�� Python<U+653C><U+3E63>���<U+393C><U+3E63> 바꾸<U+653C><U+3E62>��<U+653C><U+3E62>�� 첫번째로 찾는 R<U+653C><U+3E63>�� 바꾼<U+653C><U+3E62>��.
sub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer R Developer"
{% endhighlight %}

***

### gsub(): <ec>��치하<eb>�� 문자�<bc> 모두 바꾸<eb>�� <ed>��<ec>��

`gsub('찾아<ec>�� <ed>�� 글<ec>��','바꿔<ec>�� <ed>�� 글<ec>��','<ed>��<eb>�� <eb>��<ec>��<ed>��')`�<9c> <ec>��<ec>��<ed>��<eb>��. `sub()`�<bc> <eb>��르게 <ec>��치하<eb>�� 문자�<bc> 모두 바꾸<ec>��준<eb>��.


{% highlight r %}
# 3번째<U+653C><U+3E63>�� 값에<U+653C><U+3E63>�� R<U+653C><U+3E63>�� <U+653C><U+3E63>��치하<U+653C><U+3E62>�� 문자�<U+623C><U+3E63> <U+653C><U+3E63>��부  Python<U+653C><U+3E63>���<U+393C><U+3E63> 바꾸<U+653C><U+3E63>��준<U+653C><U+3E62>��.
gsub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer Python Developer"
{% endhighlight %}



{% highlight r %}
# 0부<U+653C><U+3E64>�� 2<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>���<U+623C><U+3E63> *�<U+393C><U+3E63> 바꾸<U+653C><U+3E63>��준<U+653C><U+3E62>��.
gsub('[0-2]','*','123450')
{% endhighlight %}



{% highlight text %}
## [1] "**345*"
{% endhighlight %}


***

## <ec>��<ec>��<ed>��<ec>��

### round(): 반올�<bc> <ed>��<ec>��

option<ec>�� <ec>��<ec>��<ed>��<ec>�� 반올림할 <ec>��치�<a5><bc> <ec>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight r %}
round(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# default값�<U+393C><U+3E64>� 0<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
round(3.141592,0)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# 반올림해<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� 3번째 <U+653C><U+3E63>��리까지 <U+653C><U+3E64>��<U+653C><U+3E64>��
round(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3.142
{% endhighlight %}



{% highlight r %}
# 반올림해<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>�� 1번째 <U+653C><U+3E63>��리만 <U+653C><U+3E64>��<U+653C><U+3E64>��
round(3.141592,-1)
{% endhighlight %}



{% highlight text %}
## [1] 0
{% endhighlight %}

***

### trunc(): 버림 <ed>��<ec>��

<ec>��<ec>��<ec>��<ec>�� 모두 버리<eb>�� <ed>��<ec>��<ec>��<eb>��.


{% highlight r %}
trunc(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� 3번째 <U+653C><U+3E63>��리밑<U+653C><U+3E63>���<U+393C><U+3E63> 버림<U+653C><U+3E63><U+393C><U+3E64>� <U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E62>��.
trunc(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

***

### signif(): 반올�<bc> <ed>��<ec>��(<ec>���<98> <ec>��<ec>��)

`round()`<ed>��<ec>��<ec><99>� <eb>��르게 <ec>��<ec>�� 첫번�<b8> <ec>��리�<b0>� 1�<9c> 기�<a4>�<ec>�� <eb>��<ec>�� <ed>��<eb>�� <ec>��치값<ec>�� 맞게 반올림을 <ed>��준<eb>��.


{% highlight r %}
signif(45.926,1)
{% endhighlight %}



{% highlight text %}
## [1] 50
{% endhighlight %}



{% highlight r %}
signif(45.926,2)
{% endhighlight %}



{% highlight text %}
## [1] 46
{% endhighlight %}



{% highlight r %}
signif(45.926,3)
{% endhighlight %}



{% highlight text %}
## [1] 45.9
{% endhighlight %}

***

### floor(): 같거<eb>�� <ec>��<ec><9d>� <ec>��<ec>���<bc> 추출<ed>��<eb>�� <ed>��<ec>��


{% highlight r %}
floor(45.926)
{% endhighlight %}



{% highlight text %}
## [1] 45
{% endhighlight %}



{% highlight r %}
floor(-45.926)
{% endhighlight %}



{% highlight text %}
## [1] -46
{% endhighlight %}

***

### mod(): 모드<ed>��<ec>��<eb>�� <ec>��<eb>��.

<ec>��<ec>��<ed>��<eb>���<b4> `%%`<ec><99>� `%/%`�<bc> <ec>��<ec>��<ed>��<ec>�� <ed>��<eb>��.


{% highlight r %}
# 몫만 추출<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>��머���<U+3E37>��<U+383C><U+3E63> 추출<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}

## <eb>��짜함<ec>��

### Sys.Date(): <ed>��<ec>�� <ec>���<84> <eb>���<9c> <ed>��<ec>��


{% highlight r %}
Sys.Date()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08"
{% endhighlight %}

***

### Sys.time()/date(): <ec>��버의 <ed>��<ec>�� <ec>��<ec>�� <ec>���<84> <ed>��<ec>��


{% highlight r %}
Sys.time()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
date()
{% endhighlight %}



{% highlight text %}
## [1] "Mon Oct 08 19:27:36 2018"
{% endhighlight %}

***

### as.Date(): 문자<eb>��짜�<a5><bc> <eb>��짜형<ec>���<9c> 변<ed>��<ed>��<eb>�� <ed>��<ec>��

지<ec>��<ec>�� 종속<eb>���<b0> <eb>��문에 <eb>��<ec>���<bc> 같이 �<b8> 지<ec>��<ec>�� 문자<ec>�� <ed>��준<ec>��<ec>��<ec>�� 맞게 <ec>��주어<ec>�� <ed>��<eb>��.


{% highlight r %}
as.Date('2018-07-25')
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-25"
{% endhighlight %}



{% highlight r %}
as.Date('2018/07/25')
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-25"
{% endhighlight %}

<ed>��준<ec>��<ec>��<ec>�� 맞게 <ec>��지 <ec>��<eb>��<eb>���<b4>, `format`<ec>�� <ec>��주어<ec>�� <ed>��준<ec>��<ec>��<ec>���<9c> 변<ed>��<eb>��<eb>��.


{% highlight r %}
as.Date('20180725',format = '%Y%m%d')

as.Date('2018<U+653C><U+3E62>�� 1<U+653C><U+3E63>�� 2<U+653C><U+3E63>��',format = '%Y<U+653C><U+3E62>��%m<U+653C><U+3E63>��%d<U+653C><U+3E63>��')
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 3
{% endhighlight %}

#### <eb>���<9c> Format

`format`<ec>�� <ec>��<ec>�� option<ec><9d>� <eb>��<ec>���<bc> 같다.

    `%Y`: <ec>��기�<a5><bc> <ed>��<ed>��<ed>�� <eb>��<eb>��(4<ec>���<ac>)
    `%y`: <ec>��기�<a5><bc> <ec>��<eb>��<ed>�� <eb>��<eb>��(2<ec>���<ac>)
    `%m`: <ec>��<ec>��<eb>��
    `%B`: 문자<eb>��
    `%b`: 문자<eb>��<ec>�� <ec>��<ec>��
    `%d`: <ec>��
    `%A`: 문자<ec>��<ec>��
    `%a`: 문자<ec>��<ec>��<ec>�� <ec>��<ec>��
    `%u`: <ec>��<ec>��<ec>��<ec>��(1(<ec>��)~7(<ec>��))
    `%w`: <ec>��<ec>��<ec>��<ec>��(0(<ec>��)~6(<ec>��))
    `%H`: <ec>��
    `%M`: �<84>
    `%S`: �<88>
    `%z`: timezone <ec>���<84>
    `%Z`: timezone <ec>���<84>
    
`format`<ec>�� <ec>��<ec>��<ed>��<ec>�� <eb>��<ec>���<bc> 같이 <ed>�� <ec>�� <ec>��<eb>��.


{% highlight r %}
format(Sys.time(),'%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "18-10-08-������ 19:27:36"
{% endhighlight %}
    
***

### <eb>���<9c> 계산 방법


{% highlight r %}
# <U+653C><U+3E62>���<U+393C><U+3E63> + <U+653C><U+3E63>��<U+653C><U+3E63>�� = <U+653C><U+3E62>���<U+393C><U+3E63>
Sys.Date() + 100
{% endhighlight %}



{% highlight text %}
## [1] "2019-01-16"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>���<U+393C><U+3E63> - <U+653C><U+3E63>��<U+653C><U+3E63>�� = <U+653C><U+3E62>���<U+393C><U+3E63>
Sys.Date() - 200
{% endhighlight %}



{% highlight text %}
## [1] "2018-03-22"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E62>��짜���<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E62>��<U+653C><U+3E64>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
as.Date('2018-01-01', format = '%Y-%m-%d') + 100
{% endhighlight %}



{% highlight text %}
## [1] "2018-04-11"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>���<U+393C><U+3E63> - <U+653C><U+3E62>���<U+393C><U+3E63> = <U+653C><U+3E63>��<U+653C><U+3E63>��
as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## Time difference of -182 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>��짜의 차이<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��값만 보고 <U+653C><U+3E63>��<U+653C><U+3E63><U+393C><U+3E64>� 경우
as.numeric(as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] -182
{% endhighlight %}

***

### weekdays(): <ec>��<ec>��<ec>�� 출력<ed>��<eb>�� <ed>��<ec>��


{% highlight r %}
weekdays(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "������"
{% endhighlight %}



{% highlight r %}
weekdays(as.Date('2000-01-01', format='%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "�����"
{% endhighlight %}

***

### dfftime(): <eb>�� <eb>��짜간<ec>�� <ec>�� <ec>�� <ed>��<ed>��


{% highlight r %}
difftime('2018-01-01', Sys.Date())
{% endhighlight %}



{% highlight text %}
## Time difference of -280.375 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��<U+653C><U+3E63>���<U+383C><U+3E63> 출력<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63><U+393C><U+3E64>� 경우
as.numeric(difftime('2018-01-01', Sys.Date()))
{% endhighlight %}



{% highlight text %}
## [1] -280.375
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��<U+653C><U+3E63>��값만 출력<U+653C><U+3E64>�����<U+3E30> <U+653C><U+3E63>��<U+653C><U+3E63><U+393C><U+3E64>� 경우
round(as.numeric(difftime('2018-01-01', Sys.Date())))
{% endhighlight %}



{% highlight text %}
## [1] -280
{% endhighlight %}

***

### as.difftime(): <ec>��간의 차이


{% highlight r %}
as.difftime('18:30:00') - as.difftime('09:30:00')
{% endhighlight %}



{% highlight text %}
## Time difference of 9 hours
{% endhighlight %}



{% highlight r %}
as.numeric(as.difftime('20:20:00') - as.difftime('09:30:00'))
{% endhighlight %}



{% highlight text %}
## [1] 10.83333
{% endhighlight %}

***

### quarters(): 분기 <ed>��<ed>��

<ed>��<eb>�� <eb>��짜의 분기 <ec>��보�<a5><bc> <ed>��<ed>��<ed>��<eb>��.


{% highlight r %}
quarters(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Q4"
{% endhighlight %}

***

### lubridate <ed>��<ed>��지: <eb>���<9c> <ed>��<ed>�� <ed>��<ed>��지

`lubridate()`<eb>�� <eb>��짜�<a5><bc> <eb>���<b0> <eb>�� <ec>��<ec>��<ed>�� <ed>��<ed>��지<eb>��. <eb>��짜�<a5><bc> 출력<ed>�� <eb>�� format<ec>�� <ec>��<ec>��<eb>�� <eb>��<eb>�� <ec>��<ec>��<ec>�� <ec>��<eb>��. 먼�<a0>� <ed>��<ed>��지 <ec>��치�<a5><bc> <ed>�� <eb>��<ec>��<ec>�� load�<bc> <ec>��켜주<ec>��<ec>�� <ed>��<eb>��.


{% highlight r %}
library(lubridate)

# <U+653C><U+3E62>���<U+393C><U+3E63> 출력
# <U+653C><U+3E64>��<U+653C><U+3E63>�� <U+653C><U+3E62>���<U+393C><U+3E63>
now()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��<U+653C><U+3E62>�� 출력 
year(now()) # format(Sys.time(),'%Y')<U+653C><U+3E63><U+393C><U+3E39>� 같다.
{% endhighlight %}



{% highlight text %}
## [1] 2018
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>�� 출력
month(now())
{% endhighlight %}



{% highlight text %}
## [1] 10
{% endhighlight %}



{% highlight r %}
# factor<U+653C><U+3E64>��<U+653C><U+3E63>���<U+393C><U+3E63> <U+653C><U+3E62>��<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E63>�� <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E62>��.
month(now(), label = T)
{% endhighlight %}



{% highlight text %}
## [1] 10
## Levels: 1 < 2 < 3 < 4 < 5 < 6 < 7 < 8 < 9 < 10 < 11 < 12
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>�� 출력
day(now())
{% endhighlight %}



{% highlight text %}
## [1] 8
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>��<U+653C><U+3E63>�� 출력
wday(now()) # format<U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� %u, %w<U+653C><U+3E63><U+393C><U+3E39>� <U+653C><U+3E62>��르다.
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 1) # <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� 기���<U+3E34>�<U+653C><U+3E63>���<U+393C><U+3E63> 출력
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7) # <U+653C><U+3E63>��<U+653C><U+3E63>��<U+653C><U+3E63>�� 기���<U+3E34>�<U+653C><U+3E63>���<U+393C><U+3E63> 출력
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7, label = T) # level 출력
{% endhighlight %}



{% highlight text %}
## [1] ��
## Levels: �� < �� < ȭ < �� < �� < �� < ��
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>���<U+393C><U+3E63> <U+653C><U+3E63>��/개월 <U+653C><U+3E62>��<U+653C><U+3E63>�� <U+653C><U+3E63>�� 출력
# <U+653C><U+3E63>�� <U+653C><U+3E63>�� (<U+653C><U+3E63>��<U+653C><U+3E62>��<U+653C><U+3E64>��<U+653C><U+3E63>�� to_yminterval()�<U+623C><U+3E63> 비슷<U+653C><U+3E64>��)
years(10)
{% endhighlight %}



{% highlight text %}
## [1] "10y 0m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# 개월 <U+653C><U+3E63>��
months(10)
{% endhighlight %}



{% highlight text %}
## [1] "10m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# 지금�<U+623C><U+3E36>�<U+653C><U+3E64>�� 10<U+653C><U+3E62>�� <U+653C><U+3E64>��
now() + years(10)
{% endhighlight %}



{% highlight text %}
## [1] "2028-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# 지금�<U+623C><U+3E36>�<U+653C><U+3E64>�� 100개월 <U+653C><U+3E64>��
now() + months(100)
{% endhighlight %}



{% highlight text %}
## [1] "2027-02-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# 지금�<U+623C><U+3E36>�<U+653C><U+3E64>�� 1000<U+653C><U+3E63>�� <U+653C><U+3E63>��
now() - days(1000)
{% endhighlight %}



{% highlight text %}
## [1] "2016-01-12 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# 지금�<U+623C><U+3E36>�<U+653C><U+3E64>�� 1<U+653C><U+3E62>�� 1개월 1<U+653C><U+3E63>�� 1<U+653C><U+3E63>���<U+383C><U+3E34> 1�<U+383C><U+3E34> 1�<U+383C><U+3E38> <U+653C><U+3E64>��
now() + years(1) + months(1) + days(1) + hours(1) + minutes(1) + seconds(1)
{% endhighlight %}



{% highlight text %}
## [1] "2019-11-09 20:28:37 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>���<U+383C><U+3E34> 계산
hm('08:00')
{% endhighlight %}



{% highlight text %}
## [1] "8H 0M 0S"
{% endhighlight %}



{% highlight r %}
now() + hm('08:00')
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-09 03:27:36 KST"
{% endhighlight %}



{% highlight r %}
now() + hms('02:30:59')
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 21:58:35 KST"
{% endhighlight %}

<ec>��<eb>��/<eb>�� <eb>��<ec>�� 바꾸<ec>��<ec>�� <eb>��루기 <ec>��<ed>��<eb>���<b4> <eb>��<ec>���<bc> 같이 변<ec>��<ec>��<eb>��가 <eb>��짜�<a5><bc> <eb>���<a0> <eb>��<ec>�� 바꿔�<84> <ec>�� <ec>��<eb>��.


{% highlight r %}
date <- now()
# <U+653C><U+3E63>��<U+653C><U+3E62>�� <U+653C><U+3E63>��<U+653C><U+3E63>��
year(date) <- 2017
date
{% endhighlight %}



{% highlight text %}
## [1] "2017-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>�� <U+653C><U+3E63>��<U+653C><U+3E63>��
month(date) <- 1 

# <U+653C><U+3E63>�� <U+653C><U+3E63>��<U+653C><U+3E63>��
day(date) <- 1

# <U+653C><U+3E63>���<U+383C><U+3E34> <U+653C><U+3E63>��<U+653C><U+3E63>��
hour(date) <- 00
minute(date) <- 00
second(date) <- 00

format(date, '%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "17-01-01-�Ͽ��� 00:00:00"
{% endhighlight %}

***

### POSIX Type

POSIX(Portable Opearating System Interface)<eb>�� UNIX �<84> <ec>��<ed>�� 가<eb>��<ed>�� <ed>��로그<eb>�� <ec>��<ed>��<ed>��<ec>��<ec>��<ec>�� 규약<ec>��<eb>��. R<ec>��<ec>��<eb>�� <eb>���<9c> <ec>���<84> <eb>��<ec>��<ed>���<bc> 처리<ed>�� <ec>�� <ec>��<eb>���<9d> `POSIXct`,`POSIXt(POSIXlt)` <ed>��<eb>��<ec>���<bc> <ec>��<ec>��<ed>��<eb>��. POSIX<ed><83>�<ec>��<ec><9d>� <eb>��<ec>�� 2가지<ec>��<eb>��.

- POSIXct(continuous) 
- POSIXt(POSIX l t)(list time)


{% highlight r %}
class(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Date"
{% endhighlight %}



{% highlight r %}
mode(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}



{% highlight r %}
class(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] "POSIXct" "POSIXt"
{% endhighlight %}



{% highlight r %}
mode(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

class�<9c> `POSIX`<ed><83>�<ec>���<bc> `DATE`<ed><83>�<ec>��<ec>�� <ec>�� <ec>�� <ec>��<eb>��. `POSIX` <ed><83>�<ec>��<ec>�� <ec>��<ec>��<ed>�� <ec>��<ec>��보자.


{% highlight r %}
# <U+653C><U+3E63>��간을 numeric<U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E63>���<U+393C><U+3E63> <U+653C><U+3E64><U+393C><U+3E32>�<U+653C><U+3E63>��<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E64>��<U+653C><U+3E62>��<U+653C><U+3E62>��.
as.numeric(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] 1538994457
{% endhighlight %}



{% highlight r %}
# POSIXlt<U+653C><U+3E63>���<U+393C><U+3E63> <U+653C><U+3E64>�� 변<U+653C><U+3E64>��
time <- as.POSIXlt(Sys.time())
time
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# POSIX<U+653C><U+3E63>�� list<U+653C><U+3E64><U+383C><U+3E33>�<U+653C><U+3E63>�� <U+653C><U+3E64>��<U+653C><U+3E63>��<U+653C><U+3E63>���<U+393C><U+3E63> 보여준<U+653C><U+3E62>��.
unlist(time)
{% endhighlight %}



{% highlight text %}
##                sec                min               hour 
## "36.6481280326843"               "27"               "19" 
##               mday                mon               year 
##                "8"                "9"              "118" 
##               wday               yday              isdst 
##                "1"              "280"                "0" 
##               zone             gmtoff 
##              "KST"            "32400"
{% endhighlight %}

`POSIX`<ec>�� <ec>��<ec>��값�<9d>� <eb>��<ec>���<bc> 같다.
    

    `mday`: �<b8> <eb>��<ec>�� <ec>��
    `mon`: 1<ec>��<ec>�� 0<ec>���<9c> <ec>��<ec>��<ed>��<eb>�� <eb>��
    `year`: 1900<eb>��<ec>�� 0<ec>���<9c> <ec>��<ec>��<ed>��<eb>�� <eb>��
    `wday`: <ec>��<ec>��<ec>��<ec>�� 0<ec>���<9c> <ec>��<ec>��<ed>��<eb>�� <ec>��
    `yday`: 1<ec>�� 1<ec>��<ec>�� 0<ec>���<9c> <ec>��<ec>��<ed>��<eb>�� <ec>��
    `isdst`: <ec>��머�<83>�<ec>��
    `zone`: timezone <ec>���<84>
    `gmtoff`: timezone<ec>�� <ec>��(초단<ec>���<9c>)


#### strptime(): POSIX<ed><83>�<ec>��<ec>���<9c> <ed>��변<ed>��

`strptime()`�<bc> <ec>��<ec>��<ed>���<b4> `POSIX`<ed><83>�<ec>��<ec>���<9c> <ed>��<ec>�� 변<ed>�� <ec>��<ed>�� <ec>�� <ec>��<eb>��.


{% highlight r %}
date <- '2018-07-26'
as.Date(date, format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-26"
{% endhighlight %}



{% highlight r %}
class(as.Date(date, format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "Date"
{% endhighlight %}



{% highlight r %}
## POSIX<U+653C><U+3E64>��<U+653C><U+3E64>��로의 <U+653C><U+3E64>��변<U+653C><U+3E64>��
strptime(date,format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-26 KST"
{% endhighlight %}



{% highlight r %}
class(strptime(date,format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "POSIXlt" "POSIXt"
{% endhighlight %}
