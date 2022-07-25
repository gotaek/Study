```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        nums=sorted(nums1+nums2)
        length=len(nums)
        
        if length==0:
            return 0
        elif length%2==0:
            index1=length//2
            index2=index1-1
            return (nums[index1]+nums[index2])/2
        else:
            return float(nums[length//2])
```
