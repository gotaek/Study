```python
from collections import Counter

def solution(X, Y):
    answer = []
    dictX=dict(Counter(list(X)))
    for i in list(Y):
        if i in dictX:
            dictX[i]-=1
            answer.append(i)
            if dictX[i]==0:
                del dictX[i]
    if len(answer)==0:
        return "-1"
    else:
        answer.sort(reverse=True)
        answer=list(map(str,answer))
        if len(answer)==answer.count("0"):
            return "0"
        else:
            return "".join(answer)

    return answer
  ```
