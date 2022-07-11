```python
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        left=0
        right=num
        
        while left<=right:
            mid=(left+right)//2
            curNum=mid**2
            if curNum==num:
                return True
            elif curNum<num:
                left=mid+1
            else:
                right=mid-1
        return False
```
