```python
from collections import Counter


def solution(topping):
    answer = 0
    toppingDict=Counter(topping)
    toppingSet=set()
    for i in topping:
        toppingSet.add(i)
        toppingDict[i]-=1
        if toppingDict[i]==0:
            toppingDict.pop(i)
        if len(toppingSet)==len(toppingDict):
            answer+=1
    return answer
  ```
  출처: https://velog.io/@minmong/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-Lv.2-%EB%A1%A4%EC%BC%80%EC%9D%B4%ED%81%AC-%EC%9E%90%EB%A5%B4%EA%B8%B0-Python-velog
