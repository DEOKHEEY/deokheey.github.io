---
layout: post
title: "[R] Function"
date: "2018-07-01"
excerpt: "R<ec><ec><ec> <ed>¨<ec>"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## λ¬Έμ<ed>¨<ec>

### grep(): λ¬Έμ<ec>΄ <ed>¨<ed>΄ κ²<ec> <ed>¨<ec>

λ¬Έμ <ed>¨<ed>΄<ec> μ°Ύμ <eb> <ec>¬<ec>©<eb><eb> <ed>¨<ec><ec>΄<eb>€. <eb>€<ec> <ed>Ή<ec>λ¬Έμ<ec><99> option<ec> <ec>¬<ec>©<ed>  <ec> <ec><eb>€.

    ^ : μ²«λ²μ§<b8> 
    $ : λ§μ<a7>λ§<89>
    . : <ed>Ή<ec>  <ec>λ¦¬μ
    * : wild card

`ignore.case`
- `ignore.case = TRUE`: <eb><8c><ec>λ¬Έμ κ΅¬λΆ<ec><ed><eb>€.  
- `ignore.case = FALSE`: <eb><8c><ec>λ¬Έμ κ΅¬λΆ<ed><eb>€.


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

### nchar(): λ¬Έμ <ec>λ₯<bc> return<ed><eb> <ed>¨<ec>

κ³΅λ°±κΉμ<a7> <ed>¬<ed>¨<ed> λ¬Έμ<ec> <ec>λ₯<bc> return<ed>΄μ€<eb>€. option<ec>Όλ‘<9c> `type`<ec> <ec>€<ec> <ed><ec>¬ κ·<b8> <ed><83><ec><ec> λ§κ² <ec>Έ<ec>΄ μ€<84> <ec> <ec><eb>€.


{% highlight r %}
nchar('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# charλ‘<U+393C><U+3E63> <U+653C><U+3E63>Ό<U+653C><U+3E62>€
nchar('R Developer', type = "chars")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# byteκ°μΌλ‘<U+393C><U+3E63> <U+653C><U+3E63>Ό<U+653C><U+3E62>€.
nchar('R Developer', type = "bytes")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}

***

### strsplit(): λΆλΆλ¬Έ<ec>λ‘<9c> λΆλ¦¬<ed><eb> <ed>¨<ec>

λ¬Έμλ₯<bc> λΆλ¦¬<ed>΄μ€<eb>€. <ec>΄ <ed>¨<ec><eb> `split`<ec>΄<eb>Ό<eb> option<ec> λ°λ<ec> <ec>¬<ec>©<ed>΄<ec>Ό <ed><eb>€. <ec>΄<eb> <ed> κΈ<ec>κ° <ec>μ£<bc> <eb>±<ec>₯<ed><eb>μ§ <ed><ec><ed>  <eb> <eb><ec><9b><ec>΄ <eb><eb>€.


{% highlight r %}
# split<U+653C><U+3E63>΄<U+653C><U+3E62>Ό<U+653C><U+3E62> option<U+653C><U+3E63> λ°λ<U+653C><U+3E63> <U+653C><U+3E63>¬<U+653C><U+3E63>©<U+653C><U+3E64>΄<U+653C><U+3E63>Ό <U+653C><U+3E64><U+653C><U+3E62>€.
# <U+653C><U+3E64>κΈ<U+653C><U+3E63><U+653C><U+3E63>© λΆλ¦¬(character<U+653C><U+3E63><U+653C><U+3E63> κ°μ λ°κΎΈ<U+653C><U+3E63>΄<U+653C><U+3E62> κ²°κ³Ό<U+653C><U+3E62> κ°μ)
strsplit('R Developer',split = character(0))
{% endhighlight %}



{% highlight text %}
## [[1]]
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}



{% highlight r %}
# κ³΅λ°±<U+653C><U+3E63> κΈ°μγε<U+3E34><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λΆλ¦¬
strsplit('R Developer',split =" ")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}



{% highlight r %}
# ,λ₯<U+623C><U+3E63> κΈ°μγε<U+3E34><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λΆλ¦¬
strsplit('R,Developer',split =",")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}

