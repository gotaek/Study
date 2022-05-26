```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        dictionary={}
        for index,num in enumerate(nums):
            if num in dictionary and index-dictionary[num]<=k:
                return True
            else:
                dictionary[num]=index
        return False
```
