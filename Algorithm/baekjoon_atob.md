```python
start, end = map(int, input().split())


def recursion(depth, num):
    double, plusedOne = num*2, int(str(num)+"1")

    if num == end:
        return depth
    elif num > end:
        return -1
    else:
        left = recursion(depth+1, double)
        right = recursion(depth+1, plusedOne)
        return max(left,right)


print(recursion(1, start))

```
