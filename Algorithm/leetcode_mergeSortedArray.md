```python

class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        nums1[m:] = nums2[:n]
        nums1.sort()
````

이 방식처럼 sort함수를 사용하는 방법이 있겠지만 일일히 정렬하는 방법도 존재했다.

```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        if n < 1:
            return
        i = m - 1
        j = n - 1
        k = len(nums1) - 1
        while i > -1 and j > -1:
            if nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1
        while j > -1:
            nums1[k] = nums2[j]
            k -= 1
            j -= 1
```
이 방식은 하나씩 포인터를 내려가면서 nums1 배열과 nums2배열을 선택하며 정렬을 그때 그때 바로하는 방법이다.
