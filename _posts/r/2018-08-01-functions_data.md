---
layout: post
title: "[R] Function"
date: "2018-07-01"
excerpt: "R<ec>—<ec>„œ<ec>˜ <ed>•¨<ec>ˆ˜"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, function]
---

## ë¬¸ì<ed>•¨<ec>ˆ˜

### grep(): ë¬¸ì<ec>—´ <ed>Œ¨<ed>„´ ê²€<ec>ƒ‰ <ed>•¨<ec>ˆ˜

ë¬¸ì <ed>Œ¨<ed>„´<ec>„ ì°¾ì„ <eb>•Œ <ec>‚¬<ec>š©<eb>˜<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤. <eb>‹¤<ec>Œ <ed>Š¹<ec>ˆ˜ë¬¸ì<ec><99>€ option<ec>„ <ec>‚¬<ec>š©<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.

    ^ : ì²«ë²ˆì§<b8> 
    $ : ë§ˆì<a7>€ë§<89>
    . : <ed>Š¹<ec> • <ec>ë¦¬ìˆ˜
    * : wild card

`ignore.case`
- `ignore.case = TRUE`: <eb><8c>€<ec>†Œë¬¸ì êµ¬ë¶„<ec>•ˆ<ed>•œ<eb>‹¤.  
- `ignore.case = FALSE`: <eb><8c>€<ec>†Œë¬¸ì êµ¬ë¶„<ed>•œ<eb>‹¤.


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

### nchar(): ë¬¸ì <ec>ˆ˜ë¥<bc> return<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

ê³µë°±ê¹Œì<a7>€ <ed>¬<ed>•¨<ed>•œ ë¬¸ì<ec>˜ <ec>ˆ˜ë¥<bc> return<ed>•´ì¤€<eb>‹¤. option<ec>œ¼ë¡<9c> `type`<ec>„ <ec>„¤<ec> •<ed>•˜<ec>—¬ ê·<b8> <ed><83>€<ec>…<ec>— ë§ê²Œ <ec>„¸<ec>–´ ì¤<84> <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
nchar('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# charë¡<U+393C><U+3E63> <U+653C><U+3E63>„¼<U+653C><U+3E62>‹¤
nchar('R Developer', type = "chars")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# byteê°’ìœ¼ë¡<U+393C><U+3E63> <U+653C><U+3E63>„¼<U+653C><U+3E62>‹¤.
nchar('R Developer', type = "bytes")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}

***

### strsplit(): ë¶€ë¶„ë¬¸<ec>ë¡<9c> ë¶„ë¦¬<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

ë¬¸ìë¥<bc> ë¶„ë¦¬<ed>•´ì¤€<eb>‹¤. <ec>´ <ed>•¨<ec>ˆ˜<eb>Š” `split`<ec>´<eb>¼<eb>Š” option<ec>„ ë°˜ë“œ<ec>‹œ <ec>‚¬<ec>š©<ed>•´<ec>•¼ <ed>•œ<eb>‹¤. <ec>–´<eb>– <ed>•œ ê¸€<ec>ê°€ <ec>ì£<bc> <eb>“±<ec>¥<ed>•˜<eb>Š”ì§€ <ed>ŒŒ<ec>•…<ed>•  <eb>•Œ <eb>„<ec><9b>€<ec>´ <eb>œ<eb>‹¤.


{% highlight r %}
# split<U+653C><U+3E63>´<U+653C><U+3E62>¼<U+653C><U+3E62>Š” option<U+653C><U+3E63>„ ë°˜ë“œ<U+653C><U+3E63>‹œ <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•´<U+653C><U+3E63>•¼ <U+653C><U+3E64>•œ<U+653C><U+3E62>‹¤.
# <U+653C><U+3E64>•œê¸€<U+653C><U+3E63><U+653C><U+3E63>”© ë¶„ë¦¬(character<U+653C><U+3E63>•ˆ<U+653C><U+3E63>˜ ê°’ì„ ë°”ê¾¸<U+653C><U+3E63>–´<U+653C><U+3E62>„ ê²°ê³¼<U+653C><U+3E62>Š” ê°™ìŒ)
strsplit('R Developer',split = character(0))
{% endhighlight %}



{% highlight text %}
## [[1]]
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}



{% highlight r %}
# ê³µë°±<U+653C><U+3E63>„ ê¸°ìãå<U+3E34>€<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë¶„ë¦¬
strsplit('R Developer',split =" ")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}



