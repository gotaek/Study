```python
t = int(input())
for i in range(t):
    n = int(input())
    trees = list(map(int, input().split()))
    trees.sort()
    level = 0
    left = trees[0]
    right = trees[1]
    for i in range(2, len(trees)):
        if i % 2 == 0:
            currentLevel = abs(left-trees[i])
            left = trees[i]
        else:
            currentLevel = abs(right-trees[i])
            right = trees[i]
        level = max(level, currentLevel)
    level = max(level, abs(left-right))
    print(level)
```
