---
layout: post
title: "Function in R"
date: "2018-07-29"
excerpt: "R에서의 함수"
output: 
  github_document:
    toc: true
    toc_depth: 3
categories: r
tag: [r, function]
comments: true
---

## 문자함수

### grep(): 문자열 패턴 검색 함수

문자 패턴을 찾을 때 사용되는 함수이다. 다음 특수문자와 option을 사용할 수 있다.

    ^ : 첫번째 
    $ : 마지막
    . : 특정 자리수
    * : wild card

`ignore.case`
- `ignore.case = TRUE`: 대소문자 구분안한다.  
- `ignore.case = FALSE`: 대소문자 구분한다.


{% highlight r %}
setwd("C:/data")
{% endhighlight %}



{% highlight text %}
## Error in setwd("C:/data"): cannot change working directory
{% endhighlight %}



{% highlight r %}
emp <- read.csv('emp.csv',stringsAsFactors = F)
{% endhighlight %}



{% highlight text %}
## Error in file(file, "rt"): cannot open the connection
{% endhighlight %}



{% highlight r %}
emp[grep("aa", emp$LAST_NAME),c("LAST_NAME","SALARY")]
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'emp' not found
{% endhighlight %}



{% highlight r %}
emp[grep("[x-z]", emp$LAST_NAME, ignore.case = TRUE),c("LAST_NAME","SALARY")]
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'emp' not found
{% endhighlight %}

***

### nchar(): 문자 수를 return하는 함수

공백까지 포함한 문자의 수를 return해준다. option으로 `type`을 설정하여 그 타입에 맞게 세어 줄 수 있다.


{% highlight r %}
nchar('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# char로 센다
nchar('R Developer', type = "chars")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}



{% highlight r %}
# byte값으로 센다.
nchar('R Developer', type = "bytes")
{% endhighlight %}



{% highlight text %}
## [1] 11
{% endhighlight %}

***

### strsplit(): 부분문자로 분리하는 함수

문자를 분리해준다. 이 함수는 `split`이라는 option을 반드시 사용해야 한다. 어떠한 글자가 자주 등장하는지 파악할 때 도움이 된다.


{% highlight r %}
# split이라는 option을 반드시 사용해야 한다.
# 한글자씩 분리(character안의 값을 바꾸어도 결과는 같음)
strsplit('R Developer',split = character(0))
{% endhighlight %}



{% highlight text %}
## [[1]]
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}



{% highlight r %}
# 공백을 기준으로 분리
strsplit('R Developer',split =" ")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}



{% highlight r %}
# ,를 기준으로 분리
strsplit('R,Developer',split =",")
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "R"         "Developer"
{% endhighlight %}

결과는 list type으로 출력됨을 알 수 있다. 아래 함수를 참고하자.

### unlist(): list형을 vector형으로 변환 함수

위에 이어서, 만약 Vector type으로 바꾸고 싶다면 `unlist(strsplit())`을 사용하면 하면 된다.


{% highlight r %}
unlist(strsplit('R Developer',split = character(0)))
{% endhighlight %}



{% highlight text %}
##  [1] "R" " " "D" "e" "v" "e" "l" "o" "p" "e" "r"
{% endhighlight %}

***

### toupper()/tolower(): 대소문자 변환하는 함수

알파벳을 대소문자로 변환하는 함수이다.


