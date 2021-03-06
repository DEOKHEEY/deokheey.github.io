---
layout: post
title: "[R] Deduplication, Sort"
date: "2018-08-01"
excerpt: "μ€λ³΅<ec> <ec> κ±°νκ³<a0> <ec> <eb> ¬<ec> <ec>μΌλ³΄<ec>"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories: R
tag: [R, deduplication, sort]
---

## Deduplication

### unique(): μ€λ³΅<ec> κ±<b0>

`unique()`λ₯<bc> <ec>¬<ec>©<ed><ec>¬ μ€λ³΅<eb> κ°μ <ec> κ±°ν<ec>¬ <ed><ed><ed>  <ec> <ec><eb>€.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

unique(x)
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10 NA  1 11
{% endhighlight %}

NAκ°μ΄ μΆλ ₯<eb><eb>€. NAκ°μ΄ μΆλ ₯<eb>μ§ <ec>κΈ<b8> <ec><ed><eb>€λ©<b4> `na.omit`<ec> <ec>¬<ec>©<ed><eb>€.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

na.omit(unique(x))
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10  1 11
## attr(,"na.action")
## [1] 9
## attr(,"class")
## [1] "omit"
{% endhighlight %}

κΉλ<ed>κ²<8c> <ec>°κ³<a0> <ec>Ά<eb>€λ©<b4> `as.integer()`λ₯<bc> <ec>¬<ec>©<ed><eb>€.


{% highlight r %}
x <- c(3,2,6,4,8,15,6,3,5,10,NA,1,11,NA,15,11,6)

as.integer(na.omit(unique(x)))
{% endhighlight %}



{% highlight text %}
##  [1]  3  2  6  4  8 15  5 10  1 11
{% endhighlight %}

***

## Sort

### sort(): <ec> <eb> ¬<ed>΄μ£Όλ <ed>¨<ec>


{% highlight r %}
x <- c(3,2,4,8,6,5,10,NA,1,11,NA,15)

# NAκ°μ<U+393C><U+3E64> <U+653C><U+3E63> <U+653C><U+3E63>Έ<U+653C><U+3E62>κ³γε<U+3E30> μΆλ ₯<U+653C><U+3E62><U+653C><U+3E62>€.
sort(x)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>€λ¦μ°¨<U+653C><U+3E63>(κΈ°λ³Έκ°<U+393C><U+3E32>)
sort(x, decreasing = FALSE)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>΄λ¦Όμ°¨<U+653C><U+3E63>
sort(x, decreasing = TRUE)
{% endhighlight %}



{% highlight text %}
##  [1] 15 11 10  8  6  5  4  3  2  1
{% endhighlight %}



{% highlight r %}
# NA μΆλ ₯ <U+653C><U+3E63><U+653C><U+3E64>¨(κΈ°λ³Έκ°<U+393C><U+3E32>)
sort(x, decreasing = FALSE, na.last = NA)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# NAλ₯<U+623C><U+3E63> <U+653C><U+3E62><U+653C><U+3E63><U+653C><U+3E62>€κ° μΆλ ₯
sort(x, decreasing = FALSE, na.last = TRUE)
{% endhighlight %}



{% highlight text %}
##  [1]  1  2  3  4  5  6  8 10 11 15 NA NA
{% endhighlight %}



{% highlight r %}
# NAλ₯<U+623C><U+3E63> μ²μ<U+653C><U+3E63><U+653C><U+3E62>€κ° μΆλ ₯
sort(x, decreasing = FALSE, na.last = FALSE)
{% endhighlight %}



{% highlight text %}
##  [1] NA NA  1  2  3  4  5  6  8 10 11 15
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>΄λ¦Όμ°¨<U+653C><U+3E63><U+653C><U+3E63> rev()λ‘<U+393C><U+3E63> <U+653C><U+3E64><U+653C><U+3E64> κ°<U+653C><U+3E62>₯
rev(sort(x))
{% endhighlight %}



