```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        set_a=set(nums1)
        set_b=set(nums2)
        
        return list(set_a & set_b)

```
```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        s1, s2 = set(nums1), set(nums2)
        output = []
        for n in s1:
            if n in s2:
                output.append(n)
        return output
  ```
