```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        last_index=len(arr)
        index=0
        max_num=0
        for i in range(last_index-1):
            if index>i:
                arr[i]=max_num
                continue
            max=0
            for j in range(i+1,last_index):
                if arr[j]>=max:
                    max=arr[j]
                    max_num=arr[j]
                    index=j
            arr[i]=max
        
        arr[-1]=-1
        return arr
```
모범 코드
```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        #initial max = -1
        #reverse iteration
        #new max = max(oldmax, arr[i])
        rightMax = -1
        for i in range(len(arr) - 1, -1, -1): #iterate in reverse order by 1
            newMax = max(rightMax, arr[i])
            arr[i] = rightMax
            rightMax = newMax
        return arr
        
```
