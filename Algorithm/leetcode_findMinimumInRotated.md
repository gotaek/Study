```python
class Solution:
    def findMin(self, nums: List[int]) -> int:
        if len(nums)==1:
            return nums[0]
        
        left=0
        right=len(nums)-1
        
        if nums[right]>nums[0]:
            return nums[0]
        
        while left<=right:
            mid=left+(right-left)//2
            
            if nums[mid]>nums[mid+1]:
                return nums[mid+1]
            elif nums[mid-1]>nums[mid]:
                return nums[mid]
            
            if nums[mid]>nums[0]:
                left=mid+1
            elif nums[mid]<nums[0]:
                right=mid-1
  ```
