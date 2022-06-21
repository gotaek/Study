```python
import heapq

n, m = map(int, input().split())
nums = [num for num in map(int, input().split())]
heapq.heapify(nums)

for _ in range(m):
    x = heapq.heappop(nums)
    y = heapq.heappop(nums)
    result = x+y

    for _ in range(2):
        heapq.heappush(nums, result)
print(sum(nums))
```
