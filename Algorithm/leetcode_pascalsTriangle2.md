```python
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        tri=[]
        for i in range(rowIndex+1):
            if i==0:
                tri.append([1])
            elif i==1:
                tri.append([1,1])
            else:
                temp=[]
                for j in range(i+1):
                    if j==0 or j==i:
                        temp.append(1)
                    else:
                        temp.append(tri[i-1][j-1]+tri[i-1][j])
                tri.append(temp)
        return(tri[-1])
```
