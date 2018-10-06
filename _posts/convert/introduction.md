---
layout: post
title: "[SQL] Introduction"
date: "2018-07-01"
excerpt: "SQL 환경 설정 및 개요"
output: 
  html_document:
    toc: true
    toc_depth: 3
comments: true
categories:
  sql
tags:
  sql, erdiagram
---

# SQL Developer 기본 환경 설정

## 새로 만들기 / DB 접속선택

* 호스트 이름 : DB가 있는 주소 (ex, IP...)
* 포트 : OS와 운영 프로그램(ex, Orcle...) 과 연결시켜주는 값 (충돌 방지)
    * Ex, 1521 : Oracle 고유포트
* SID (System Identifier) 
    * DB 서버를 식별하는데 필요한 고유한 메모리 이름
    * Data는 Storage에 저장되어 있고 이 Storage에 저장되어 있는 Data를 다루기 위해 메모리에 저장해야함
    * 이 메모리 이름을 __SID__라 부름.
    * SID는 Storage 이름과 일치해야 함
    
* 현업에서 접속을 위해 고객사로부터 받 정보
    * 접속이름/사용자이름/PW/호스트이름/포트/SID
    
***

# RDBMS

### 들어가기 앞서

* 기본 용어 정리 (Entity와 Attribute)
    * `Entity`: Object(Table) 안에서 사용하는 고유한 이름 (Table 명과 같은 의미)
    * `Attribute`: Table의 Column 명
    * 엔티티 분리: 정규화 작업
        * 왜? 중복을 제거하기 위해 -> 저장공간 낭비 방지 
        * __중복이 있다면 무조건 분리시키고 Key 값을 가져가자__
    * 모델러: 현업의 전문가로서 데이터 모델링을 하는 사람
    
* 데이터 무결성 
    * 데이터의 정확성과 일관성을 유지하는 것
    * 데이터의 품질과 연관됌
    
* Table 디자인을 고민해서 DB를 만들어야 함

***

### 데이터 모델

![plot of chunk unnamed-chunk-1](/assets/article_images/introduction/unnamed-chunk-1-1.png)

***

### ER Diagram
#### ER Diagram?

* 엔티티 간의 연결고리는 KEY값으로 가져감 -> 이를 표시해준 Diagram
    * KEY 값으로 1:n 혹은 n:n 관계를 만들 수 있음
    * `Primary key`
        *테이블의 각 데이터 행은 Primary key를 통해 식별됌
    * `Forien key`
        * FK를 사용하여 여러 테이블의 데이터를 논리적으로 연킬 수 있음
        * 언제나 Orimary key를 참조(Foreign key는 Primary key에 종속)
        * 참조로 인해  PK를 삭제할 때 FK가 막아서 삭제를 방지함 -> Data 품질을 높임

***

#### CROSS PUT

* 1:n 관계를 나타냄
* 점선을 사용하는 이유는 있을 수도 있고 없을 수도 있기 때문.(Ex. 제품 정보는 있으나 구매 내역이 없는 경우)
* 점선 관계: NULL 값이 들어 갈 수 있음. (배치 받을 수 있는 형태)
    * Ex. 사원과 부서 간 점선 관계 -> 소속 사원이 부서에 있을 수도, 없을 수도 있음(NULL 허용 O)

* 실선 관계: 무조건 배치 받아야 하는 형태
    * Ex. 사원과 부서 간 실선/점선 관계 -> 소속 사원이 부서에 있어야 함(NULL 허용 X)
    
***

### SQL문의 개요

>RDBMS 안에 있는 데이터를 조작하는 언어는 SQL뿐이다.

#### DQL(Data Query Language)
* `SELECT`: SQL의 기본 중의 기본


#### DML(Data Manipulation Language)
    ROW 단위
* `INSERT`
* `UPDATE`
* `DELETE`
* `MERGE`: DATA WAREHOUSING 할 때 주로 사용


#### TCL(Transaction Control Language)
    DML 문장이 수행되면 Transaction이 발생 -> TLC를 반드시 수행해야 충돌이 일어나지 않음
* `COMMIT`
* `ROLLBACK`
* `SAVEPOINT`


#### DDL(Data Definition Language)
    TABLE 단위
* `CREATE`
* `ALTER`
* `DROP`
* `RENAME`
* `TRUNCATE`: 사용시 주의(데이터가 영구히 삭제됌)
* `COMMENT`: 주석처리 때 사용


#### DCL(Data Control Language)
    권한 부여
* `GRANT`
* `REVOKE`

***

### 책 매커니즘
　  | 
------| ------ 
책      | TABLE
페이지  | PAGE, BLOCK
문장    | ROW
단어    | FIELD


***

### DATA를 저장하는 단계

