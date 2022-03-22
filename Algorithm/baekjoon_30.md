```python
n = input()

nums = list(map(int, n))
best = int("".join(sorted(list(map(str, nums)), reverse=True)))

if best % 30 == 0:
    print(best)
else:
    print(-1)
```
