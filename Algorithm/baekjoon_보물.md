```python
n = int(input())
a = list(map(int, input().split()))
b = list(map(int, input().split()))
a.sort()

answer = 0
for i in a:
    best_elem = max(b)
    answer += i*best_elem
    b.remove(best_elem)

print(answer)
```
