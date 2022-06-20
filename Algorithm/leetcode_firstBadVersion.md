```python
# The isBadVersion API is already defined for you.
# def isBadVersion(version: int) -> bool:

class Solution:
    def firstBadVersion(self, n: int) -> int:
        l=1
        r=n+1
        while l<r:
            m=(l+r)//2
            if l==r:
                break
            elif isBadVersion(m)==False:
                l=m+1
            else:
                r=m
        if l!=n+1 a
```
