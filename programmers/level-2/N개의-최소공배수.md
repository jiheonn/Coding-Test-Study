# N개의 최소공배수

연습문제 > [N개의 최소공배수](https://programmers.co.kr/learn/courses/30/lessons/12953)

## 문제 설명

두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미한다.  
정의를 확장해서, n개의 수의 최소공배수는 n개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 된다.  
n개의 숫자를 담은 배열 `arr`이 입력되었을 때 이 수들의 최소공배수를 return 하도록 한다.

## 문제 풀이

```python
def gcd(a, b):
    while b != 0:
        temp = a % b
        a = b
        b = temp
        
    return a;


def lcm(a, b):
    return a * b / gcd(a, b)
        
        
def solution(arr):
    while len(arr) != 1:
        arr.append(lcm(arr.pop(), arr.pop()))
    
    return arr[0]
```

### 풀이 설명

두 수의 최대공약수를 구하는 알고리즘인 유클리드 호제법으로 `gcd()` 함수를 정의한다.

두 수의 최소공배수는 두 수의 곱을 두 수의 최대공약수로 나눈 것과 같다. 이를 통해 `lcm()` 함수를 정의한다.

n개의 숫자를 담은 `arr` 배열에서 원소 2개씩 꺼내어 최소공배수를 구하고, `arr` 배열에 다시 담는다.  
이를 `arr` 배열의 원소가 1개가 남을 때까지 반복하여, 마지막에 남은 1개의 원소를 반환한다.
