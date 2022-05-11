```python
def solution(s):
    answer = []
    s=s[2:-2]
    s=s.split("},{")
    s=sorted(s,key= lambda x: len(x))
    tuples=[i.split(",") for i in s]
    for tuple in tuples:
        for j in tuple:
            if int(j) not in answer:
                answer.append(int(j))
    return answer

```
