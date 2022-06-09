```python
from collections import defaultdict
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        frequent=defaultdict(int)
        answer=[]
        for num in nums:
            frequent[num]+=1
        
        sortedFreq=sorted(frequent.items(),key=lambda x:-x[1])
        
        for i in range(k):
            answer.append(sortedFreq[i][0])
        
        return answer
```