{% highlight r %}
# ,ë¥<U+623C><U+3E63> ê¸°ìãå<U+3E34>€<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë¶„ë¦¬
strsplit('R,Developer',split =",")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}

ê²°ê³¼<eb>Š” list type<ec>œ¼ë¡<9c> ì¶œë ¥<eb>¨<ec>„ <ec>•Œ <ec>ˆ˜ <ec>ˆ<eb>‹¤. <ec>•„<eb>˜ <ed>•¨<ec>ˆ˜ë¥<bc> ì°¸ê³ <ed>•˜<ec>.

### unlist(): list<ed>˜•<ec>„ vector<ed>˜•<ec>œ¼ë¡<9c> ë³€<ed>™˜ <ed>•¨<ec>ˆ˜

<ec>œ„<ec>— <ec>´<ec>–´<ec>„œ, ë§Œì•½ Vector type<ec>œ¼ë¡<9c> ë°”ê¾¸ê³<a0> <ec>‹¶<eb>‹¤ë©<b4> `unlist(strsplit())`<ec>„ <ec>‚¬<ec>š©<ed>•˜ë©<b4> <ed>•˜ë©<b4> <eb>œ<eb>‹¤.


{% highlight r %}
unlist(strsplit('R Developer',split = character(0)))
{% endhighlight %}



{% highlight text %}
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}

***

### toupper()/tolower(): <eb><8c>€<ec>†Œë¬¸ì ë³€<ed>™˜<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

<ec>•Œ<ed>ŒŒë²³ì„ <eb><8c>€<ec>†Œë¬¸ìë¡<9c> ë³€<ed>™˜<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤.


