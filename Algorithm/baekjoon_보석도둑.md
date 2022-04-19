```python
import sys
import heapq

N, K = map(int, sys.stdin.readline().rstrip().split())
jewels = []
bags = []
for _ in range(N):
	M, V = map(int, sys.stdin.readline().rstrip().split())
	heapq.heappush(jewels, (M, V))

for _ in range(K):
	bags.append(int(sys.stdin.readline().rstrip()))
bags.sort()

rv = 0

jewels_candidate = []
for bag in bags:
	while jewels and jewels[0][0] <= bag: # 가벼운 가방부터 순회하기 때문에 한번 jewels_candidate로 간 보석은 계속 candidate에 해당한다.
		lightest_jewel = heapq.heappop(jewels)
		heapq.heappush(jewels_candidate, -lightest_jewel[1]) # 비싼 순으로 정렬. 지금 들어간 보석이면 다음 가방에서도 어차피 다 맞으니까 보석 가격만 max-heap 돌리면 됨. 

	if jewels_candidate:
		rv += -heapq.heappop(jewels_candidate)

print(rv)
```
