---
layout: post
title: "[SQL] ANALYTIC FUNCTION"
date: "2018-07-21"
excerpt: "OLAP 기능에 적합한 함수"
toc: true
tag:
  [sql, analyticfunction]
output: github_document
comments: true
categories:
  SQL
---

## 분석함수(Analytic Function)

분석함수는 OLAP 기능에 적합하고 단일행(문자함수, 날짜함수, 형변환함수 등) 함수처럼 사용가능하다. 아래 문제를 보고 분석 함수의 이점을 알아보자.

<br>

***

### SUM/AVG() OVER ()

누적되게 값을 출력하는 방식이다.

```sql
--Ex. 30번 부서의 평균 급여보다 더 높은 급여를 받는 사원을 출력하세요

SELECT e.employee_id, e.salary, e.department_id, sum(t.salary) as total
FROM employees e, employees t
WHERE e.department_id = 30
AND t.department_id = 30
AND e.employee_id >= t.employee_id
GROUP BY e.employee_id, e.salary, e.department_id;
```

아래 문제를 분석함수를 사용하면 편리하게 사용할 수 있다.

>SUM() OVER(ORDER BY -)

```sql
--row단위로 salary에 대한 합을 출력

SELECT employee_id, salary, department_id, SUM(salary) OVER (ORDER BY employee_id) AS total
FROM employees
WHERE department_id = 30;


>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID      TOTAL
----------- ---------- ------------- ----------
        114      11000            30      11000
        115       3100            30      14100
        116       2900            30      17000
        117       2800            30      19800
        118       2600            30      22400
        119       2500            30      24900
```

>SUM() OVER()

```sql
--20번 사원들의 총액을 ROW단위로 출력 (order by를 쓰지 않으면 전체를 출력함)

SELECT employee_id, salary, department_id, SUM(salary) OVER () AS total
FROM employees
WHERE department_id = 20;

>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID      TOTAL
----------- ---------- ------------- ----------
        114      11000            30      24900
        115       3100            30      24900
        116       2900            30      24900
        117       2800            30      24900
        118       2600            30      24900
        119       2500            30      24900

```

>AVG() OVER()

```sql
SELECT employee_id, salary, department_id, AVG(salary) OVER () AS total
FROM employees
WHERE department_id = 30;

>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID      TOTAL
----------- ---------- ------------- ----------
        114      11000            30       4150
        115       3100            30       4150
        116       2900            30       4150
        117       2800            30       4150
        118       2600            30       4150
        119       2500            30       4150
```

>AVG() OVER(ORDER BY -)

```sql
SELECT employee_id, salary, department_id, AVG(salary) OVER (ORDER BY employee_id) AS total
FROM employees
WHERE department_id = 30;

>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID      TOTAL
----------- ---------- ------------- ----------
        114      11000            30      11000
        115       3100            30       7050
        116       2900            30 5666.66667
        117       2800            30       4950
        118       2600            30       4480
        119       2500            30       4150
```

> SUM() OVER(PARTITION BY -)

```sql
--부서별로 파티션을 나눈 다음에 총액값을 ROW단위로 출력
SELECT employee_id, salary, department_id, SUM(salary) OVER (PARTITION BY department_id) AS dept_total
FROM employees;

>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID DEPT_TOTAL
----------- ---------- ------------- ----------
        200       4400            10       4400
        201      13000            20      19000
        202       6000            20      19000
        114      11000            30      24900
        115       3100            30      24900
        116       2900            30      24900
        117       2800            30      24900
        118       2600            30      24900
        119       2500            30      24900
```

> SUM() OVER(PARTITION BY - ORDER BY -)

```sql
--부서별로 파티션을 나눈 다음에 누적값을 ROW단위로 출력
SELECT employee_id, salary, department_id, sum(salary) OVER (PARTITION BY department_id ORDER BY employee_id) AS total
FROM employees
WHERE department_id <= 30;

>결과

EMPLOYEE_ID     SALARY DEPARTMENT_ID      TOTAL
----------- ---------- ------------- ----------
        200       4400            10       4400
        201      13000            20      13000
        202       6000            20      19000
        114      11000            30      11000
        115       3100            30      14100
        116       2900            30      17000
        117       2800            30      19800
        118       2600            30      22400
        119       2500            30      24900
```

그룹함수 뒤의 `OVER()`는 다음의 `OPTION`이 생략되어 있는 것이다.

```sql
--각 쿼리의 마지막 컬럼은 option을 쓰지 않았다.
SELECT employee_id, salary,
  SUM(salary) over (ORDER BY employee_id rows between unbounded preceding and current row),
  SUM(salary) over (ORDER BY employee_id)
FROM employees;

SELECT employee_id, salary,
  SUM(salary) over (ORDER BY employee_id rows between unbounded preceding and unbounded following),
  SUM(salary) over ()
FROM employees;
```

- `rows between unbounded preceding and current row`: 정렬결과 처음부터 현재행까지를 대상
- `rows between unbounded preceding and unbounded following`: 정렬결과 처음과 끝을 대상

아래와 같은 방식으로 사용할 수 있다.

```sql
SELECT department_id, salary,
  first_value(salary) over (partition by department_id order by salary rows between unbounded preceding and unbounded following) first_value,
  last_value(salary) over (partition by department_id order by salary rows between unbounded preceding and unbounded following) last_value
FROM employees
WHERE department_id IN (10,30);

>결과

DEPARTMENT_ID     SALARY FIRST_VALUE LAST_VALUE
------------- ---------- ----------- ----------
           10       4400        4400       4400
           30       2500        2500      11000
           30       2600        2500      11000
           30       2800        2500      11000
           30       2900        2500      11000
           30       3100        2500      11000
           30      11000        2500      11000
```


<BR>

***

### RANK(): TOP-N분석 시

순위를 출력해야 하는 경우 일 때 `RANK()` 혹은 `DENSE_RANK()`를 떠올리자

```sql
SELECT employee_id, salary, 
  RANK() OVER (ORDER BY salary desc) as rank,
  DENSE_RANK() OVER (ORDER BY salary desc) as dense_rank
FROM employees
WHERE department_id IN (90,100);

>결과

EMPLOYEE_ID     SALARY       RANK DENSE_RANK
----------- ---------- ---------- ----------
        100      24000          1          1
        101      17000          2          2
        102      17000          2          2
        108      12008          4          3
        109       9000          5          4
        110       8200          6          5
        112       7800          7          6
        111       7700          8          7
        113       6900          9          8
```

<br>

### LNNVL()

`LNNVL()`의 안에 들어오는 매개변수 값을 반대로 출력해준다. 아래 예시를 보고 `LNNVL()`을 이해해보자.

```sql
SELECT *
FROM employees e
WHERE job_id = 'IT_PROG'
UNION
SELECT *
FROM employees
WHERE department_id = 20;
```

위 문장은 sort가 발생한다. 그래서 `UNION ALL` 을 쓰고 `NOT EXISTS`를 써서 튜닝해줘야하지만 `LNNVL()`을 쓸 수 있다.

```sql
SELECT *
FROM employees
WHERE department_id = 20
UNION ALL
SELECT *
FROM employees e
WHERE job_id = 'IT_PROG'
AND LNNVL(department_id = 20);
```

여기서 `LNNVL(department_id = 20)`은 `department_id != 20` OR `department_id IS NULL`을 의미한다.
