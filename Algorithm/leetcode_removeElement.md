```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        
        pos = 0 
        
        for i in range(len(nums)):
            if nums[i] != val:
                
                temp = nums[pos]
                nums[pos] = nums[i]
                nums[i] = nums[pos]
                # nums[pos] = nums[i]
                pos+=1
        return pos
```
```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        for i in range(nums.count(val)):
            nums.remove(val)
        return len(nums)
   ```
 내 코드
 ```python
 class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        left,right=0,len(nums)-1
        while left<=right:
            if nums[left]==val:
                nums[left],nums[right]=nums[right],nums[left]
                right-=1
            else:
                left+=1
        return (len(nums[:right+1]))
  ```
