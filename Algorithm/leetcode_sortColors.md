```python
class Solution:
    def sortColors(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        mid_value=1
        left,cur,right=0,0,len(nums)-1
        while cur<=right:
            if nums[cur]<mid_value:
                nums[cur],nums[left]=nums[left],nums[cur]
                cur+=1
                left+=1
            elif nums[cur]==mid_value:
                cur+=1
            else:
                nums[cur],nums[right]=nums[right],nums[cur]
                right-=1
```
