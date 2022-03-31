```python
def dominantIndex(self, nums: List[int]) -> int:
        first=nums[0]
        second=0
        length=len(nums)
        max_index=0
        if length==1:
            return 0
        else:
            for i in range(1,len(nums)):
                if nums[i]>first:
                    first,second=nums[i],first
                    max_index=i
                elif nums[i]>second:
                    second=nums[i]
            if second*2<=first:
                return max_index
            else:
                return -1
  ```
