```python
t = int(input())
for _ in range(t):
    answer = 0
    n = int(input())
    prices = list(map(int, input().split()))

    max = prices[-1]
    for i in range(n-2, -1, -1):
        if max > prices[i]:
            answer += max-prices[i]
        else:
            max = prices[i]
    print(answer)
  ```
