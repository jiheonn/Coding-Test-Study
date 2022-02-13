# 이름에 el이 들어가는 동물 찾기

String, Date > [이름에 el이 들어가는 동물 찾기](https://programmers.co.kr/learn/courses/30/lessons/59047)

## 문제 설명

동물 보호소에 들어온 동물의 정보를 담은 `ANIMAL_INS` 테이블 구조는 다음과 같다.

- `ANIMAL_ID`: 동물의 아이디
- `ANIMAL_TYPE`: 생물 종
- `DATETIME`: 보호 시작일
- `INTAKE_CONDITION`: 보호 시작 시 상태
- `NAME`: 이름
- `SEX_UPON_INTAKE`: 성별 및 중성화 여부

동물 보호소에 들어온 동물 이름 중, 이름에 "EL"이 들어가는 개의 아이디와 이름을 조회하는 SQL문을 작성한다. 단, 결과는 이름 순으로 조회하며 이름의 대소문자는 구분하지 않는다.

## 문제 풀이

```sql
SELECT
    ANIMAL_ID, NAME
FROM
    ANIMAL_INS
WHERE
    UPPER(NAME) LIKE UPPER("%el%")
    AND ANIMAL_TYPE = "Dog"
ORDER BY
    NAME ASC;
```
