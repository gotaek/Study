```python
from collections import Counter
def solution(want, number, discount):
    answer = 0
    for i in range(len(discount)-9):
        currentDiscount=Counter(discount[i:i+10])
        for j in range(len(want)):
            production=want[j]
            count=number[j]
            if production not in currentDiscount or currentDiscount[production]<count:
                break
        else:
            answer+=1
    return answer
```
