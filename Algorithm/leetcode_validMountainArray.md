지저분한 내 코드와는 다르게 너무 깔끔했다.

바로 아래는 내코드
```python
class Solution:
    def validMountainArray(self, arr: List[int]) -> bool:
        flag=[0]
        for i in range(1,len(arr)):
            if arr[i-1]<arr[i]:
                if flag[-1]==0:
                    flag.append(1)
                elif flag[-1]==1:
                    continue
                else:
                    return False
            elif arr[i-1]>arr[i]:
                if flag[-1]==1:
                    flag.append(2)
                elif flag[-1]==2:
                    continue
                else:
                    return False
            else:
                return False
        if flag==[0,1,2]:
            return True
````
```python
class Solution:
    def validMountainArray(self, arr: List[int]) -> bool:
        m = max(arr)
        mi = arr.index(m)
        a = arr[:mi+1]
        b = arr[mi:]
        
        return len(a) > 1 and len(b) > 1 and a == sorted(a) and b == sorted(b, reverse= True) and len(a) == len(set(a)) and len(b) == len(set(b))
  ```
