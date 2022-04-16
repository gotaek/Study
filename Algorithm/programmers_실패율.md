```python
def solution(N, stages):
    answer=[]
    dict_stages={}

    length=len(stages)
    for i in range(1,N+1):
        if length>0:
            cnt=stages.count(i)
            dict_stages[i]=cnt/length
            length-=cnt
        else:
            dict_stages[i]=0

    dict_stages=dict(sorted(dict_stages.items(),key=lambda x:(-x[1],x[0])))
    answer=list(dict_stages.keys())
    return answer
```
