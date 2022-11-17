```python
from math import gcd
def getGcd(arr):
    g=arr[0]
    for i in range(1,len(arr)):
        g=gcd(g,arr[i])
    return g

def solution(arrayA, arrayB):
    res=0
    gcdA,gcdB=getGcd(arrayA),getGcd(arrayB)

    for i in arrayB:
        if i%gcdA==0:
            break

    else:
        res=max(res,gcdA)
    for j in arrayA:
        if j%gcdB==0:
            break
    else:
            res=max(res,gcdB)
    return res
```
