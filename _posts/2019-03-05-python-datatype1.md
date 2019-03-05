---
layout: post
title: Python 숫자형, 문자열 자료형 정리
categories:
- study
---

### 숫자형
- 정수형
- 실수형
- 복소수  

  실수? 제곱하면 0 이상이 되는 수  
  허수? 제곱하면 음수가 되는 수   

  파이썬 2.7 에서는 정수형끼리 나눌 경우 정수로만 결과값 리턴한다. 파이썬 3은 실수형으로 변환할 필요 없다.  
  ex)  
  4/3 = 0  
  4/(3*0.1) = 0.25 로 강제로 실수로 변환을 해 계산해야 한다.


### 문자열
- 문자열 곱하기
&nbsp;  
```Python
>>> a = "python"
>>> a * 2
'pythonpython'
```
&nbsp;  
- 문자열 인덱싱  
0부터 숫자를 세고, 뒤에서부터는 -1부터 센다.
&nbsp;  
```python
>>> a = "Life is Short"
>>> a[2]
f
>>> a[-1]
t
```
&nbsp;  
- 문자열 슬라이싱  
시작번호부터 끝번호 전까지의 문자열을 가져온다.  
시작번호, 끝번호의 생략도 가능하다.
&nbsp;  
```python
>>> a = "Life is Short"
>>> a[0:4]
Life
>>> a[:4]
Life
>>> a[5:]
is Short
>>> a[:]
Life is Short
```
&nbsp;  
- 문자 개수 세기
&nbsp;  
```python
>>> a = "apple"
>>> a.count('p')
2
```
&nbsp;  
- 문자 위치 알려주기
&nbsp;  
```python
>>> a = "apple"
>>> a.find('p')
1
>>> a.find('b')
-1
>>> a.index('p')
1
```
&nbsp;  
- 문자열 삽입
&nbsp;  
```python
>>> a = ","
>>> a.join('abcd')
a,b,c,d
```
&nbsp;  
- 대,소문자 변환
&nbsp;  
```python
>>> a = "hi"
>>> a.upper()
'HI'
>>> a = "HI"
>>> a.lower()
'hi'
```
&nbsp;  
- 공백 지우기  
lstrip은 왼쪽 공백을, rstrip은 오른쪽 공백을, strip은 문자열 양쪽에 있는 공백을 지운다.
&nbsp;  
```python
>>> a = " apple "
>>> a.strip()
apple
```
&nbsp;  
- 문자열 바꾸기
&nbsp;  
```python
>>> a = "Apple is delicious"
>>> a.replace('Apple', 'Banana')
Banana is delicious
apple
```
&nbsp;  
- 문자열 나누기
&nbsp;  
```python
>>> a = "Apple is delicious"
>>> a.split()
['Apple', 'is', 'delicious']
>>> a = "a:b:c:d"
>>> a.split(':')
['a', 'b', 'c', 'd']
```
&nbsp;  
