```python
n, k = tuple(map(int, input().split()))

answer = 0
while bin(n).count('1') > k:
    answer += 1
    n += 1

print(answer)
```
출처: https://fre2-dom.tistory.com/420
