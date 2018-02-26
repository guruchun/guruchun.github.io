---
layout: post
title: Python  1
category: [python]
tags: [python, 기초, basic]
---

## 자료형

- 정수
``` python
>>> a = 123
>>> a = -178
>>> a = 0b0110011 # 2진수 표현
>>> a = 0o177     # 8진수 표현
>>> a = 0x8ff     #16진수 표현
```
- 실수
``` python
>>> a = 1.2
>>> a = -3.45
>>> a = 4.24E10   #지수 표현
>>> a = 4.24e-10
```

- 문자열
  - 작은따옴표, 큰따옴표, 따옴표3개 연속으로 둘러싼다.
  - 이스케이프코드: \n, \t, \\, \', \"

## 연산자

- /: 나눗셈, 2.7에서 정수나눗셈은 정수로 결과를 반환하지만 3.4에서는 실수로 반환한다.
- **: 제곱
- //: 나눗셈 몫
- %: 나눗셈 나머지
- and: 논리 AND
- or: 논리 OR
- bit : &, |, ^, ~, >>, <<

## 컨솔 입력받기
``` python
# 입력은 항상 문자열로 들어온다.
str1 = input("input number #1:"))
# 숫자로 바꾸려면 변환해야 한다.
num2 = int(input("input number #2:"))
```

## 현재 시간
``` python
import time

start = time.time()
# do something
str1 = input("input number #1:")
end = time.time()
diff = end - start
print(diff)
```

## 블럭문
- if, while, for, ...
- 조건절에 괄호는 필요없지만 있어도 된다. 블럭은 콜론':'으로 표시한다.
- ':' 다음줄에 들여쓰기를 하면서 블럭이 시작되고 들여쓰기를 끝내면 블럭이 끝난다.
``` python
if a >= 90:
    print("A")
else:
    print("B")
    print("try more...")

for x in range(10):
    print(x)
print("end")
```

## range, list
- range(x): 0부터 x 미만의 정수를 가진다. x가 포함되지 않는다.
- range(x, y): x <= .... < y 범위의 모든 정수를 가진다
- list는 collection 자료구조 중 하나이다

``` python
# list를 생성하고 list에 요소를 추가한다. 
>>> a = list()
>>> a.append(1)
>>> a.append(2)
>>> a
[1, 2]
>>> b = [1,2,3]
>>> b
[1,2,3]

# range를 list로 만들어 출력할 수 있다.
>>> range (10)
range(0, 10)
>>> range (1,10)
range(1, 10)
>>> a=range(5)
>>> b=range(1,5)
>>> print(list(a))
[0, 1, 2, 3, 4]
>>> print(list(b))
[1, 2, 3, 4]

# list는 임의의 요소를 담는다. list를 요소로 가질 수도 있다.
>>> b = [1, 2, 3]
>>> c = ['Life', 'is', 'too', 'short']
>>> d = [1, 2, 'Life', 'is']
>>> e = [1, 2, ['Life', 'is']]

# 인덱스를 사용해 요소에 접근할 수 있다.
>>> b[0]
1
# 인덱스를 사용해 요소를 변경할 수 있다.
>>> b[0]=4
>>> b
[4, 2, 3]
# 인덱스 -1은 마지막 요소를 가리킨다.
>>> e[-1]
['Life', 'is']

# list는 부분을 떼어내기 편하다. slicing
>>> a = [1, 2, 3, 4, 5]
>>> a[0:2]
[1, 2]
>>> a[:2]  # 처음부터 index 2까지
[1, 2]
>>> a[2:]  # index 2부터 끝까지
[3, 4, 5]
# 문자열도 똑같이 동작한다.
>>> a = "12345"
>>> a[0:2]
'12'
```