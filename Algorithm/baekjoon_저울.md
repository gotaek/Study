```python
n = int(input())
num_list = [int(i) for i in input().split()]

num_list.sort()

target = 1

for num in num_list:
    if target < num:
        break
    else:
        target += num
print(target)
```