{% highlight text %}
##  [1] 15 11 10  8  6  5  4  3  2  1
{% endhighlight %}


***
  
### order(): <ec> <eb> ¬<ec> <ec><ec>Έ<ec> λ°ν
  
<ec> <eb> ¬<ec> <ec>μΉ<98>(index) <ec> λ³΄λ<a5><bc> λ°ν<ed>  <eb> <ec>¬<ec>©<ed><eb>€.


{% highlight r %}
x <- c(30,50,10,40,20,NA)

sort(x)
{% endhighlight %}



{% highlight text %}
## [1] 10 20 30 40 50
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63> <U+653C><U+3E62> ¬<U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63>Έ<U+653C><U+3E63> λ°ν
order(x) # 10<U+653C><U+3E63>΄ 3λ²<U+383C><U+3E38> index<U+653C><U+3E63>, 20λ²μ<U+393C><U+3E64> 5λ²<U+383C><U+3E38> index<U+653C><U+3E63>... <U+653C><U+3E63><U+653C><U+3E62>€κ³γε<U+3E30> <U+653C><U+3E64>΄<U+653C><U+3E63><U+653C><U+3E64>λ©<U+623C><U+3E34> <U+653C><U+3E62><U+653C><U+3E62>€.
{% endhighlight %}



{% highlight text %}
## [1] 3 5 1 4 2 6
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>μΉ<U+393C><U+3E38> <U+653C><U+3E63> λ³΄λ‘ μΆλ ₯
x[order(x)] # SORT κΈ°λ₯
{% endhighlight %}



{% highlight text %}
## [1] 10 20 30 40 50 NA
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>μΉμ λ³΄μ NA<U+653C><U+3E63> λ³΄λγε<U+3E35><U+623C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E64>¨ 
x[order(x, decreasing = TRUE, na.last = NA)]
{% endhighlight %}



{% highlight text %}
## [1] 50 40 30 20 10
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>μΉμ λ³΄μ NAλ₯<U+623C><U+3E63> λ§μγε<U+3E37>λ§μ <U+653C><U+3E64><U+653C><U+3E63><U+653C><U+3E64><U+653C><U+3E63>¬ μΆλ ₯ (κΈ°λ³Έκ°<U+393C><U+3E32>)
x[order(x, decreasing = TRUE, na.last = TRUE)]
{% endhighlight %}



{% highlight text %}
## [1] 50 40 30 20 10 NA
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>μΉμ λ³΄μ NAλ₯<U+623C><U+3E63> μ²μ<U+653C><U+3E63> <U+653C><U+3E64><U+653C><U+3E63><U+653C><U+3E64><U+653C><U+3E63>¬ μΆλ ₯
x[order(x, decreasing = TRUE, na.last = FALSE)]
{% endhighlight %}



{% highlight text %}
## [1] NA 50 40 30 20 10
{% endhighlight %}

***
  
### doBy <ed>¨<ed>€μ§: <eb>°<ec>΄<ed>° <ed><eb> <ec><ec> <ec> <eb> ¬


{% highlight r %}
# emp table road
setwd("C:/data")
emp <- read.csv('emp.csv',stringsAsFactors = F)

# doBy package road
library(doBy)

# SALARYλ₯<U+623C><U+3E63> κΈ°μγε<U+3E34><U+653C><U+3E63>Όλ‘<U+393C><U+3E63> <U+653C><U+3E63>€λ¦μ°¨<U+653C><U+3E63> <U+653C><U+3E63> <U+653C><U+3E62> ¬
orderBy(~SALARY,emp[,c("LAST_NAME","SALARY")])
{% endhighlight %}



