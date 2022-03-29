```python
import sys

t = int(input())
for i in range(t):
    n = int(input())
    list = []
    for i in range(n):
        list.append(tuple(map(int, sys.stdin.readline().split())))
    list.sort()
    winner = list[0][1]
    cnt = 0
    for _, j in list:
        if j < winner:
            cnt += 1
            winner = j
    print(cnt+1)
```
