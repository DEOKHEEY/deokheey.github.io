---
layout: post
title: "INTRODUCTION - R"
date: "2018-07-29"
excerpt: "R이란"
output: 
  github_document:
    toc: true
    toc_depth: 3
categories: r
tag: r
comments: true
---

# R

뉴질랜드 AUKLAND 대학의 Ross Lhaka, Robert Clifford Gentleman가 1995년에 개발한 소프트웨어이고 데이터 분석을 위한 통계 및 그래픽스를 지원하는 무료 소프트웨어이다.

<br>

## R을 사용해야 하는 이유

1. R은 무료소프트웨어이다.
2. 데이터를 분석을 위해서 가장 많이 쓰는 통계 플랫폼이다.
3. 복잡한 데이터를 다양한 그래프로 표현할 수가 있다.
4. 분석을 위한 데이터를 쉽게 저장하고 조작할 수 있다.
5. 누구든지 유용한 패키지를 생성해서 공유할 수 있고 새로운 기능에 대한 전달이 빠르다.
6. 어떠한 OS에서도 설치가 가능하다. 

<br>

## R 설치

https://www.r-project.org/
https://www.rstudio.com/

***

<br>

## R의 기본 변수

- 변수 이름은 알파벳, 숫자, _, .(마침표) 사용할 수 있다.
- 변수 이림의 첫글자는 알파벳 또는 .(마침표)로 시작할 수 있다.
- .(마침표)로 시작 할 경우에는 바로 뒤에 숫자를 입력할 수 있다.
    - 변수 이름으로 가능한 예: `a`, `i`, `x2`, `.y`
    - 변수이름으로 사용이 불가능한 예: `1a`, `.2`, `k-j`


{% highlight r %}
x <- 1
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
y <<-2
print(y)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
z = 3
print(z)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# 전역변수 표현 방식(x변수는 글로벌변수처럼 처리된다.)
sum(x <- c(1,2,3,4,5)) 
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
x
{% endhighlight %}



{% highlight text %}
## [1] 1 2 3 4 5
{% endhighlight %}



{% highlight r %}
# 지역변수 표현 방식(y변수는 로컬변수처럼 처리된다.)
sum(y = c(1,2,3,4,5)) 
{% endhighlight %}



{% highlight text %}
## [1] 15
{% endhighlight %}



{% highlight r %}
y
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}

***

### 숫자(정수, 실수)


{% highlight r %}
x <- 2
print(x)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
# 변수의 타입을 return해주는 method
class(x)
{% endhighlight %}



{% highlight text %}
## [1] "numeric"
{% endhighlight %}

R에서는 기본적으로 숫자를 실수로 표현한다.


{% highlight r %}
y <- 2L
class(y)
{% endhighlight %}



{% highlight text %}
## [1] "integer"
{% endhighlight %}

대문자 `L`(RESERVED WORD)을 사용하면 정확하게 정수로 표현된다.


{% highlight r %}
z <- x+y
# class와 비슷하게 타입과 값을 동시에 return해준다.
str(z)
{% endhighlight %}



{% highlight text %}
##  num 4
{% endhighlight %}

`is.type`와 같은 형식(`is.numeric`,`is.integer`,`is.character`,`is.logical` 등)은 변수의 타입을 확인하는 방법으로 BOOLEAN형식으로 표현해준다.


{% highlight r %}
is.numeric(z)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
is.integer(y)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}

***

### 숫자(지수표기법)


{% highlight r %}
# 1 * 10^2
1e2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}



{% highlight r %}
# 5 * 10^-1
5e-1
{% endhighlight %}



{% highlight text %}
## [1] 0.5
{% endhighlight %}

***

### 문자열

문자열을 입력할 때는 ''(Single quation mark)나 ""(double quation mark)를 사용하면 된다.


{% highlight r %}
s1 <- 'hello'
class(s1)
{% endhighlight %}



{% highlight text %}
## [1] "character"
{% endhighlight %}



{% highlight r %}
s2 <- "안녕하세요"
class(s2)
{% endhighlight %}



{% highlight text %}
## [1] "character"
{% endhighlight %}



{% highlight r %}
is.character(s2)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}

***

### Boolean(진리값)

`AND`는 `&`, `OR`은 `|`로 표현한다.


{% highlight r %}
TRUE & TRUE
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
TRUE | FALSE
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
# 약어로도 표현할 수 있다.
T & F
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}

하지만 약어 사용은 변수로 선언되었으면 헷갈릴 수 있다. 처리하는 우선순위가 진리값보다 변수가 더 높으므로 약어 사용을 지양하자.

***

### NA(Not Available)

결측치(결측값)으로 데이터 입력 중 실수로 값이 입력되지 않는 경우에 발생한다. (`NULL`과 다름을 주의)


{% highlight r %}
a <- 100; b <- 90; c <- NA;
is.na(a)
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}



{% highlight r %}
is.na(c)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
# 결측값이 있는 변수로 연산 작업을 하면 NA로 표시된다.
a+b+c
{% endhighlight %}



{% highlight text %}
## [1] NA
{% endhighlight %}

***

### NULL

`NULL`은 Undefined값을 표현한다. 변수가 초기화되지 않을 때 사용한다. 즉, 선언 시에 숫자를 넣을지 문자를 넣을지 모르지만 변수를 선언하고 싶을 때 사용한다. (`NA`과 다름을 주의) 


{% highlight r %}
# R은 대소문자를 구분하기에 대문자 NULL을 사용해야 한다.
x <- NULL

is.null(x)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
is.na(x)
{% endhighlight %}



{% highlight text %}
## logical(0)
{% endhighlight %}



{% highlight r %}
y <- 100

# 아래 결과를 보고 하나의 값이 없다는 것을 알아야 한다.
x + y
{% endhighlight %}



{% highlight text %}
## numeric(0)
{% endhighlight %}

***

## 연산자

### 산술연산자

기본 사칙연산이 가능하다. 


{% highlight r %}
# 몫만 추출하고 싶을 시
100 %/% 3
{% endhighlight %}



{% highlight text %}
## [1] 33
{% endhighlight %}



{% highlight r %}
# 나머지만 추출하고 싶을 시
100 %% 3
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
# 거듭제곱(10**2로도 사용 가능)(참고, plsql에서는 power(10,2))
10^2
{% endhighlight %}



{% highlight text %}
## [1] 100
{% endhighlight %}

***

### 비교연산자

`==`(같다), `!=`(다르다), `>`(크다), `<`(작다) 등으로 표현 할 수 있다.


{% highlight r %}
10 != 5 & 10>= 10
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
(10 < 15) | (10 == 5)
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}

***
