# [K번째수](https://programmers.co.kr/learn/courses/30/lessons/42748)

```python
def solution(array, commands):
    answer = []
    for command in commands:
        i, j, k = command
        answer.append(sorted(array[i-1:j])[k-1])

    return answer
```

**함수 설명**

- `sorted(리스트)`: 정렬된 새로운 리스트를 반환

> `list.sort()`: 기존 리스트를 정렬

**풀이 설명**

`[i, j, k]`를 원소로 가진 2차원 배열 `commands`에서 배열을 하나씩 꺼내 `i`, `j`, `k`에 대입한다. 배열의 인덱스를 맞추기 위해 필요에 따라 `-1`을 한다. `i-1`번째부터 `j`까지 자르고 정렬한 후 `k-1`의 원소를 `answer`에 담는 것을 반복한다.

**다른 사람의 풀이**

```python
def solution(array, commands):
    return list(map(lambda x: sorted(array[x[0]-1:x[1]])[x[2]-1], commands))
```
