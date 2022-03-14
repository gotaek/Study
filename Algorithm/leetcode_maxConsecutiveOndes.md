```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        window=0
        max_window=0
        for i in range(len(nums)):
            if nums[i]==1:
                window+=1
            else:
                max_window=max(max_window,window)
                window=0
        max_window=max(max_window,window)
        return max_window
 ```
