```python
import heapq
import sys

read = sys.stdin.readline

n = int(read().strip("\n"))
datas = []
queue = []
answer = 0
for i in range(n):
    datas.append(tuple(map(int, read().strip("\n").split())))

datas.sort()

for deadLine, lamen in datas:
    heapq.heappush(queue, lamen)
    if deadLine < len(queue):
        heapq.heappop(queue)
print(sum(queue))
```
출처: https://jokerldg.github.io/algorithm/2021/06/22/cup-noodle.html
