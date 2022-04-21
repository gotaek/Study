```python

class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        print(id(nums))
        k = k % len(nums)
        nums[:] = nums[-k:] + nums[:-k]
        print(id(nums))
```
