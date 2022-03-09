이번 문제는 어떤 명제를 파악하고 구현하는데 꽤 애를 먹었다. 

그러니깐 

1. i한테 진 애들은 i한테 이긴 애들한테도 진 것이다.

2. i한테 이긴 애들은 i한테 진 애들한테도 이긴 것이다.

이 명제를 사용해 구현을 해야했다. 그래서 집합을 만들어 이기고 진 정보들을 표현해야했던 것이다. 
```python
from collections import defaultdict
def solution(n, results):
    answer = 0
    wins=defaultdict(set)
    loses=defaultdict(set)
    
    for r in results:
        wins[r[0]].add(r[1])
        loses[r[1]].add(r[0])
    
    for i in range(1,n+1):
        for loser in wins[i]:
            loses[loser].update(loses[i])
        for winner in loses[i]:
            wins[winner].update(wins[i])
    
    for i in range(1,n+1):
        if len(wins[i])+len(loses[i])==n-1:
            answer+=1
        
    return answer
 ```
출처:https://velog.io/@narastro/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EC%88%9C%EC%9C%84-Python