{% highlight r %}
# 대문자로 변환
toupper('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "R DEVELOPER"
{% endhighlight %}



{% highlight r %}
# 소문자로 변환
tolower('R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "r developer"
{% endhighlight %}

***

### substr(): 문자열 추출 함수

`substr(' ',시작점,끝점)`이다. sql에서와 `substr()`와 다름을 주의하자.


{% highlight r %}
# 첫번째부터 첫번째까지 추출
substr('R Developer',1,1)
{% endhighlight %}



{% highlight text %}
## [1] "R"
{% endhighlight %}



{% highlight r %}
# 첫번째부터 세번째까지 추출
substr('R Developer',1,3)
{% endhighlight %}



{% highlight text %}
## [1] "R D"
{% endhighlight %}



{% highlight r %}
# 5번째부터 11번째 추출
substr('R Developer',5,11)
{% endhighlight %}



{% highlight text %}
## [1] "veloper"
{% endhighlight %}

***

### sub(): 첫번째 일치하는 문자만 바꾸는 함수

`sub('찾아야 할 글자','바꿔야 할 글자','해당 데이터')`로 사용한다. 하지만 찾아야 할 글자가 많다면 첫번째로 일치하는 글자만 바꿔야 할 글자로 바꾸어준다.


{% highlight r %}
# 3번째의 값에서 R을 Python으로 바꾸는데 첫번째로 찾는 R을 바꾼다.
sub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer R Developer"
{% endhighlight %}

***

### gsub(): 일치하는 문자를 모두 바꾸는 함수

`gsub('찾아야 할 글자','바꿔야 할 글자','해당 데이터')`로 사용한다. `sub()`과 다르게 일치하는 문자를 모두 바꾸어준다.


{% highlight r %}
# 3번째의 값에서 R에 일치하는 문자를 전부  Python으로 바꾸어준다.
gsub('R','Python','R Programmer R Developer')
{% endhighlight %}



{% highlight text %}
## [1] "Python Programmer Python Developer"
{% endhighlight %}



{% highlight r %}
# 0부터 2사이의 숫자를 *로 바꾸어준다.
gsub('[0-2]','*','123450')
{% endhighlight %}



{% highlight text %}
## [1] "**345*"
{% endhighlight %}


***

## 숫자함수

### round(): 반올림 함수

option을 사용하여 반올림할 위치를 정할 수 있다.


{% highlight r %}
round(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# default값은 0임을 알 수 있다.
round(3.141592,0)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# 반올림해서 소수점 3번째 자리까지 표현
round(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3.142
{% endhighlight %}



{% highlight r %}
# 반올림해서 정수 1번째 자리만 표현
round(3.141592,-1)
{% endhighlight %}



{% highlight text %}
## [1] 0
{% endhighlight %}

***

### trunc(): 버림 함수

소수점을 모두 버리는 함수이다.


{% highlight r %}
trunc(3.141592)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}



{% highlight r %}
# 소수점 3번째 자리밑으로 버림은 안된다.
trunc(3.141592,3)
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}

***

### signif(): 반올림 함수(위치 순서)

`round()`함수와 다르게 제일 첫번째 자리가 1로 기준이 되어 해당 위치값에 맞게 반올림을 해준다.


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

### floor(): 같거나 작은 정수를 추출하는 함수


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

### mod(): 모드함수는 없다.

사용하려면 `%%`와 `%/%`를 사용해야 한다.


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

## 날짜함수

### Sys.Date(): 현재 서버 날짜 표시


{% highlight r %}
Sys.Date()
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-29"
{% endhighlight %}

***

### Sys.time()/date(): 서버의 현재 상세 시간 표시


{% highlight r %}
Sys.time()
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-29 16:58:57 KST"
{% endhighlight %}



{% highlight r %}
date()
{% endhighlight %}



{% highlight text %}
## [1] "Sun Jul 29 16:58:57 2018"
{% endhighlight %}

***

### as.Date(): 문자날짜를 날짜형으로 변환하는 함수

지역에 종속되기 때문에 다음과 같이 그 지역의 문자열 표준서식에 맞게 써주어야 한다.


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

표준서식에 맞게 쓰지 않는다면, `format`을 써주어야 표준서식으로 변환된다.


{% highlight r %}
as.Date('20180725',format = '%Y%m%d')
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-25"
{% endhighlight %}



{% highlight r %}
as.Date('2018년 1월 2일',format = '%Y년%m월%d일')
{% endhighlight %}



{% highlight text %}
## [1] "2018-01-02"
{% endhighlight %}

#### 날짜 Format

`format`의 상세 option은 다음과 같다.

    `%Y`: 세기를 포함한 년도(4자리)
    `%y`: 세기를 생략한 년도(2자리)
    `%m`: 숫자달
    `%B`: 문자달
    `%b`: 문자달의 약어
    `%d`: 일
    `%A`: 문자요일
    `%a`: 문자요일의 약어
    `%u`: 숫자요일(1(월)~7(일))
    `%w`: 숫자요일(0(일)~6(월))
    `%H`: 시
    `%M`: 분
    `%S`: 초
    `%z`: timezone 시간
    `%Z`: timezone 이름
    
`format`을 사용하여 다음과 같이 할 수 있다.


{% highlight r %}
format(Sys.time(),'%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "18-07-29-Sunday 16:58:57"
{% endhighlight %}
    
***

### 날짜 계산 방법


{% highlight r %}
# 날짜 + 숫자 = 날짜
Sys.Date() + 100
{% endhighlight %}



{% highlight text %}
## [1] "2018-11-06"
{% endhighlight %}



{% highlight r %}
# 날짜 - 숫자 = 날짜
Sys.Date() - 200
{% endhighlight %}



{% highlight text %}
## [1] "2018-01-10"
{% endhighlight %}



{% highlight r %}
# 특정 날짜를 사용하여 더할 수 있다.
as.Date('2018-01-01', format = '%Y-%m-%d') + 100
{% endhighlight %}



{% highlight text %}
## [1] "2018-04-11"
{% endhighlight %}



{% highlight r %}
# 날짜 - 날짜 = 숫자
as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d')
{% endhighlight %}



{% highlight text %}
## Time difference of -182 days
{% endhighlight %}



{% highlight r %}
# 날짜의 차이에서 숫자값만 보고 싶은 경우
as.numeric(as.Date('2018-05-24', format = '%Y-%m-%d') - as.Date('2018-11-22', format = '%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] -182
{% endhighlight %}

***

### weekdays(): 요일을 출력하는 함수


{% highlight r %}
weekdays(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Sunday"
{% endhighlight %}



{% highlight r %}
weekdays(as.Date('2000-01-01', format='%Y-%m-%d'))
{% endhighlight %}



{% highlight text %}
## [1] "Saturday"
{% endhighlight %}

***

### dfftime(): 두 날짜간의 일 수 표현


{% highlight r %}
difftime('2018-01-01', Sys.Date())
{% endhighlight %}



{% highlight text %}
## Time difference of -209.375 days
{% endhighlight %}



{% highlight r %}
# 숫자만 출력하고 싶은 경우
as.numeric(difftime('2018-01-01', Sys.Date()))
{% endhighlight %}



{% highlight text %}
## [1] -209.375
{% endhighlight %}



{% highlight r %}
# 정수값만 출력하고 싶은 경우
round(as.numeric(difftime('2018-01-01', Sys.Date())))
{% endhighlight %}



{% highlight text %}
## [1] -209
{% endhighlight %}

***

### as.difftime(): 시간의 차이


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

### quarters(): 분기 표현

해당 날짜의 분기 정보를 표현한다.


{% highlight r %}
quarters(Sys.Date())
{% endhighlight %}



{% highlight text %}
## [1] "Q3"
{% endhighlight %}

***

### lubridate 패키지: 날짜 표현 패키지

`lubridate()`는 날짜를 다룰 때 유용한 패키지다. 날짜를 출력할 때 format을 안써도 되는 이점이 있다. 먼저 패키지 설치를 한 다음에 load를 시켜주어야 한다.


{% highlight r %}
library(lubridate)
{% endhighlight %}



{% highlight text %}
## Error in library(lubridate): there is no package called 'lubridate'
{% endhighlight %}



{% highlight r %}
# 날짜 출력
# 현재 날짜
now()
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 연도 출력 
year(now()) # format(Sys.time(),'%Y')와 같다.
{% endhighlight %}



{% highlight text %}
## Error in year(now()): could not find function "year"
{% endhighlight %}



{% highlight r %}
# 달 출력
month(now())
{% endhighlight %}



{% highlight text %}
## Error in month(now()): could not find function "month"
{% endhighlight %}



{% highlight r %}
# factor형으로 되어있음을 알 수 있다.
month(now(), label = T)
{% endhighlight %}



{% highlight text %}
## Error in month(now(), label = T): could not find function "month"
{% endhighlight %}



{% highlight r %}
# 일 출력
day(now())
{% endhighlight %}



{% highlight text %}
## Error in day(now()): could not find function "day"
{% endhighlight %}



{% highlight r %}
# 요일 출력
wday(now()) # format에서의 %u, %w와 다르다.
{% endhighlight %}



{% highlight text %}
## Error in wday(now()): could not find function "wday"
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 1) # 월요일 기준으로 출력
{% endhighlight %}



{% highlight text %}
## Error in wday(now(), week_start = 1): could not find function "wday"
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7) # 일요일 기준으로 출력
{% endhighlight %}



{% highlight text %}
## Error in wday(now(), week_start = 7): could not find function "wday"
{% endhighlight %}



{% highlight r %}
wday(now(), week_start = 7, label = T) # level 출력
{% endhighlight %}



{% highlight text %}
## Error in wday(now(), week_start = 7, label = T): could not find function "wday"
{% endhighlight %}



{% highlight r %}
# 날짜 연/개월 등의 수 출력
# 연 수 (오라클의 to_yminterval()과 비슷함)
years(10)
{% endhighlight %}



{% highlight text %}
## Error in years(10): could not find function "years"
{% endhighlight %}



{% highlight r %}
# 개월 수
months(10)
{% endhighlight %}



{% highlight text %}
## Error in UseMethod("months"): no applicable method for 'months' applied to an object of class "c('double', 'numeric')"
{% endhighlight %}



{% highlight r %}
# 지금부터 10년 후
now() + years(10)
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 지금부터 100개월 후
now() + months(100)
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 지금부터 1000일 전
now() - days(1000)
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 지금부터 1년 1개월 1일 1시간 1분 1초 후
now() + years(1) + months(1) + days(1) + hours(1) + minutes(1) + seconds(1)
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 시간 계산
hm('08:00')
{% endhighlight %}



{% highlight text %}
## Error in hm("08:00"): could not find function "hm"
{% endhighlight %}



{% highlight r %}
now() + hm('08:00')
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
now() + hms('02:30:59')
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}

연도/달 등을 바꾸어서 다루기 원하다면 다음과 같이 변수에다가 날짜를 넣고 날을 바꿔줄 수 있다.


{% highlight r %}
date <- now()
{% endhighlight %}



{% highlight text %}
## Error in now(): could not find function "now"
{% endhighlight %}



{% highlight r %}
# 연도 수정
year(date) <- 2017
{% endhighlight %}



{% highlight text %}
## Error in year(date) <- 2017: could not find function "year<-"
{% endhighlight %}



{% highlight r %}
date
{% endhighlight %}



{% highlight text %}
## function () 
## .Internal(date())
## <bytecode: 0x102c22750>
## <environment: namespace:base>
{% endhighlight %}



{% highlight r %}
# 달 수정
month(date) <- 1 
{% endhighlight %}



{% highlight text %}
## Error in month(date) <- 1: could not find function "month<-"
{% endhighlight %}



{% highlight r %}
# 일 수정
day(date) <- 1
{% endhighlight %}



{% highlight text %}
## Error in day(date) <- 1: could not find function "day<-"
{% endhighlight %}



{% highlight r %}
# 시간 수정
hour(date) <- 00
{% endhighlight %}



{% highlight text %}
## Error in hour(date) <- 0: could not find function "hour<-"
{% endhighlight %}



{% highlight r %}
minute(date) <- 00
{% endhighlight %}



{% highlight text %}
## Error in minute(date) <- 0: could not find function "minute<-"
{% endhighlight %}



{% highlight r %}
second(date) <- 00
{% endhighlight %}



{% highlight text %}
## Error in second(date) <- 0: could not find function "second<-"
{% endhighlight %}



{% highlight r %}
format(date, '%y-%m-%d-%A %H:%M:%S')
{% endhighlight %}



{% highlight text %}
## [1] "function () "      ".Internal(date())"
{% endhighlight %}

***

### POSIX Type

POSIX(Portable Opearating System Interface)는 UNIX 간 소통 가능한 프로그램 인터페이스의 규약이다. R에서는 날짜 시간 데이터를 처리할 수 있도록 `POSIXct`,`POSIXt(POSIXlt)` 클래스를 사용한다. POSIX타입은 다음 2가지이다.

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

class로 `POSIX`타입과 `DATE`타입을 알 수 있다. `POSIX` 타입을 자세히 알아보자.


{% highlight r %}
# 시간을 numeric형식으로 풀어서 표현된다.
as.numeric(Sys.time())
{% endhighlight %}



{% highlight text %}
## [1] 1532851138
{% endhighlight %}



{% highlight r %}
# POSIXlt으로 형 변환
time <- as.POSIXlt(Sys.time())
time
{% endhighlight %}



{% highlight text %}
## [1] "2018-07-29 16:58:57 KST"
{% endhighlight %}



{% highlight r %}
# POSIX의 list타입 형식으로 보여준다.
unlist(time)
{% endhighlight %}



{% highlight text %}
##                sec                min               hour 
## "57.8819169998169"               "58"               "16" 
##               mday                mon               year 
##               "29"                "6"              "118" 
##               wday               yday              isdst 
##                "0"              "209"                "0" 
##               zone             gmtoff 
##              "KST"            "32400"
{% endhighlight %}

`POSIX`의 상세값은 다음과 같다.
    

    `mday`: 그 달의 일
    `mon`: 1월을 0으로 시작하는 달
    `year`: 1900년을 0으로 시작하는 년
    `wday`: 일요일을 0으로 시작하는 일
    `yday`: 1월 1일을 0으로 시작하는 일
    `isdst`: 서머타임
    `zone`: timezone 이름
    `gmtoff`: timezone의 시(초단위로)


#### strptime(): POSIX타입으로 형변환

`strptime()`를 사용하면 `POSIX`타입으로 형을 변환 시킬 수 있다.


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
## POSIX형태로의 형변환
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
