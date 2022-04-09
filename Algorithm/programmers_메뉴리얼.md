```python
from itertools import combinations
from collections import Counter
def solution(orders, course):
    answer=[]

    for c in course:
        candidates=[]
        for order in orders:
            for li in combinations(order,c):
                res=''.join(sorted(li))
                candidates.append(res)
        sorted_candidates=Counter(candidates).most_common()
        answer += [menu for menu, cnt in sorted_candidates if cnt > 1 and cnt == sorted_candidates[0][1]]


    return sorted(answer)
```


출처

https://programmers.co.kr/learn/courses/30/lessons/72411/solution_groups?language=python3&type=all
