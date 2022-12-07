```python
t = int(input())
i = 0
while i < t:
    n, m = tuple(map(int, input().split()))
    numbers = [False]*(n+1)
    ranges = []
    answer = 0
    for j in range(m):
        ranges.append(tuple(map(int, input().split())))

    ranges.sort(key=lambda x: x[1])

    for start, end in ranges:
        for k in range(start, end+1):
            if numbers[k] == False:
                numbers[k] = True
                answer += 1
                break
    print(answer)
    i += 1
```