κ²°κ³Ό<eb> list type<ec>Όλ‘<9c> μΆλ ₯<eb>¨<ec> <ec> <ec> <ec><eb>€. <ec><eb> <ed>¨<ec>λ₯<bc> μ°Έκ³ <ed><ec>.

### unlist(): list<ed><ec> vector<ed><ec>Όλ‘<9c> λ³<ed> <ed>¨<ec>

<ec><ec> <ec>΄<ec>΄<ec>, λ§μ½ Vector type<ec>Όλ‘<9c> λ°κΎΈκ³<a0> <ec>Ά<eb>€λ©<b4> `unlist(strsplit())`<ec> <ec>¬<ec>©<ed>λ©<b4> <ed>λ©<b4> <eb><eb>€.


{% highlight r %}
unlist(strsplit('R Developer',split = character(0)))
{% endhighlight %}



{% highlight text %}
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}

***

### toupper()/tolower(): <eb><8c><ec>λ¬Έμ λ³<ed><ed><eb> <ed>¨<ec>

<ec><ed>λ²³μ <eb><8c><ec>λ¬Έμλ‘<9c> λ³<ed><ed><eb> <ed>¨<ec><ec>΄<eb>€.


{% highlight r %}
# <U+653C><U+3E62><U+383C><U+3E63>λ¬Έμλ‘<U+393C><U+3E63> λ³<U+653C><U+3E64>
toupper('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "R DEVELOPER"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>λ¬Έμλ‘<U+393C><U+3E63> λ³<U+653C><U+3E64>
tolower('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "r developer"
{% endhighlight %}

***

### substr(): λ¬Έμ<ec>΄ μΆμΆ <ed>¨<ec>

`substr(' ',<ec><ec><ec> ,<eb><ec> )`<ec>΄<eb>€. sql<ec><ec><ec><99> `substr()`<ec><99> <eb>€λ¦μ μ£Όμ<ed><ec>.


{% highlight r %}
# μ²«λ²μ§Έλ<U+623C><U+3E36><U+653C><U+3E64>° μ²«λ²μ§ΈκΉμ§ μΆμΆ
substr('R Developer',1,1)
{% endhighlight %}



{% highlight text %}
## [1] "R"
{% endhighlight %}



{% highlight r %}
# μ²«λ²μ§Έλ<U+623C><U+3E36><U+653C><U+3E64>° <U+653C><U+3E63>Έλ²μ§ΈκΉμγε<U+3E37> μΆμΆ
substr('R Developer',1,3)
{% endhighlight %}



{% highlight text %}
## [1] "R D"
{% endhighlight %}



{% highlight r %}
# 5λ²μ§ΈλΆ<U+653C><U+3E64>° 11λ²μ§Έ μΆμΆ
substr('R Developer',5,11)
{% endhighlight %}



{% highlight text %}
## [1] "veloper"
{% endhighlight %}

***

### sub(): μ²«λ²μ§<b8> <ec>ΌμΉν<eb> λ¬Έμλ§<8c> λ°κΎΈ<eb> <ed>¨<ec>

`sub('μ°Ύμ<ec>Ό <ed>  κΈ<ec>','λ°κΏ<ec>Ό <ed>  κΈ<ec>','<ed>΄<eb>Ή <eb>°<ec>΄<ed>°')`λ‘<9c> <ec>¬<ec>©<ed><eb>€. <ed>μ§λ§<8c> μ°Ύμ<ec>Ό <ed>  κΈ<ec>κ° λ§λ€λ©<b4> μ²«λ²μ§Έλ‘ <ec>ΌμΉν<eb> κΈ<ec>λ§<8c> λ°κΏ<ec>Ό <ed>  κΈ<ec>λ‘<9c> λ°κΎΈ<ec>΄μ€<eb>€.


{% highlight r %}
# 3λ²μ§Έ<U+653C><U+3E63> κ°μ<U+653C><U+3E63> R<U+653C><U+3E63> Python<U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λ°κΎΈ<U+653C><U+3E62><U+653C><U+3E62>° μ²«λ²μ§Έλ‘ μ°Ύλ R<U+653C><U+3E63> λ°κΎΌ<U+653C><U+3E62>€.
sub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer R Developer"
{% endhighlight %}

***

### gsub(): <ec>ΌμΉν<eb> λ¬Έμλ₯<bc> λͺ¨λ λ°κΎΈ<eb> <ed>¨<ec>

`gsub('μ°Ύμ<ec>Ό <ed>  κΈ<ec>','λ°κΏ<ec>Ό <ed>  κΈ<ec>','<ed>΄<eb>Ή <eb>°<ec>΄<ed>°')`λ‘<9c> <ec>¬<ec>©<ed><eb>€. `sub()`κ³<bc> <eb>€λ₯΄κ² <ec>ΌμΉν<eb> λ¬Έμλ₯<bc> λͺ¨λ λ°κΎΈ<ec>΄μ€<eb>€.


{% highlight r %}
# 3λ²μ§Έ<U+653C><U+3E63> κ°μ<U+653C><U+3E63> R<U+653C><U+3E63> <U+653C><U+3E63>ΌμΉν<U+653C><U+3E62> λ¬Έμλ₯<U+623C><U+3E63> <U+653C><U+3E63> λΆ  Python<U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λ°κΎΈ<U+653C><U+3E63>΄μ€<U+653C><U+3E62>€.
gsub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer Python Developer"
{% endhighlight %}



{% highlight r %}
# 0λΆ<U+653C><U+3E64>° 2<U+653C><U+3E63>¬<U+653C><U+3E63>΄<U+653C><U+3E63> <U+653C><U+3E63>«<U+653C><U+3E63>λ₯<U+623C><U+3E63> *λ‘<U+393C><U+3E63> λ°κΎΈ<U+653C><U+3E63>΄μ€<U+653C><U+3E62>€.
gsub('[0-2]','*','123450')
{% endhighlight %}



{% highlight text %}
## [1] "**345*"
{% endhighlight %}


***

## <ec>«<ec><ed>¨<ec>

### round(): λ°μ¬λ¦<bc> <ed>¨<ec>

option<ec> <ec>¬<ec>©<ed><ec>¬ λ°μ¬λ¦Όν  <ec>μΉλ<a5><bc> <ec> <ed>  <ec> <ec><eb>€.


{% highlight r %}
round(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# defaultκ°μ<U+393C><U+3E64> 0<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E62>€.
round(3.141592,0)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# λ°μ¬λ¦Όν΄<U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63>  3λ²μ§Έ <U+653C><U+3E63>λ¦¬κΉμ§ <U+653C><U+3E64><U+653C><U+3E64>
round(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3.142
{% endhighlight %}



{% highlight r %}
# λ°μ¬λ¦Όν΄<U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63> 1λ²μ§Έ <U+653C><U+3E63>λ¦¬λ§ <U+653C><U+3E64><U+653C><U+3E64>
round(3.141592,-1)
{% endhighlight %}



{% highlight text %}
## [1] 0
{% endhighlight %}

***

### trunc(): λ²λ¦Ό <ed>¨<ec>

<ec><ec><ec> <ec> λͺ¨λ λ²λ¦¬<eb> <ed>¨<ec><ec>΄<eb>€.


{% highlight r %}
trunc(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63>  3λ²μ§Έ <U+653C><U+3E63>λ¦¬λ°<U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λ²λ¦Ό<U+653C><U+3E63><U+393C><U+3E64> <U+653C><U+3E63><U+653C><U+3E62><U+653C><U+3E62>€.
trunc(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

***

### signif(): λ°μ¬λ¦<bc> <ed>¨<ec>(<ec>μΉ<98> <ec><ec>)

`round()`<ed>¨<ec><ec><99> <eb>€λ₯΄κ² <ec> <ec>Ό μ²«λ²μ§<b8> <ec>λ¦¬κ<b0> 1λ‘<9c> κΈ°μ<a4><ec>΄ <eb><ec>΄ <ed>΄<eb>Ή <ec>μΉκ°<ec> λ§κ² λ°μ¬λ¦Όμ <ed>΄μ€<eb>€.


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

### floor(): κ°κ±°<eb> <ec><ec><9d> <ec> <ec>λ₯<bc> μΆμΆ<ed><eb> <ed>¨<ec>


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

### mod(): λͺ¨λ<ed>¨<ec><eb> <ec><eb>€.

<ec>¬<ec>©<ed><eb> €λ©<b4> `%%`<ec><99> `%/%`λ₯<bc> <ec>¬<ec>©<ed>΄<ec>Ό <ed><eb>€.


{% highlight r %}
# λͺ«λ§ μΆμΆ<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63> <U+653C><U+3E63>
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>λ¨Έμγε<U+3E37>λ§<U+383C><U+3E63> μΆμΆ<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63> <U+653C><U+3E63>
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}

## <eb> μ§ν¨<ec>

### Sys.Date(): <ed><ec>¬ <ec>λ²<84> <eb> μ§<9c> <ed><ec>


{% highlight r %}
Sys.Date()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08"
{% endhighlight %}

***

### Sys.time()/date(): <ec>λ²μ <ed><ec>¬ <ec><ec>Έ <ec>κ°<84> <ed><ec>


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

### as.Date(): λ¬Έμ<eb> μ§λ<a5><bc> <eb> μ§ν<ec>Όλ‘<9c> λ³<ed><ed><eb> <ed>¨<ec>

μ§<ec>­<ec> μ’μ<eb>κΈ<b0> <eb>λ¬Έμ <eb>€<ec>κ³<bc> κ°μ΄ κ·<b8> μ§<ec>­<ec> λ¬Έμ<ec>΄ <ed>μ€<ec><ec><ec> λ§κ² <ec>¨μ£Όμ΄<ec>Ό <ed><eb>€.


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

<ed>μ€<ec><ec><ec> λ§κ² <ec>°μ§ <ec><eb><eb>€λ©<b4>, `format`<ec> <ec>¨μ£Όμ΄<ec>Ό <ed>μ€<ec><ec><ec>Όλ‘<9c> λ³<ed><eb><eb>€.


{% highlight r %}
as.Date('20180725',format = '%Y%m%d')

as.Date('2018<U+653C><U+3E62> 1<U+653C><U+3E63> 2<U+653C><U+3E63>Ό',format = '%Y<U+653C><U+3E62>%m<U+653C><U+3E63>%d<U+653C><U+3E63>Ό')
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 3
{% endhighlight %}

#### <eb> μ§<9c> Format

`format`<ec> <ec><ec>Έ option<ec><9d> <eb>€<ec>κ³<bc> κ°λ€.

    `%Y`: <ec>ΈκΈ°λ<a5><bc> <ed>¬<ed>¨<ed> <eb><eb>(4<ec>λ¦<ac>)
    `%y`: <ec>ΈκΈ°λ<a5><bc> <ec><eb>΅<ed> <eb><eb>(2<ec>λ¦<ac>)
    `%m`: <ec>«<ec><eb>¬
    `%B`: λ¬Έμ<eb>¬
    `%b`: λ¬Έμ<eb>¬<ec> <ec>½<ec>΄
    `%d`: <ec>Ό
    `%A`: λ¬Έμ<ec><ec>Ό
    `%a`: λ¬Έμ<ec><ec>Ό<ec> <ec>½<ec>΄
    `%u`: <ec>«<ec><ec><ec>Ό(1(<ec>)~7(<ec>Ό))
    `%w`: <ec>«<ec><ec><ec>Ό(0(<ec>Ό)~6(<ec>))
    `%H`: <ec>
    `%M`: λΆ<84>
    `%S`: μ΄<88>
    `%z`: timezone <ec>κ°<84>
    `%Z`: timezone <ec>΄λ¦<84>
    
`format`<ec> <ec>¬<ec>©<ed><ec>¬ <eb>€<ec>κ³<bc> κ°μ΄ <ed>  <ec> <ec><eb>€.


{% highlight r %}
format(Sys.time(),'%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "18-10-08-ΏωΏδΐΟ 19:27:36"
{% endhighlight %}
    
***

### <eb> μ§<9c> κ³μ° λ°©λ²


{% highlight r %}
# <U+653C><U+3E62> μ§<U+393C><U+3E63> + <U+653C><U+3E63>«<U+653C><U+3E63> = <U+653C><U+3E62> μ§<U+393C><U+3E63>
Sys.Date() + 100
{% endhighlight %}



{% highlight text %}
## [1] "2019-01-16"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62> μ§<U+393C><U+3E63> - <U+653C><U+3E63>«<U+653C><U+3E63> = <U+653C><U+3E62> μ§<U+393C><U+3E63>
Sys.Date() - 200
{% endhighlight %}



{% highlight text %}
## [1] "2018-03-22"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>Ή<U+653C><U+3E63>  <U+653C><U+3E62> μ§λγε<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>¬<U+653C><U+3E63>©<U+653C><U+3E64><U+653C><U+3E63>¬ <U+653C><U+3E62><U+653C><U+3E64>  <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E62>€.
as.Date('2018-01-01', format = '%Y-%m-%d') + 100
{% endhighlight %}



{% highlight text %}
## [1] "2018-04-11"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62> μ§<U+393C><U+3E63> - <U+653C><U+3E62> μ§<U+393C><U+3E63> = <U+653C><U+3E63>«<U+653C><U+3E63>
as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## Time difference of -182 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62> μ§μ μ°¨μ΄<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63>«<U+653C><U+3E63>κ°λ§ λ³΄κ³  <U+653C><U+3E63>Ά<U+653C><U+3E63><U+393C><U+3E64> κ²½μ°
as.numeric(as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] -182
{% endhighlight %}

***

### weekdays(): <ec><ec>Ό<ec> μΆλ ₯<ed><eb> <ed>¨<ec>


{% highlight r %}
weekdays(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "ΏωΏδΐΟ"
{% endhighlight %}



{% highlight r %}
weekdays(as.Date('2000-01-01', format='%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "ΕδΏδΐΟ"
{% endhighlight %}

***

### dfftime(): <eb> <eb> μ§κ°<ec> <ec>Ό <ec> <ed><ed>


{% highlight r %}
difftime('2018-01-01', Sys.Date())
{% endhighlight %}



{% highlight text %}
## Time difference of -280.375 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>«<U+653C><U+3E63>λ§<U+383C><U+3E63> μΆλ ₯<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63><U+393C><U+3E64> κ²½μ°
as.numeric(difftime('2018-01-01', Sys.Date()))
{% endhighlight %}



{% highlight text %}
## [1] -280.375
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63> <U+653C><U+3E63>κ°λ§ μΆλ ₯<U+653C><U+3E64>κ³γε<U+3E30> <U+653C><U+3E63>Ά<U+653C><U+3E63><U+393C><U+3E64> κ²½μ°
round(as.numeric(difftime('2018-01-01', Sys.Date())))
{% endhighlight %}



{% highlight text %}
## [1] -280
{% endhighlight %}

***

### as.difftime(): <ec>κ°μ μ°¨μ΄


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

### quarters(): λΆκΈ° <ed><ed>

<ed>΄<eb>Ή <eb> μ§μ λΆκΈ° <ec> λ³΄λ<a5><bc> <ed><ed><ed><eb>€.


{% highlight r %}
quarters(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Q4"
{% endhighlight %}

***

### lubridate <ed>¨<ed>€μ§: <eb> μ§<9c> <ed><ed> <ed>¨<ed>€μ§

`lubridate()`<eb> <eb> μ§λ<a5><bc> <eb>€λ£<b0> <eb> <ec> <ec>©<ed> <ed>¨<ed>€μ§<eb>€. <eb> μ§λ<a5><bc> μΆλ ₯<ed>  <eb> format<ec> <ec><ec>¨<eb> <eb><eb> <ec>΄<ec> <ec>΄ <ec><eb>€. λ¨Όμ<a0> <ed>¨<ed>€μ§ <ec>€μΉλ<a5><bc> <ed> <eb>€<ec><ec> loadλ₯<bc> <ec>μΌμ£Ό<ec>΄<ec>Ό <ed><eb>€.


{% highlight r %}
library(lubridate)

# <U+653C><U+3E62> μ§<U+393C><U+3E63> μΆλ ₯
# <U+653C><U+3E64><U+653C><U+3E63>¬ <U+653C><U+3E62> μ§<U+393C><U+3E63>
now()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>°<U+653C><U+3E62> μΆλ ₯ 
year(now()) # format(Sys.time(),'%Y')<U+653C><U+3E63><U+393C><U+3E39> κ°λ€.
{% endhighlight %}



{% highlight text %}
## [1] 2018
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>¬ μΆλ ₯
month(now())
{% endhighlight %}



{% highlight text %}
## [1] 10
{% endhighlight %}



{% highlight r %}
# factor<U+653C><U+3E64><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> <U+653C><U+3E62><U+653C><U+3E63>΄<U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E62>€.
month(now(), label = T)
{% endhighlight %}



{% highlight text %}
## [1] 10
## Levels: 1 < 2 < 3 < 4 < 5 < 6 < 7 < 8 < 9 < 10 < 11 < 12
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>Ό μΆλ ₯
day(now())
{% endhighlight %}



{% highlight text %}
## [1] 8
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63><U+653C><U+3E63>Ό μΆλ ₯
wday(now()) # format<U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63> %u, %w<U+653C><U+3E63><U+393C><U+3E39> <U+653C><U+3E62>€λ₯΄λ€.
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 1) # <U+653C><U+3E63><U+653C><U+3E63><U+653C><U+3E63>Ό κΈ°μγε<U+3E34><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> μΆλ ₯
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7) # <U+653C><U+3E63>Ό<U+653C><U+3E63><U+653C><U+3E63>Ό κΈ°μγε<U+3E34><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> μΆλ ₯
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7, label = T) # level μΆλ ₯
{% endhighlight %}



{% highlight text %}
## [1] Ώω
## Levels: ΐΟ < Ώω < Θ­ < Όφ < Έρ < ±έ < Εδ
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62> μ§<U+393C><U+3E63> <U+653C><U+3E63>°/κ°μ <U+653C><U+3E62>±<U+653C><U+3E63> <U+653C><U+3E63> μΆλ ₯
# <U+653C><U+3E63>° <U+653C><U+3E63> (<U+653C><U+3E63>€<U+653C><U+3E62>Ό<U+653C><U+3E64>΄<U+653C><U+3E63> to_yminterval()κ³<U+623C><U+3E63> λΉμ·<U+653C><U+3E64>¨)
years(10)
{% endhighlight %}



{% highlight text %}
## [1] "10y 0m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# κ°μ <U+653C><U+3E63>
months(10)
{% endhighlight %}



{% highlight text %}
## [1] "10m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# μ§κΈλ<U+623C><U+3E36><U+653C><U+3E64>° 10<U+653C><U+3E62> <U+653C><U+3E64>
now() + years(10)
{% endhighlight %}



{% highlight text %}
## [1] "2028-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# μ§κΈλ<U+623C><U+3E36><U+653C><U+3E64>° 100κ°μ <U+653C><U+3E64>
now() + months(100)
{% endhighlight %}



{% highlight text %}
## [1] "2027-02-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# μ§κΈλ<U+623C><U+3E36><U+653C><U+3E64>° 1000<U+653C><U+3E63>Ό <U+653C><U+3E63> 
now() - days(1000)
{% endhighlight %}



{% highlight text %}
## [1] "2016-01-12 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# μ§κΈλ<U+623C><U+3E36><U+653C><U+3E64>° 1<U+653C><U+3E62> 1κ°μ 1<U+653C><U+3E63>Ό 1<U+653C><U+3E63>κ°<U+383C><U+3E34> 1λΆ<U+383C><U+3E34> 1μ΄<U+383C><U+3E38> <U+653C><U+3E64>
now() + years(1) + months(1) + days(1) + hours(1) + minutes(1) + seconds(1)
{% endhighlight %}



{% highlight text %}
## [1] "2019-11-09 20:28:37 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>κ°<U+383C><U+3E34> κ³μ°
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

<ec>°<eb>/<eb>¬ <eb>±<ec> λ°κΎΈ<ec>΄<ec> <eb>€λ£¨κΈ° <ec><ed><eb>€λ©<b4> <eb>€<ec>κ³<bc> κ°μ΄ λ³<ec><ec><eb>€κ° <eb> μ§λ<a5><bc> <eb>£κ³<a0> <eb> <ec> λ°κΏμ€<84> <ec> <ec><eb>€.


{% highlight r %}
date <- now()
# <U+653C><U+3E63>°<U+653C><U+3E62> <U+653C><U+3E63><U+653C><U+3E63> 
year(date) <- 2017
date
{% endhighlight %}



{% highlight text %}
## [1] "2017-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>¬ <U+653C><U+3E63><U+653C><U+3E63> 
month(date) <- 1 

# <U+653C><U+3E63>Ό <U+653C><U+3E63><U+653C><U+3E63> 
day(date) <- 1

# <U+653C><U+3E63>κ°<U+383C><U+3E34> <U+653C><U+3E63><U+653C><U+3E63> 
hour(date) <- 00
minute(date) <- 00
second(date) <- 00

format(date, '%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "17-01-01-ΐΟΏδΐΟ 00:00:00"
{% endhighlight %}

***

### POSIX Type

POSIX(Portable Opearating System Interface)<eb> UNIX κ°<84> <ec><ed>΅ κ°<eb>₯<ed> <ed>λ‘κ·Έ<eb>¨ <ec>Έ<ed>°<ed><ec>΄<ec>€<ec> κ·μ½<ec>΄<eb>€. R<ec><ec><eb> <eb> μ§<9c> <ec>κ°<84> <eb>°<ec>΄<ed>°λ₯<bc> μ²λ¦¬<ed>  <ec> <ec><eb>λ‘<9d> `POSIXct`,`POSIXt(POSIXlt)` <ed>΄<eb><ec>€λ₯<bc> <ec>¬<ec>©<ed><eb>€. POSIX<ed><83><ec><ec><9d> <eb>€<ec> 2κ°μ§<ec>΄<eb>€.

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

classλ‘<9c> `POSIX`<ed><83><ec>κ³<bc> `DATE`<ed><83><ec><ec> <ec> <ec> <ec><eb>€. `POSIX` <ed><83><ec><ec> <ec><ec>Έ<ed> <ec><ec>λ³΄μ.


{% highlight r %}
# <U+653C><U+3E63>κ°μ numeric<U+653C><U+3E64><U+653C><U+3E63><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> <U+653C><U+3E64><U+393C><U+3E32><U+653C><U+3E63>΄<U+653C><U+3E63> <U+653C><U+3E64><U+653C><U+3E64><U+653C><U+3E62><U+653C><U+3E62>€.
as.numeric(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] 1538994457
{% endhighlight %}



{% highlight r %}
# POSIXlt<U+653C><U+3E63>Όλ‘<U+393C><U+3E63> <U+653C><U+3E64> λ³<U+653C><U+3E64>
time <- as.POSIXlt(Sys.time())
time
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# POSIX<U+653C><U+3E63> list<U+653C><U+3E64><U+383C><U+3E33><U+653C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> λ³΄μ¬μ€<U+653C><U+3E62>€.
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

`POSIX`<ec> <ec><ec>Έκ°μ<9d> <eb>€<ec>κ³<bc> κ°λ€.
    

    `mday`: κ·<b8> <eb>¬<ec> <ec>Ό
    `mon`: 1<ec><ec> 0<ec>Όλ‘<9c> <ec><ec><ed><eb> <eb>¬
    `year`: 1900<eb><ec> 0<ec>Όλ‘<9c> <ec><ec><ed><eb> <eb>
    `wday`: <ec>Ό<ec><ec>Ό<ec> 0<ec>Όλ‘<9c> <ec><ec><ed><eb> <ec>Ό
    `yday`: 1<ec> 1<ec>Ό<ec> 0<ec>Όλ‘<9c> <ec><ec><ed><eb> <ec>Ό
    `isdst`: <ec>λ¨Έν<83><ec>
    `zone`: timezone <ec>΄λ¦<84>
    `gmtoff`: timezone<ec> <ec>(μ΄λ¨<ec>λ‘<9c>)


#### strptime(): POSIX<ed><83><ec><ec>Όλ‘<9c> <ed>λ³<ed>

`strptime()`λ₯<bc> <ec>¬<ec>©<ed>λ©<b4> `POSIX`<ed><83><ec><ec>Όλ‘<9c> <ed><ec> λ³<ed> <ec><ed>¬ <ec> <ec><eb>€.


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
## POSIX<U+653C><U+3E64><U+653C><U+3E64>λ‘μ <U+653C><U+3E64>λ³<U+653C><U+3E64>
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
