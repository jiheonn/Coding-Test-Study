# DATETIME에서 DATE로 형 변환

String, Date > [DATETIME에서 DATE로 형 변환](https://programmers.co.kr/learn/courses/30/lessons/59414)

## 문제 설명

동물 보호소에 들어온 동물의 정보를 담은 `ANIMAL_INS` 테이블 구조는 다음과 같다.

- `ANIMAL_ID`: 동물의 아이디
- `ANIMAL_TYPE`: 생물 종
- `DATETIME`: 보호 시작일
- `INTAKE_CONDITION`: 보호 시작 시 상태
- `NAME`: 이름
- `SEX_UPON_INTAKE`: 성별 및 중성화 여부

각 동물의 아이디와 이름, 들어온 날짜를 조회하는 SQL문을 작성한다.  
단, 시각(시-분-초)을 제외한 날짜(년-월-일)만 보여주며, 아이디 순으로 조회해야 한다.

## 문제 풀이

```sql
SELECT
    ANIMAL_ID, NAME, DATE_FORMAT(DATETIME, "%Y-%m-%d") AS "날짜"
FROM
    ANIMAL_INS
ORDER BY
    ANIMAL_ID;
```
