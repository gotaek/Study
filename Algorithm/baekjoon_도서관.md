```python
answer = 0
positive = []
negative = []
maxLocation = 0

n, m = tuple(map(int, input().split()))
locations = list(map(int, input().split()))
for location in locations:
    if location > 0:
        positive.append(location)
    else:
        negative.append(location)
    if abs(location) > abs(maxLocation):
        maxLocation = location

positive.sort()
negative.sort()

for i in range(0, len(negative), m):
    if negative[i] != maxLocation:
        answer += abs(negative[i])
for j in range(len(positive)-1, -1, -m):
    if positive[j] != maxLocation:
        answer += positive[j]

answer *= 2
answer += abs(maxLocation)

print(answer)
```
