```python
import heapq
import sys
n = int(input())

timeOfLectures = []
queue = []
for _ in range(n):
    startTime, endTime = map(int, sys.stdin.readline().split())
    timeOfLectures.append((startTime, endTime))

timeOfLectures = sorted(timeOfLectures, key=lambda x: x[0])
heapq.heappush(queue, timeOfLectures[0][1])

for i in range(1, n):
    if queue[0] > timeOfLectures[i][0]:
        heapq.heappush(queue, timeOfLectures[i][1])
    else:
        heapq.heappop(queue)
        heapq.heappush(queue, timeOfLectures[i][1])

print(len(queue))

```