{% highlight r %}
# <U+653C><U+3E62><U+383C><U+3E63>€ë¬¸ìë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
toupper('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "R DEVELOPER"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>†Œë¬¸ìë¡<U+393C><U+3E63> ë³€<U+653C><U+3E64>™˜
tolower('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "r developer"
{% endhighlight %}

***

### substr(): ë¬¸ì<ec>—´ ì¶”ì¶œ <ed>•¨<ec>ˆ˜

`substr(' ',<ec>‹œ<ec>‘<ec> ,<eb><ec> )`<ec>´<eb>‹¤. sql<ec>—<ec>„œ<ec><99>€ `substr()`<ec><99>€ <eb>‹¤ë¦„ì„ ì£¼ì˜<ed>•˜<ec>.


{% highlight r %}
# ì²«ë²ˆì§¸ë<U+623C><U+3E36>€<U+653C><U+3E64>„° ì²«ë²ˆì§¸ê¹Œì§€ ì¶”ì¶œ
substr('R Developer',1,1)
{% endhighlight %}



{% highlight text %}
## [1] "R"
{% endhighlight %}



{% highlight r %}
# ì²«ë²ˆì§¸ë<U+623C><U+3E36>€<U+653C><U+3E64>„° <U+653C><U+3E63>„¸ë²ˆì§¸ê¹Œìãå<U+3E37>€ ì¶”ì¶œ
substr('R Developer',1,3)
{% endhighlight %}



{% highlight text %}
## [1] "R D"
{% endhighlight %}



{% highlight r %}
# 5ë²ˆì§¸ë¶€<U+653C><U+3E64>„° 11ë²ˆì§¸ ì¶”ì¶œ
substr('R Developer',5,11)
{% endhighlight %}



{% highlight text %}
## [1] "veloper"
{% endhighlight %}

***

### sub(): ì²«ë²ˆì§<b8> <ec>¼ì¹˜í•˜<eb>Š” ë¬¸ìë§<8c> ë°”ê¾¸<eb>Š” <ed>•¨<ec>ˆ˜

`sub('ì°¾ì•„<ec>•¼ <ed>•  ê¸€<ec>','ë°”ê¿”<ec>•¼ <ed>•  ê¸€<ec>','<ed>•´<eb>‹¹ <eb>°<ec>´<ed>„°')`ë¡<9c> <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. <ed>•˜ì§€ë§<8c> ì°¾ì•„<ec>•¼ <ed>•  ê¸€<ec>ê°€ ë§ë‹¤ë©<b4> ì²«ë²ˆì§¸ë¡œ <ec>¼ì¹˜í•˜<eb>Š” ê¸€<ec>ë§<8c> ë°”ê¿”<ec>•¼ <ed>•  ê¸€<ec>ë¡<9c> ë°”ê¾¸<ec>–´ì¤€<eb>‹¤.


{% highlight r %}
# 3ë²ˆì§¸<U+653C><U+3E63>˜ ê°’ì—<U+653C><U+3E63>„œ R<U+653C><U+3E63>„ Python<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë°”ê¾¸<U+653C><U+3E62>Š”<U+653C><U+3E62>° ì²«ë²ˆì§¸ë¡œ ì°¾ëŠ” R<U+653C><U+3E63>„ ë°”ê¾¼<U+653C><U+3E62>‹¤.
sub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer R Developer"
{% endhighlight %}

***

### gsub(): <ec>¼ì¹˜í•˜<eb>Š” ë¬¸ìë¥<bc> ëª¨ë‘ ë°”ê¾¸<eb>Š” <ed>•¨<ec>ˆ˜

`gsub('ì°¾ì•„<ec>•¼ <ed>•  ê¸€<ec>','ë°”ê¿”<ec>•¼ <ed>•  ê¸€<ec>','<ed>•´<eb>‹¹ <eb>°<ec>´<ed>„°')`ë¡<9c> <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. `sub()`ê³<bc> <eb>‹¤ë¥´ê²Œ <ec>¼ì¹˜í•˜<eb>Š” ë¬¸ìë¥<bc> ëª¨ë‘ ë°”ê¾¸<ec>–´ì¤€<eb>‹¤.


{% highlight r %}
# 3ë²ˆì§¸<U+653C><U+3E63>˜ ê°’ì—<U+653C><U+3E63>„œ R<U+653C><U+3E63>— <U+653C><U+3E63>¼ì¹˜í•˜<U+653C><U+3E62>Š” ë¬¸ìë¥<U+623C><U+3E63> <U+653C><U+3E63> „ë¶€  Python<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë°”ê¾¸<U+653C><U+3E63>–´ì¤€<U+653C><U+3E62>‹¤.
gsub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer Python Developer"
{% endhighlight %}



{% highlight r %}
# 0ë¶€<U+653C><U+3E64>„° 2<U+653C><U+3E63>‚¬<U+653C><U+3E63>´<U+653C><U+3E63>˜ <U+653C><U+3E63>ˆ«<U+653C><U+3E63>ë¥<U+623C><U+3E63> *ë¡<U+393C><U+3E63> ë°”ê¾¸<U+653C><U+3E63>–´ì¤€<U+653C><U+3E62>‹¤.
gsub('[0-2]','*','123450')
{% endhighlight %}



{% highlight text %}
## [1] "**345*"
{% endhighlight %}


***

## <ec>ˆ«<ec><ed>•¨<ec>ˆ˜

### round(): ë°˜ì˜¬ë¦<bc> <ed>•¨<ec>ˆ˜

option<ec>„ <ec>‚¬<ec>š©<ed>•˜<ec>—¬ ë°˜ì˜¬ë¦¼í•  <ec>œ„ì¹˜ë<a5><bc> <ec> •<ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
round(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# defaultê°’ì<U+393C><U+3E64>€ 0<U+653C><U+3E63>„<U+653C><U+3E63>„ <U+653C><U+3E63>•Œ <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
round(3.141592,0)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# ë°˜ì˜¬ë¦¼í•´<U+653C><U+3E63>„œ <U+653C><U+3E63>†Œ<U+653C><U+3E63>ˆ˜<U+653C><U+3E63>  3ë²ˆì§¸ <U+653C><U+3E63>ë¦¬ê¹Œì§€ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„
round(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3.142
{% endhighlight %}



{% highlight r %}
# ë°˜ì˜¬ë¦¼í•´<U+653C><U+3E63>„œ <U+653C><U+3E63> •<U+653C><U+3E63>ˆ˜ 1ë²ˆì§¸ <U+653C><U+3E63>ë¦¬ë§Œ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„
round(3.141592,-1)
{% endhighlight %}



{% highlight text %}
## [1] 0
{% endhighlight %}

***

### trunc(): ë²„ë¦¼ <ed>•¨<ec>ˆ˜

<ec>†Œ<ec>ˆ˜<ec> <ec>„ ëª¨ë‘ ë²„ë¦¬<eb>Š” <ed>•¨<ec>ˆ˜<ec>´<eb>‹¤.


{% highlight r %}
trunc(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>†Œ<U+653C><U+3E63>ˆ˜<U+653C><U+3E63>  3ë²ˆì§¸ <U+653C><U+3E63>ë¦¬ë°‘<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë²„ë¦¼<U+653C><U+3E63><U+393C><U+3E64>€ <U+653C><U+3E63>•ˆ<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.
trunc(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

***

### signif(): ë°˜ì˜¬ë¦<bc> <ed>•¨<ec>ˆ˜(<ec>œ„ì¹<98> <ec>ˆœ<ec>„œ)

`round()`<ed>•¨<ec>ˆ˜<ec><99>€ <eb>‹¤ë¥´ê²Œ <ec> œ<ec>¼ ì²«ë²ˆì§<b8> <ec>ë¦¬ê<b0>€ 1ë¡<9c> ê¸°ì<a4>€<ec>´ <eb>˜<ec>–´ <ed>•´<eb>‹¹ <ec>œ„ì¹˜ê°’<ec>— ë§ê²Œ ë°˜ì˜¬ë¦¼ì„ <ed>•´ì¤€<eb>‹¤.


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

### floor(): ê°™ê±°<eb>‚˜ <ec>‘<ec><9d>€ <ec> •<ec>ˆ˜ë¥<bc> ì¶”ì¶œ<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜


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

### mod(): ëª¨ë“œ<ed>•¨<ec>ˆ˜<eb>Š” <ec>—†<eb>‹¤.

<ec>‚¬<ec>š©<ed>•˜<eb> ¤ë©<b4> `%%`<ec><99>€ `%/%`ë¥<bc> <ec>‚¬<ec>š©<ed>•´<ec>•¼ <ed>•œ<eb>‹¤.


{% highlight r %}
# ëª«ë§Œ ì¶”ì¶œ<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63>„ <U+653C><U+3E63>‹œ
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚˜ë¨¸ìãå<U+3E37>€ë§<U+383C><U+3E63> ì¶”ì¶œ<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63>„ <U+653C><U+3E63>‹œ
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}

## <eb>‚ ì§œí•¨<ec>ˆ˜

### Sys.Date(): <ed>˜„<ec>¬ <ec>„œë²<84> <eb>‚ ì§<9c> <ed>‘œ<ec>‹œ


{% highlight r %}
Sys.Date()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08"
{% endhighlight %}

***

### Sys.time()/date(): <ec>„œë²„ì˜ <ed>˜„<ec>¬ <ec>ƒ<ec>„¸ <ec>‹œê°<84> <ed>‘œ<ec>‹œ


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

### as.Date(): ë¬¸ì<eb>‚ ì§œë<a5><bc> <eb>‚ ì§œí˜•<ec>œ¼ë¡<9c> ë³€<ed>™˜<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜

ì§€<ec>—­<ec>— ì¢…ì†<eb>˜ê¸<b0> <eb>•Œë¬¸ì— <eb>‹¤<ec>Œê³<bc> ê°™ì´ ê·<b8> ì§€<ec>—­<ec>˜ ë¬¸ì<ec>—´ <ed>‘œì¤€<ec>„œ<ec>‹<ec>— ë§ê²Œ <ec>¨ì£¼ì–´<ec>•¼ <ed>•œ<eb>‹¤.


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

<ed>‘œì¤€<ec>„œ<ec>‹<ec>— ë§ê²Œ <ec>“°ì§€ <ec>•Š<eb>Š”<eb>‹¤ë©<b4>, `format`<ec>„ <ec>¨ì£¼ì–´<ec>•¼ <ed>‘œì¤€<ec>„œ<ec>‹<ec>œ¼ë¡<9c> ë³€<ed>™˜<eb>œ<eb>‹¤.


{% highlight r %}
as.Date('20180725',format = '%Y%m%d')

as.Date('2018<U+653C><U+3E62>…„ 1<U+653C><U+3E63>›” 2<U+653C><U+3E63>¼',format = '%Y<U+653C><U+3E62>…„%m<U+653C><U+3E63>›”%d<U+653C><U+3E63>¼')
{% endhighlight %}



{% highlight text %}
## Error: invalid multibyte character in parser at line 3
{% endhighlight %}

#### <eb>‚ ì§<9c> Format

`format`<ec>˜ <ec>ƒ<ec>„¸ option<ec><9d>€ <eb>‹¤<ec>Œê³<bc> ê°™ë‹¤.

    `%Y`: <ec>„¸ê¸°ë<a5><bc> <ed>¬<ed>•¨<ed>•œ <eb>…„<eb>„(4<ec>ë¦<ac>)
    `%y`: <ec>„¸ê¸°ë<a5><bc> <ec>ƒ<eb>µ<ed>•œ <eb>…„<eb>„(2<ec>ë¦<ac>)
    `%m`: <ec>ˆ«<ec><eb>‹¬
    `%B`: ë¬¸ì<eb>‹¬
    `%b`: ë¬¸ì<eb>‹¬<ec>˜ <ec>•½<ec>–´
    `%d`: <ec>¼
    `%A`: ë¬¸ì<ec>š”<ec>¼
    `%a`: ë¬¸ì<ec>š”<ec>¼<ec>˜ <ec>•½<ec>–´
    `%u`: <ec>ˆ«<ec><ec>š”<ec>¼(1(<ec>›”)~7(<ec>¼))
    `%w`: <ec>ˆ«<ec><ec>š”<ec>¼(0(<ec>¼)~6(<ec>›”))
    `%H`: <ec>‹œ
    `%M`: ë¶<84>
    `%S`: ì´<88>
    `%z`: timezone <ec>‹œê°<84>
    `%Z`: timezone <ec>´ë¦<84>
    
`format`<ec>„ <ec>‚¬<ec>š©<ed>•˜<ec>—¬ <eb>‹¤<ec>Œê³<bc> ê°™ì´ <ed>•  <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
format(Sys.time(),'%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "18-10-08-¿ù¿äÀÏ 19:27:36"
{% endhighlight %}
    
***

### <eb>‚ ì§<9c> ê³„ì‚° ë°©ë²•


{% highlight r %}
# <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> + <U+653C><U+3E63>ˆ«<U+653C><U+3E63> = <U+653C><U+3E62>‚ ì§<U+393C><U+3E63>
Sys.Date() + 100
{% endhighlight %}



{% highlight text %}
## [1] "2019-01-16"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> - <U+653C><U+3E63>ˆ«<U+653C><U+3E63> = <U+653C><U+3E62>‚ ì§<U+393C><U+3E63>
Sys.Date() - 200
{% endhighlight %}



{% highlight text %}
## [1] "2018-03-22"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E64>Š¹<U+653C><U+3E63> • <U+653C><U+3E62>‚ ì§œëãå<U+3E35><U+623C><U+3E63> <U+653C><U+3E63>‚¬<U+653C><U+3E63>š©<U+653C><U+3E64>•˜<U+653C><U+3E63>—¬ <U+653C><U+3E62>”<U+653C><U+3E64>•  <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
as.Date('2018-01-01', format = '%Y-%m-%d') + 100
{% endhighlight %}



{% highlight text %}
## [1] "2018-04-11"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> - <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> = <U+653C><U+3E63>ˆ«<U+653C><U+3E63>
as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## Time difference of -182 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚ ì§œì˜ ì°¨ì´<U+653C><U+3E63>—<U+653C><U+3E63>„œ <U+653C><U+3E63>ˆ«<U+653C><U+3E63>ê°’ë§Œ ë³´ê³  <U+653C><U+3E63>‹¶<U+653C><U+3E63><U+393C><U+3E64>€ ê²½ìš°
as.numeric(as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] -182
{% endhighlight %}

***

### weekdays(): <ec>š”<ec>¼<ec>„ ì¶œë ¥<ed>•˜<eb>Š” <ed>•¨<ec>ˆ˜


{% highlight r %}
weekdays(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "¿ù¿äÀÏ"
{% endhighlight %}



{% highlight r %}
weekdays(as.Date('2000-01-01', format='%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "Åä¿äÀÏ"
{% endhighlight %}

***

### dfftime(): <eb>‘ <eb>‚ ì§œê°„<ec>˜ <ec>¼ <ec>ˆ˜ <ed>‘œ<ed>˜„


{% highlight r %}
difftime('2018-01-01', Sys.Date())
{% endhighlight %}



{% highlight text %}
## Time difference of -280.375 days
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>ˆ«<U+653C><U+3E63>ë§<U+383C><U+3E63> ì¶œë ¥<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63><U+393C><U+3E64>€ ê²½ìš°
as.numeric(difftime('2018-01-01', Sys.Date()))
{% endhighlight %}



{% highlight text %}
## [1] -280.375
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63> •<U+653C><U+3E63>ˆ˜ê°’ë§Œ ì¶œë ¥<U+653C><U+3E64>•˜ê³ãå<U+3E30> <U+653C><U+3E63>‹¶<U+653C><U+3E63><U+393C><U+3E64>€ ê²½ìš°
round(as.numeric(difftime('2018-01-01', Sys.Date())))
{% endhighlight %}



{% highlight text %}
## [1] -280
{% endhighlight %}

***

### as.difftime(): <ec>‹œê°„ì˜ ì°¨ì´


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

### quarters(): ë¶„ê¸° <ed>‘œ<ed>˜„

<ed>•´<eb>‹¹ <eb>‚ ì§œì˜ ë¶„ê¸° <ec> •ë³´ë<a5><bc> <ed>‘œ<ed>˜„<ed>•œ<eb>‹¤.


{% highlight r %}
quarters(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Q4"
{% endhighlight %}

***

### lubridate <ed>Œ¨<ed>‚¤ì§€: <eb>‚ ì§<9c> <ed>‘œ<ed>˜„ <ed>Œ¨<ed>‚¤ì§€

`lubridate()`<eb>Š” <eb>‚ ì§œë<a5><bc> <eb>‹¤ë£<b0> <eb>•Œ <ec>œ <ec>š©<ed>•œ <ed>Œ¨<ed>‚¤ì§€<eb>‹¤. <eb>‚ ì§œë<a5><bc> ì¶œë ¥<ed>•  <eb>•Œ format<ec>„ <ec>•ˆ<ec>¨<eb>„ <eb>˜<eb>Š” <ec>´<ec> <ec>´ <ec>ˆ<eb>‹¤. ë¨¼ì<a0>€ <ed>Œ¨<ed>‚¤ì§€ <ec>„¤ì¹˜ë<a5><bc> <ed>•œ <eb>‹¤<ec>Œ<ec>— loadë¥<bc> <ec>‹œì¼œì£¼<ec>–´<ec>•¼ <ed>•œ<eb>‹¤.


{% highlight r %}
library(lubridate)

# <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> ì¶œë ¥
# <U+653C><U+3E64>˜„<U+653C><U+3E63>¬ <U+653C><U+3E62>‚ ì§<U+393C><U+3E63>
now()
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>—°<U+653C><U+3E62>„ ì¶œë ¥ 
year(now()) # format(Sys.time(),'%Y')<U+653C><U+3E63><U+393C><U+3E39>€ ê°™ë‹¤.
{% endhighlight %}



{% highlight text %}
## [1] 2018
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‹¬ ì¶œë ¥
month(now())
{% endhighlight %}



{% highlight text %}
## [1] 10
{% endhighlight %}



{% highlight r %}
# factor<U+653C><U+3E64>˜•<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> <U+653C><U+3E62>˜<U+653C><U+3E63>–´<U+653C><U+3E63>ˆ<U+653C><U+3E63>Œ<U+653C><U+3E63>„ <U+653C><U+3E63>•Œ <U+653C><U+3E63>ˆ˜ <U+653C><U+3E63>ˆ<U+653C><U+3E62>‹¤.
month(now(), label = T)
{% endhighlight %}



{% highlight text %}
## [1] 10
## Levels: 1 < 2 < 3 < 4 < 5 < 6 < 7 < 8 < 9 < 10 < 11 < 12
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>¼ ì¶œë ¥
day(now())
{% endhighlight %}



{% highlight text %}
## [1] 8
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>š”<U+653C><U+3E63>¼ ì¶œë ¥
wday(now()) # format<U+653C><U+3E63>—<U+653C><U+3E63>„œ<U+653C><U+3E63>˜ %u, %w<U+653C><U+3E63><U+393C><U+3E39>€ <U+653C><U+3E62>‹¤ë¥´ë‹¤.
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 1) # <U+653C><U+3E63>›”<U+653C><U+3E63>š”<U+653C><U+3E63>¼ ê¸°ìãå<U+3E34>€<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ì¶œë ¥
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7) # <U+653C><U+3E63>¼<U+653C><U+3E63>š”<U+653C><U+3E63>¼ ê¸°ìãå<U+3E34>€<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ì¶œë ¥
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7, label = T) # level ì¶œë ¥
{% endhighlight %}



{% highlight text %}
## [1] ¿ù
## Levels: ÀÏ < ¿ù < È­ < ¼ö < ¸ñ < ±İ < Åä
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‚ ì§<U+393C><U+3E63> <U+653C><U+3E63>—°/ê°œì›” <U+653C><U+3E62>“±<U+653C><U+3E63>˜ <U+653C><U+3E63>ˆ˜ ì¶œë ¥
# <U+653C><U+3E63>—° <U+653C><U+3E63>ˆ˜ (<U+653C><U+3E63>˜¤<U+653C><U+3E62>¼<U+653C><U+3E64>´<U+653C><U+3E63>˜ to_yminterval()ê³<U+623C><U+3E63> ë¹„ìŠ·<U+653C><U+3E64>•¨)
years(10)
{% endhighlight %}



{% highlight text %}
## [1] "10y 0m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# ê°œì›” <U+653C><U+3E63>ˆ˜
months(10)
{% endhighlight %}



{% highlight text %}
## [1] "10m 0d 0H 0M 0S"
{% endhighlight %}



{% highlight r %}
# ì§€ê¸ˆë<U+623C><U+3E36>€<U+653C><U+3E64>„° 10<U+653C><U+3E62>…„ <U+653C><U+3E64>›„
now() + years(10)
{% endhighlight %}



{% highlight text %}
## [1] "2028-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# ì§€ê¸ˆë<U+623C><U+3E36>€<U+653C><U+3E64>„° 100ê°œì›” <U+653C><U+3E64>›„
now() + months(100)
{% endhighlight %}



{% highlight text %}
## [1] "2027-02-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# ì§€ê¸ˆë<U+623C><U+3E36>€<U+653C><U+3E64>„° 1000<U+653C><U+3E63>¼ <U+653C><U+3E63> „
now() - days(1000)
{% endhighlight %}



{% highlight text %}
## [1] "2016-01-12 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# ì§€ê¸ˆë<U+623C><U+3E36>€<U+653C><U+3E64>„° 1<U+653C><U+3E62>…„ 1ê°œì›” 1<U+653C><U+3E63>¼ 1<U+653C><U+3E63>‹œê°<U+383C><U+3E34> 1ë¶<U+383C><U+3E34> 1ì´<U+383C><U+3E38> <U+653C><U+3E64>›„
now() + years(1) + months(1) + days(1) + hours(1) + minutes(1) + seconds(1)
{% endhighlight %}



{% highlight text %}
## [1] "2019-11-09 20:28:37 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>‹œê°<U+383C><U+3E34> ê³„ì‚°
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

<ec>—°<eb>„/<eb>‹¬ <eb>“±<ec>„ ë°”ê¾¸<ec>–´<ec>„œ <eb>‹¤ë£¨ê¸° <ec>›<ed>•˜<eb>‹¤ë©<b4> <eb>‹¤<ec>Œê³<bc> ê°™ì´ ë³€<ec>ˆ˜<ec>—<eb>‹¤ê°€ <eb>‚ ì§œë<a5><bc> <eb>„£ê³<a0> <eb>‚ <ec>„ ë°”ê¿”ì¤<84> <ec>ˆ˜ <ec>ˆ<eb>‹¤.


{% highlight r %}
date <- now()
# <U+653C><U+3E63>—°<U+653C><U+3E62>„ <U+653C><U+3E63>ˆ˜<U+653C><U+3E63> •
year(date) <- 2017
date
{% endhighlight %}



{% highlight text %}
## [1] "2017-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>‹¬ <U+653C><U+3E63>ˆ˜<U+653C><U+3E63> •
month(date) <- 1 

# <U+653C><U+3E63>¼ <U+653C><U+3E63>ˆ˜<U+653C><U+3E63> •
day(date) <- 1

# <U+653C><U+3E63>‹œê°<U+383C><U+3E34> <U+653C><U+3E63>ˆ˜<U+653C><U+3E63> •
hour(date) <- 00
minute(date) <- 00
second(date) <- 00

format(date, '%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "17-01-01-ÀÏ¿äÀÏ 00:00:00"
{% endhighlight %}

***

### POSIX Type

POSIX(Portable Opearating System Interface)<eb>Š” UNIX ê°<84> <ec>†Œ<ed>†µ ê°€<eb>Š¥<ed>•œ <ed>”„ë¡œê·¸<eb>¨ <ec>¸<ed>„°<ed>˜<ec>´<ec>Š¤<ec>˜ ê·œì•½<ec>´<eb>‹¤. R<ec>—<ec>„œ<eb>Š” <eb>‚ ì§<9c> <ec>‹œê°<84> <eb>°<ec>´<ed>„°ë¥<bc> ì²˜ë¦¬<ed>•  <ec>ˆ˜ <ec>ˆ<eb>„ë¡<9d> `POSIXct`,`POSIXt(POSIXlt)` <ed>´<eb>˜<ec>Š¤ë¥<bc> <ec>‚¬<ec>š©<ed>•œ<eb>‹¤. POSIX<ed><83>€<ec>…<ec><9d>€ <eb>‹¤<ec>Œ 2ê°€ì§€<ec>´<eb>‹¤.

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

classë¡<9c> `POSIX`<ed><83>€<ec>…ê³<bc> `DATE`<ed><83>€<ec>…<ec>„ <ec>•Œ <ec>ˆ˜ <ec>ˆ<eb>‹¤. `POSIX` <ed><83>€<ec>…<ec>„ <ec><ec>„¸<ed>ˆ <ec>•Œ<ec>•„ë³´ì.


{% highlight r %}
# <U+653C><U+3E63>‹œê°„ì„ numeric<U+653C><U+3E64>˜•<U+653C><U+3E63>‹<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> <U+653C><U+3E64><U+393C><U+3E32>€<U+653C><U+3E63>–´<U+653C><U+3E63>„œ <U+653C><U+3E64>‘œ<U+653C><U+3E64>˜„<U+653C><U+3E62>œ<U+653C><U+3E62>‹¤.
as.numeric(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] 1538994457
{% endhighlight %}



{% highlight r %}
# POSIXlt<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> <U+653C><U+3E64>˜• ë³€<U+653C><U+3E64>™˜
time <- as.POSIXlt(Sys.time())
time
{% endhighlight %}



{% highlight text %}
## [1] "2018-10-08 19:27:36 KST"
{% endhighlight %}



{% highlight r %}
# POSIX<U+653C><U+3E63>˜ list<U+653C><U+3E64><U+383C><U+3E33>€<U+653C><U+3E63>… <U+653C><U+3E64>˜•<U+653C><U+3E63>‹<U+653C><U+3E63>œ¼ë¡<U+393C><U+3E63> ë³´ì—¬ì¤€<U+653C><U+3E62>‹¤.
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

`POSIX`<ec>˜ <ec>ƒ<ec>„¸ê°’ì<9d>€ <eb>‹¤<ec>Œê³<bc> ê°™ë‹¤.
    

    `mday`: ê·<b8> <eb>‹¬<ec>˜ <ec>¼
    `mon`: 1<ec>›”<ec>„ 0<ec>œ¼ë¡<9c> <ec>‹œ<ec>‘<ed>•˜<eb>Š” <eb>‹¬
    `year`: 1900<eb>…„<ec>„ 0<ec>œ¼ë¡<9c> <ec>‹œ<ec>‘<ed>•˜<eb>Š” <eb>…„
    `wday`: <ec>¼<ec>š”<ec>¼<ec>„ 0<ec>œ¼ë¡<9c> <ec>‹œ<ec>‘<ed>•˜<eb>Š” <ec>¼
    `yday`: 1<ec>›” 1<ec>¼<ec>„ 0<ec>œ¼ë¡<9c> <ec>‹œ<ec>‘<ed>•˜<eb>Š” <ec>¼
    `isdst`: <ec>„œë¨¸í<83>€<ec>„
    `zone`: timezone <ec>´ë¦<84>
    `gmtoff`: timezone<ec>˜ <ec>‹œ(ì´ˆë‹¨<ec>œ„ë¡<9c>)


#### strptime(): POSIX<ed><83>€<ec>…<ec>œ¼ë¡<9c> <ed>˜•ë³€<ed>™˜

`strptime()`ë¥<bc> <ec>‚¬<ec>š©<ed>•˜ë©<b4> `POSIX`<ed><83>€<ec>…<ec>œ¼ë¡<9c> <ed>˜•<ec>„ ë³€<ed>™˜ <ec>‹œ<ed>‚¬ <ec>ˆ˜ <ec>ˆ<eb>‹¤.


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
## POSIX<U+653C><U+3E64>˜•<U+653C><U+3E64>ƒœë¡œì˜ <U+653C><U+3E64>˜•ë³€<U+653C><U+3E64>™˜
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
