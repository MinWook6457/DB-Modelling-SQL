### 조인
하나 이상의 테이블로 부터 데이터를 검색하기 위함
일반적으로 외래키를 사용하는 경우가 대부분이지만 때로는 논리적인 값들의 연관으로도 조인 하는 경우가 있음

### 카티젼 조인
두 테이블의 모든 행들의 조인 => M:M 조인으로 두 개의 집합 간의 연결고리 조건이 전혀 없는 경우에 발생

EX)
```sql
SELECT I.SABUN, I.JOIN_DAY, E.RECT_REG_NO
FROM INSA I, INSA_EMP_PJT E
ORDER BY E.RECT_REG_NO DESC
```

조인에 사용된 테이블의 곱으로 두 개의 테이블의 모든 데이터를 리턴

### 조인 전 알아두면 좋은 테이블 개념

#### DUAL 테이블
SELECT의 값을 확인해 볼 때 주로 사용하는 테이블
```sql
SELECT * FROM DUAL
```

=> DUMMY / 컬럼명으로 생성

#### COPY_T 테이블
기준 테이블을 원하는 배수만큼 복제하여 결과 집합을 구할 때 사용

COPY_T 테이블 생성
```sql
CREATE TABLE COPY_T
AS
SELECT ROWNUM AS COL_1, TO_CHAR(ROWNUM,'009') AS COL_2
FROM CMM_CODE_DETAIL
WHERE ROWNUM < 101;
```
