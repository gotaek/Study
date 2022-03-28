```python
class Solution:
    def thirdMax(self, nums: List[int]) -> int:
        first=-10000000000
        second=-10000000000
        third=-10000000000
        for num in nums:
            if num in [first,second,third]:
                continue
            if num>first :
                first,second,third=num,first,second
            elif num>second:
                second,third=num,second
            elif num>third:
                third=num
                
        if len(nums)>=3 and -10000000000 not in [first,second,third]:
            return third
        else:
            return first
```
