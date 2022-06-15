```python
from itertools import combinations

def solution(relation):
    answer = 0
    len_col=len(relation)
    len_row=len(relation[0])

    superKeys=[]
    combinationList=[]

    for i in range(1,len_row+1):
        combinationList+=list(combinations(range(len_row),i))
    for combination in combinationList:
        dict={}

        for i in range(len_col):
            key=''
            for c in combination:
                key+=relation[i][c]
            if key in dict:
                break
            else:
                dict[key]=1
        if len_col==len(dict):
            superKeys.append(combination)
    answer=set(superKeys)
    for i in range(len(superKeys)):
        for j in range(i+1,len(superKeys)):
            if len(superKeys[i])==len(set(superKeys[i])&set(superKeys[j])):
                answer.discard(superKeys[j])



    return len(answer)
```
