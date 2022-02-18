# NULL 처리하기

IS NULL > [NULL 처리하기](https://programmers.co.kr/learn/courses/30/lessons/59410)

## 문제 설명

동물 보호소에 들어온 동물의 정보를 담은 `ANIMAL_INS` 테이블 구조는 다음과 같다.

- `ANIMAL_ID`: 동물의 아이디
- `ANIMAL_TYPE`: 생물 종
- `DATETIME`: 보호 시작일
- `INTAKE_CONDITION`: 보호 시작 시 상태
- `NAME`: 이름
- `SEX_UPON_INTAKE`: 성별 및 중성화 여부

동물의 생물 종, 이름, 성별 및 중성화 여부를 아이디 순으로 조회하는 SQL문을 작성한다.  
단, 이름이 없는 동물의 이름은 "No name"으로 표시해야 한다.

## 문제 풀이

```sql
SELECT
    ANIMAL_TYPE, IFNULL(NAME, "No name") AS "NAME", SEX_UPON_INTAKE
FROM
    ANIMAL_INS
ORDER BY
    ANIMAL_ID ASC;
```