{% highlight text %}
##       LAST_NAME SALARY
## 42        Olson   2100
## 38       Markle   2200
## 46   Philtanker   2200
## 37       Landry   2400
## 45          Gee   2400
## 29   Colmenares   2500
## 41       Marlow   2500
## 50        Patel   2500
## 54       Vargas   2500
## 92     Sullivan   2500
## 101     Perkins   2500
## 1      OConnell   2600
## 2         Grant   2600
## 28       Himuro   2600
## 53        Matos   2600
## 36  Mikkilineni   2700
## 49          Seo   2700
## 27       Tobias   2800
## 40     Atkinson   2800
## 93        Geoni   2800
## 105       Jones   2800
## 26        Baida   2900
## 44       Rogers   2900
## 100       Gates   2900
## 97       Cabrio   3000
## 107      Feeney   3000
## 25         Khoo   3100
## 52       Davies   3100
## 91       Fleaur   3100
## 106       Walsh   3100
## 35        Nayer   3200
## 48       Stiles   3200
## 90       Taylor   3200
## 104      McCain   3200
## 39       Bissot   3300
## 43       Mallin   3300
## 96    Dellinger   3400
## 51         Rajs   3500
## 47       Ladwig   3600
## 99        Dilly   3600
## 98        Chung   3800
## 103     Everett   3900
## 102        Bell   4000
## 95         Bull   4100
## 17      Lorentz   4200
## 94     Sarchand   4200
## 3        Whalen   4400
## 15       Austin   4800
## 16    Pataballa   4800
## 34      Mourgos   5800
## 5           Fay   6000
## 14        Ernst   6000
## 83        Kumar   6100
## 77        Banda   6200
## 89      Johnson   6200
## 76         Ande   6400
## 6        Mavris   6500
## 33      Vollman   6500
## 75          Lee   6800
## 23         Popp   6900
## 65      Tuvault   7000
## 71       Sewall   7000
## 88        Grant   7000
## 74      Marvins   7200
## 82        Bates   7300
## 81        Smith   7400
## 64    Cambrault   7500
## 70        Doran   7500
## 21      Sciarra   7700
## 22        Urman   7800
## 32     Kaufling   7900
## 30        Weiss   8000
## 63        Olsen   8000
## 69        Smith   8000
## 20         Chen   8200
## 31        Fripp   8200
## 9         Gietz   8300
## 87   Livingston   8400
## 86       Taylor   8600
## 85       Hutton   8800
## 13       Hunold   9000
## 19       Faviet   9000
## 62         Hall   9000
## 68       McEwen   9000
## 61    Bernstein   9500
## 67        Sully   9500
## 73       Greene   9500
## 80          Fox   9600
## 7          Baer  10000
## 60       Tucker  10000
## 66         King  10000
## 79        Bloom  10000
## 59      Zlotkey  10500
## 72      Vishney  10500
## 24     Raphaely  11000
## 58    Cambrault  11000
## 84         Abel  11000
## 78         Ozer  11500
## 57    Errazuriz  12000
## 8       Higgins  12008
## 18    Greenberg  12008
## 4     Hartstein  13000
## 56     Partners  13500
## 55      Russell  14000
## 11      Kochhar  17000
## 12      De Haan  17000
## 10         King  29040
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>΄λ¦Όμ°¨<U+653C><U+3E63>(μ»¬λΌ <U+653C><U+3E63><U+653C><U+3E63> -λ₯<U+623C><U+3E63> <U+653C><U+3E63>΄<U+653C><U+3E63>©)
orderBy(~-SALARY,emp[,c("LAST_NAME","SALARY")])
{% endhighlight %}



