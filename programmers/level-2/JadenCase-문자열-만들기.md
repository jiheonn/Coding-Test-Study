# JadenCase 문자열 만들기

연습문제 > [JadenCase 문자열 만들기](https://programmers.co.kr/learn/courses/30/lessons/12951)

## 문제 설명

JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자이다.  
문자열 `s`가 주어졌을 때, `s`를 JadenCase로 바꾼 문자열을 return 하도록 한다.  
단, 첫 문자가 알파벳이 아닐 때 이어지는 알파벳은 소문자이다.

## 문제 풀이

```python
def solution(s):
    return ' '.join([word.capitalize() for word in s.split(' ')])
```

### 함수 설명

- `capitalize()`: 문자열의 첫글자는 대문자로, 나머지는 소문자로 변환한다.
