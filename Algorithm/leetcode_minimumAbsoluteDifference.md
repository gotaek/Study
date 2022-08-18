```python
class Solution:
    def minimumAbsDifference(self, arr: List[int]) -> List[List[int]]:
        arr.sort()
        gap=[]
        answer=[]
        for i in range(len(arr)-1):
            gap.append(arr[i+1]-arr[i])
        minimum=min(gap)
        
        for j in range(len(gap)):
            if gap[j]==minimum:
                answer.append([arr[j],arr[j+1]])
        return answer
```
