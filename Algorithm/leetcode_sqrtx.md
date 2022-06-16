```python
class Solution:
    def mySqrt(self, x: int) -> int:
        left=0
        right=x

        while left<=right:
            mid=(left+right)//2
            result=mid**2
            if result==x:
                return mid
            elif result>x:
                right=mid-1
            else:
                left=mid+1
        return right
```
