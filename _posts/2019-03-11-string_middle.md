---
layout: post
title: level1. 가운데 글자 가져오기
categories:
- algorithm
---
#### 문제
단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.
&nbsp;  

#### 풀이
```python
def solution(s):
    answer = ''
    length = len(s)
    if length % 2 == 0:
        index = int(length / 2)
        answer = s[index - 1:index + 1]
        return answer
    else:
        index = int((length + 1) / 2)
        answer = s[index - 1]
        return answer
```

#### 다른 사람 풀이
```python
def string_middle(str):
    return str[(len(str)-1)//2:len(str)//2+1]
```    

#### 배운점
- // 는 나머지 후 소수점 아랫자리를 버리는 연산자 
- 문자열[시작번호:끝번호]라면 끝번호-1 까지 가져온다

---
출처  
<https://programmers.co.kr/learn/courses/30/lessons/12903>  