{% highlight text %}
##       LAST_NAME SALARY
## 10         King  29040
## 11      Kochhar  17000
## 12      De Haan  17000
## 55      Russell  14000
## 56     Partners  13500
## 4     Hartstein  13000
## 8       Higgins  12008
## 18    Greenberg  12008
## 57    Errazuriz  12000
## 78         Ozer  11500
## 24     Raphaely  11000
## 58    Cambrault  11000
## 84         Abel  11000
## 59      Zlotkey  10500
## 72      Vishney  10500
## 7          Baer  10000
## 60       Tucker  10000
## 66         King  10000
## 79        Bloom  10000
## 80          Fox   9600
## 61    Bernstein   9500
## 67        Sully   9500
## 73       Greene   9500
## 13       Hunold   9000
## 19       Faviet   9000
## 62         Hall   9000
## 68       McEwen   9000
## 85       Hutton   8800
## 86       Taylor   8600
## 87   Livingston   8400
## 9         Gietz   8300
## 20         Chen   8200
## 31        Fripp   8200
## 30        Weiss   8000
## 63        Olsen   8000
## 69        Smith   8000
## 32     Kaufling   7900
## 22        Urman   7800
## 21      Sciarra   7700
## 64    Cambrault   7500
## 70        Doran   7500
## 81        Smith   7400
## 82        Bates   7300
## 74      Marvins   7200
## 65      Tuvault   7000
## 71       Sewall   7000
## 88        Grant   7000
## 23         Popp   6900
## 75          Lee   6800
## 6        Mavris   6500
## 33      Vollman   6500
## 76         Ande   6400
## 77        Banda   6200
## 89      Johnson   6200
## 83        Kumar   6100
## 5           Fay   6000
## 14        Ernst   6000
## 34      Mourgos   5800
## 15       Austin   4800
## 16    Pataballa   4800
## 3        Whalen   4400
## 17      Lorentz   4200
## 94     Sarchand   4200
## 95         Bull   4100
## 102        Bell   4000
## 103     Everett   3900
## 98        Chung   3800
## 47       Ladwig   3600
## 99        Dilly   3600
## 51         Rajs   3500
## 96    Dellinger   3400
## 39       Bissot   3300
## 43       Mallin   3300
## 35        Nayer   3200
## 48       Stiles   3200
## 90       Taylor   3200
## 104      McCain   3200
## 25         Khoo   3100
## 52       Davies   3100
## 91       Fleaur   3100
## 106       Walsh   3100
## 97       Cabrio   3000
## 107      Feeney   3000
## 26        Baida   2900
## 44       Rogers   2900
## 100       Gates   2900
## 27       Tobias   2800
## 40     Atkinson   2800
## 93        Geoni   2800
## 105       Jones   2800
## 36  Mikkilineni   2700
## 49          Seo   2700
## 1      OConnell   2600
## 2         Grant   2600
## 28       Himuro   2600
## 53        Matos   2600
## 29   Colmenares   2500
## 41       Marlow   2500
## 50        Patel   2500
## 54       Vargas   2500
## 92     Sullivan   2500
## 101     Perkins   2500
## 37       Landry   2400
## 45          Gee   2400
## 38       Markle   2200
## 46   Philtanker   2200
## 42        Olson   2100
{% endhighlight %}

<ec>¬<eb>¬ κ°μ μ»¬λΌ<ec>Όλ‘<9c> <ec> <eb> ¬<ec> <ed><eb> κ²½μ°κ° <ec><eb>€. κ·<b8> <eb><eb> `~`<eb>€<ec> μ»¬λΌ<eb>Όλ¦<ac> <ec>°κ²°ν<eb>, <ec>€λ¦μ°¨<ec>(+)<ec>Έμ§ <eb>΄λ¦Όμ°¨<ec><ec>Έμ§(-)λ₯<bc> λͺμ<ed>΄μ£Όμ΄<ec>Ό <ed><eb>€.


