```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        tri=[[1],[1,1]]
        if numRows==1:
            return [[1]]
        elif numRows==2:
            return tri
        else:
            for i in range(2,numRows):
                list=[]
                for j in range(i+1):
                    if j==0:
                        list.append(1)
                    elif j==i:
                        list.append(1)
                    else:
                        list.append(tri[i-1][j-1]+tri[i-1][j])
                tri.append(list)
            return tri
  ```
