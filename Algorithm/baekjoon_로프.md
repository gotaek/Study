```python
n = int(input())
ropes = []
for i in range(n):
    ropes.append(int(input()))

ropes.sort()
answer = 0
sum_rope = sum(ropes)
for rope in ropes:
    candidate = rope*n
    if candidate <= sum_rope and answer < candidate:
        answer = candidate
    sum_rope -= rope
    n -= 1
print(answer)
```