{% highlight r %}
# <U+653C><U+3E63>€λ¦μ°¨<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63>(+λ₯<U+623C><U+3E63> <U+653C><U+3E63>΄<U+653C><U+3E63>©)
orderBy(~DEPARTMENT_ID+SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
##       LAST_NAME SALARY DEPARTMENT_ID
## 3        Whalen   4400            10
## 5           Fay   6000            20
## 4     Hartstein  13000            20
## 29   Colmenares   2500            30
## 28       Himuro   2600            30
## 27       Tobias   2800            30
## 26        Baida   2900            30
## 25         Khoo   3100            30
## 24     Raphaely  11000            30
## 6        Mavris   6500            40
## 42        Olson   2100            50
## 38       Markle   2200            50
## 46   Philtanker   2200            50
## 37       Landry   2400            50
## 45          Gee   2400            50
## 41       Marlow   2500            50
## 50        Patel   2500            50
## 54       Vargas   2500            50
## 92     Sullivan   2500            50
## 101     Perkins   2500            50
## 1      OConnell   2600            50
## 2         Grant   2600            50
## 53        Matos   2600            50
## 36  Mikkilineni   2700            50
## 49          Seo   2700            50
## 40     Atkinson   2800            50
## 93        Geoni   2800            50
## 105       Jones   2800            50
## 44       Rogers   2900            50
## 100       Gates   2900            50
## 97       Cabrio   3000            50
## 107      Feeney   3000            50
## 52       Davies   3100            50
## 91       Fleaur   3100            50
## 106       Walsh   3100            50
## 35        Nayer   3200            50
## 48       Stiles   3200            50
## 90       Taylor   3200            50
## 104      McCain   3200            50
## 39       Bissot   3300            50
## 43       Mallin   3300            50
## 96    Dellinger   3400            50
## 51         Rajs   3500            50
## 47       Ladwig   3600            50
## 99        Dilly   3600            50
## 98        Chung   3800            50
## 103     Everett   3900            50
## 102        Bell   4000            50
## 95         Bull   4100            50
## 94     Sarchand   4200            50
## 34      Mourgos   5800            50
## 33      Vollman   6500            50
## 32     Kaufling   7900            50
## 30        Weiss   8000            50
## 31        Fripp   8200            50
## 17      Lorentz   4200            60
## 15       Austin   4800            60
## 16    Pataballa   4800            60
## 14        Ernst   6000            60
## 13       Hunold   9000            60
## 7          Baer  10000            70
## 83        Kumar   6100            80
## 77        Banda   6200            80
## 89      Johnson   6200            80
## 76         Ande   6400            80
## 75          Lee   6800            80
## 65      Tuvault   7000            80
## 71       Sewall   7000            80
## 74      Marvins   7200            80
## 82        Bates   7300            80
## 81        Smith   7400            80
## 64    Cambrault   7500            80
## 70        Doran   7500            80
## 63        Olsen   8000            80
## 69        Smith   8000            80
## 87   Livingston   8400            80
## 86       Taylor   8600            80
## 85       Hutton   8800            80
## 62         Hall   9000            80
## 68       McEwen   9000            80
## 61    Bernstein   9500            80
## 67        Sully   9500            80
## 73       Greene   9500            80
## 80          Fox   9600            80
## 60       Tucker  10000            80
## 66         King  10000            80
## 79        Bloom  10000            80
## 59      Zlotkey  10500            80
## 72      Vishney  10500            80
## 58    Cambrault  11000            80
## 84         Abel  11000            80
## 78         Ozer  11500            80
## 57    Errazuriz  12000            80
## 56     Partners  13500            80
## 55      Russell  14000            80
## 11      Kochhar  17000            90
## 12      De Haan  17000            90
## 10         King  29040            90
## 23         Popp   6900           100
## 21      Sciarra   7700           100
## 22        Urman   7800           100
## 20         Chen   8200           100
## 19       Faviet   9000           100
## 18    Greenberg  12008           100
## 9         Gietz   8300           110
## 8       Higgins  12008           110
## 88        Grant   7000            NA
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E62>΄λ¦Όμ°¨<U+653C><U+3E63><U+653C><U+3E63> <U+653C><U+3E63><U+653C><U+3E63>(-λ₯<U+623C><U+3E63> <U+653C><U+3E63>΄<U+653C><U+3E63>©)
orderBy(~-DEPARTMENT_ID-SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
##       LAST_NAME SALARY DEPARTMENT_ID
## 8       Higgins  12008           110
## 9         Gietz   8300           110
## 18    Greenberg  12008           100
## 19       Faviet   9000           100
## 20         Chen   8200           100
## 22        Urman   7800           100
## 21      Sciarra   7700           100
## 23         Popp   6900           100
## 10         King  29040            90
## 11      Kochhar  17000            90
## 12      De Haan  17000            90
## 55      Russell  14000            80
## 56     Partners  13500            80
## 57    Errazuriz  12000            80
## 78         Ozer  11500            80
## 58    Cambrault  11000            80
## 84         Abel  11000            80
## 59      Zlotkey  10500            80
## 72      Vishney  10500            80
## 60       Tucker  10000            80
## 66         King  10000            80
## 79        Bloom  10000            80
## 80          Fox   9600            80
## 61    Bernstein   9500            80
## 67        Sully   9500            80
## 73       Greene   9500            80
## 62         Hall   9000            80
## 68       McEwen   9000            80
## 85       Hutton   8800            80
## 86       Taylor   8600            80
## 87   Livingston   8400            80
## 63        Olsen   8000            80
## 69        Smith   8000            80
## 64    Cambrault   7500            80
## 70        Doran   7500            80
## 81        Smith   7400            80
## 82        Bates   7300            80
## 74      Marvins   7200            80
## 65      Tuvault   7000            80
## 71       Sewall   7000            80
## 75          Lee   6800            80
## 76         Ande   6400            80
## 77        Banda   6200            80
## 89      Johnson   6200            80
## 83        Kumar   6100            80
## 7          Baer  10000            70
## 13       Hunold   9000            60
## 14        Ernst   6000            60
## 15       Austin   4800            60
## 16    Pataballa   4800            60
## 17      Lorentz   4200            60
## 31        Fripp   8200            50
## 30        Weiss   8000            50
## 32     Kaufling   7900            50
## 33      Vollman   6500            50
## 34      Mourgos   5800            50
## 94     Sarchand   4200            50
## 95         Bull   4100            50
## 102        Bell   4000            50
## 103     Everett   3900            50
## 98        Chung   3800            50
## 47       Ladwig   3600            50
## 99        Dilly   3600            50
## 51         Rajs   3500            50
## 96    Dellinger   3400            50
## 39       Bissot   3300            50
## 43       Mallin   3300            50
## 35        Nayer   3200            50
## 48       Stiles   3200            50
## 90       Taylor   3200            50
## 104      McCain   3200            50
## 52       Davies   3100            50
## 91       Fleaur   3100            50
## 106       Walsh   3100            50
## 97       Cabrio   3000            50
## 107      Feeney   3000            50
## 44       Rogers   2900            50
## 100       Gates   2900            50
## 40     Atkinson   2800            50
## 93        Geoni   2800            50
## 105       Jones   2800            50
## 36  Mikkilineni   2700            50
## 49          Seo   2700            50
## 1      OConnell   2600            50
## 2         Grant   2600            50
## 53        Matos   2600            50
## 41       Marlow   2500            50
## 50        Patel   2500            50
## 54       Vargas   2500            50
## 92     Sullivan   2500            50
## 101     Perkins   2500            50
## 37       Landry   2400            50
## 45          Gee   2400            50
## 38       Markle   2200            50
## 46   Philtanker   2200            50
## 42        Olson   2100            50
## 6        Mavris   6500            40
## 24     Raphaely  11000            30
## 25         Khoo   3100            30
## 26        Baida   2900            30
## 27       Tobias   2800            30
## 28       Himuro   2600            30
## 29   Colmenares   2500            30
## 4     Hartstein  13000            20
## 5           Fay   6000            20
## 3        Whalen   4400            10
## 88        Grant   7000            NA
{% endhighlight %}



{% highlight r %}
# <U+653C><U+3E63>€λ¦μ°¨<U+653C><U+3E63>κ³<U+623C><U+3E63> <U+653C><U+3E62>΄λ¦Όμ°¨<U+653C><U+3E63> <U+653C><U+3E64>Ό<U+653C><U+3E63>©(μ²γε<U+3E62> μ»¬λΌ<U+653C><U+3E63> + <U+653C><U+3E63><U+653C><U+3E62>΅ κ°<U+653C><U+3E62>₯)
orderBy(~DEPARTMENT_ID-SALARY,emp[,c("LAST_NAME","SALARY","DEPARTMENT_ID")])
{% endhighlight %}



{% highlight text %}
##       LAST_NAME SALARY DEPARTMENT_ID
## 3        Whalen   4400            10
## 4     Hartstein  13000            20
## 5           Fay   6000            20
## 24     Raphaely  11000            30
## 25         Khoo   3100            30
## 26        Baida   2900            30
## 27       Tobias   2800            30
## 28       Himuro   2600            30
## 29   Colmenares   2500            30
## 6        Mavris   6500            40
## 31        Fripp   8200            50
## 30        Weiss   8000            50
## 32     Kaufling   7900            50
## 33      Vollman   6500            50
## 34      Mourgos   5800            50
## 94     Sarchand   4200            50
## 95         Bull   4100            50
## 102        Bell   4000            50
## 103     Everett   3900            50
## 98        Chung   3800            50
## 47       Ladwig   3600            50
## 99        Dilly   3600            50
## 51         Rajs   3500            50
## 96    Dellinger   3400            50
## 39       Bissot   3300            50
## 43       Mallin   3300            50
## 35        Nayer   3200            50
## 48       Stiles   3200            50
## 90       Taylor   3200            50
## 104      McCain   3200            50
## 52       Davies   3100            50
## 91       Fleaur   3100            50
## 106       Walsh   3100            50
## 97       Cabrio   3000            50
## 107      Feeney   3000            50
## 44       Rogers   2900            50
## 100       Gates   2900            50
## 40     Atkinson   2800            50
## 93        Geoni   2800            50
## 105       Jones   2800            50
## 36  Mikkilineni   2700            50
## 49          Seo   2700            50
## 1      OConnell   2600            50
## 2         Grant   2600            50
## 53        Matos   2600            50
## 41       Marlow   2500            50
## 50        Patel   2500            50
## 54       Vargas   2500            50
## 92     Sullivan   2500            50
## 101     Perkins   2500            50
## 37       Landry   2400            50
## 45          Gee   2400            50
## 38       Markle   2200            50
## 46   Philtanker   2200            50
## 42        Olson   2100            50
## 13       Hunold   9000            60
## 14        Ernst   6000            60
## 15       Austin   4800            60
## 16    Pataballa   4800            60
## 17      Lorentz   4200            60
## 7          Baer  10000            70
## 55      Russell  14000            80
## 56     Partners  13500            80
## 57    Errazuriz  12000            80
## 78         Ozer  11500            80
## 58    Cambrault  11000            80
## 84         Abel  11000            80
## 59      Zlotkey  10500            80
## 72      Vishney  10500            80
## 60       Tucker  10000            80
## 66         King  10000            80
## 79        Bloom  10000            80
## 80          Fox   9600            80
## 61    Bernstein   9500            80
## 67        Sully   9500            80
## 73       Greene   9500            80
## 62         Hall   9000            80
## 68       McEwen   9000            80
## 85       Hutton   8800            80
## 86       Taylor   8600            80
## 87   Livingston   8400            80
## 63        Olsen   8000            80
## 69        Smith   8000            80
## 64    Cambrault   7500            80
## 70        Doran   7500            80
## 81        Smith   7400            80
## 82        Bates   7300            80
## 74      Marvins   7200            80
## 65      Tuvault   7000            80
## 71       Sewall   7000            80
## 75          Lee   6800            80
## 76         Ande   6400            80
## 77        Banda   6200            80
## 89      Johnson   6200            80
## 83        Kumar   6100            80
## 10         King  29040            90
## 11      Kochhar  17000            90
## 12      De Haan  17000            90
## 18    Greenberg  12008           100
## 19       Faviet   9000           100
## 20         Chen   8200           100
## 22        Urman   7800           100
## 21      Sciarra   7700           100
## 23         Popp   6900           100
## 8       Higgins  12008           110
## 9         Gietz   8300           110
## 88        Grant   7000            NA
{% endhighlight %}

