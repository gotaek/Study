```python
n, c = tuple(map(int, input().split()))
m = int(input())

info = []
for i in range(m):
    info.append(tuple(map(int, input().split())))

info.sort(key=lambda x: x[1])

box = [c]*(n+1)
answer = 0

for start, end, order in info:
    minimum = c
    for i in range(start, end):
        minimum = min(minimum, box[i])
    minimum = min(order, minimum)
    for j in range(start, end):
        box[j] -= minimum
    answer += minimum

print(answer)
```
출처: https://jaimemin.tistory.com/764
