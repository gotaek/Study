그냥 일반적으로 배열을 순회하며 문제를 풀려고 하였지만 출력 초과가 발생했다. 그래서 다른 블로그를 찾아보니 힙을 이용해야 했다.
```python
import heapq

N = int(input())

cardList = list(int(input()) for _ in range(N))
heapq.heapify(cardList)
result = 0


while len(cardList) != 1:
    num1 = heapq.heappop(cardList)
    num2 = heapq.heappop(cardList)
    Sum = num1 + num2
    result += Sum
    heapq.heappush(cardList, Sum)

print(result)
```
출처
https://kyoung-jnn.tistory.com/entry/%EB%B0%B1%EC%A4%801715%EB%B2%88%ED%8C%8C%EC%9D%B4%EC%8D%ACPython-%EC%B9%B4%EB%93%9C-%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84-%ED%81%90
