```python
from collections import defaultdict
class Solution:
    def fourSumCount(self, nums1: List[int], nums2: List[int], nums3: List[int], nums4: List[int]) -> int:
        cnt=0
        dictionary=defaultdict(int)
        for n1 in nums1:
            for n2 in nums2:
                dictionary[n1+n2]+=1
        for n3 in nums3:
            for n4 in nums4:
                temp=-n3-n4
                if temp in dictionary:
                    cnt+=dictionary[temp]
        return(cnt)
  ```
