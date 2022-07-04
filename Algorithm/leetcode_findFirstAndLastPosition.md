```python
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        left=0
        right=len(nums)-1
        while left<=right:
            mid=(left+right)//2
            
            if nums[mid]==target:
                while nums[left]!=target:
                    left+=1
                while nums[right]!=target:
                    right-=1
                return [left,right]
            elif nums[mid]<target:
                left=mid+1
            else:
                right=mid-1
        return [-1,-1]
```
