```python
class Solution:
    def smallestTrimmedNumbers(self, nums: List[str], queries: List[List[int]]) -> List[int]:
        answer=[]
        for k,t in queries:
            arr=[]
            for i,x in enumerate(nums):
                arr.append((int(x[-t:]),i))
            arr.sort()
            answer.append(arr[k-1][1])
        return answer
```
