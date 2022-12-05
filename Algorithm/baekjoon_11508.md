```python
n = int(input())
numbers = []
total = 0
for i in range(n):
    numbers.append(int(input()))

numbers.sort(reverse=True)

for i in range(n):
    if i % 3 != 2:
        total += numbers[i]
print(total)
```