* Oracle DB 안에 DATA를 저장하는 단계는 다음 순서와 같다

DB            | 논리적인 영역
------        | ------ 
TABLE SPACE   | DB보다 하위의 논리적인 영역
SEGMENT       | Storage를 갖는 TABLE(OBJECT)<BR>실제 데이터가 저장되는 영역
EXTENT        | BLOCK의 집합
BLOCK         | 최소 INPUT/OUTPUT 단위<BR>크기는 보통 2K, 4K, 8K, 16K, 32K
***

### RDBMS에서 데이터를 처리하는 방법 

딱 2가지 뿐! FULL SCAN 과 ROWID SCAN!



1. __FULL SCAN__

2. __ROWID SCAN__
    1. BY USER ROWID SCAN
    2. INDEX ROWID SCAN


***

### SELECT 문의 기능

> SELECT를 하기 전, 테이블과 컬럼 타입을 먼저 확인하자!<br>

* USER의 모든 테이블 확인: `SELECT * FROM tab;`

* 테이블의 컬럼명 확인: `DESC 테이블명`
    
SELECT 문의 기능은 3가지다.

    1. PROJECTION
    2. SELECTION
    3. JOIN

***

#### PROJECTION

* 테이블에서 열단위로 추출하기 위해 사용함

```sql
Ex.

SELECT employee_id, last_name
FROM employees;
```


#### SELECTION

* 테이블에서 행을 추출

```sql
Ex.

SELECT *
FROM employees
WHERE employee_id = 100;
```

#### JOIN

* 서로 다른 테이블에서 원하는 데이터를 추출하는 방법

```sql
Ex.

SELECT d.department_name
FROM employees e, departments d
WHERE e.department_id=d.department_id
AND e.employee_id=100;
```

<br>

***

### 동일 SQL문의 기준

* 똑같은 실행계획을 반복하면 CPU 낭비. 그래서 실행한 계획을 메모리에 저장을 함
* DB에 접속한다 = 메모리에 접속한다. -> 메모리가 대신 DISK처리.
* 하지만, 결과는 같더라도 같은 문장은 아님(대소문자가 다름, 다른 문자체계)

조건은 다음과 같다.
  
	1. 대소문자 일치
	2. 공백, TAB KEY, ENTER KEY 일치
	3. 주석(/*주석내용*/ 또는 --주석내용) 일치
	4. 실행계획을 제어하는 힌트 일치 /*+ FULL(E) */ (+는 힌트를쓰겠다 라는 의미)
	5. 상수값, 리터럴값 일치
		=>그럼 동일 SQL문으로 사용하기 위해선 어떻게 해야할까? - 변수처리 (PL/SQL)
		
<br>

```sql
SELECT * 
FROM employees 
WHERE employee_id = 100;
```
```sql
SELECT * 
FROM employees 
WHERE employee_id = 200;
```

* RDMS에다가 row를 입력하면, row마다 고유한 주소를 가지고 있음.

```sql
SELECT rowid, employee_id 
FROM employees;
```

* rowid는 가상 컬럼이자 책 매커니즘에서의 쪽 번호라 생각하면 됌
* rowid는 물리적인 row 주소값

```
Rowid: AAAEAbAAEAAAADNAAA

AAAEAb(첫 6자리) - Ojbect id
AAE(다음 3자리) - data file 번호
AAAADN(다음 6자리) - block 번호
AAA(다음 3자리) - row slot 번호
```

<br>

```sql
SELECT * 
FROM employees 
WHERE rowid = 'AAAEAbAAEAAAADNAAA';
```

* 특정 row 를 찾아가는 가장 빠른 방법 - 하나의 i/o만 발생
* 하지만, rowid의 18자리를 기억하고 찾는 것은 힘듦
* 그래서, index mechanism 을 사용해서 찾아 간다! (ex, WHERE employee_id=100; )

<br>

***

### 변수

* 문자 명은 대부분 VARCHAR 사용. (이유는 알고 쓰자)
* DATE 는 7 Byte.
* NUMBER(8,2) : 전체 8자리 중에 2자리는 소수점으로 가진다.
* NUMBER(2,2) : 전체 2자리 중에 2자리를 소수점으로 -> **아, 소수점 2자리겠다 를 파악할 수 있다!**
* 널 Col. : 'NOT NULL' = 필수항목.

<br>

***

## SCAN 방식
* RDBMS에서 데이터를 처리하는 방법은 __2가지__ 뿐이다.

![plot of chunk unnamed-chunk-2](/assets/article_images/introduction/unnamed-chunk-2-1.png)
    
* FULL SCAN: 모든 데이터를 검색한다.
* ROWID SCAN: ROWID를 기억하지 못하니, ROWID SCAN을 하기 위해 INDEX 사용해서 찾음
