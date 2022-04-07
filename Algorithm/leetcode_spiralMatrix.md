```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        if not matrix:
            return []
        
        dr=[0,1,0,-1]
        dc=[1,0,-1,0]
        
        i,j,r,c=0,0,len(matrix),len(matrix[0])
        ans=[]
        
        cur=0
        
        for _ in range(r*c):
            ans.append(matrix[i][j])
            matrix[i][j]=""
            
            nr=i+dr[cur]
            nc=j+dc[cur]
            
            if matrix[(nr)%r][(nc)%c]=="":
                cur=(cur+1)%4
                
            i=i+dr[cur]
            j=j+dc[cur]
        return ans
```

출처:https://upcount.tistory.com/67

```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        
        sr, er = 0, len(matrix)
        sc, ec = 0, len(matrix[0])
        
        res = []
        while sr <= er and sc <= ec:
            if sr == er:
                break

            # l -> r
            for j in range(sc, ec):
                res.append(matrix[sr][j])
            sr += 1

            if sc == ec:
                break
            # u -> d
            for i in range(sr, er):
                res.append(matrix[i][ec-1])
            ec -= 1

            if sr == er:
                break
            # r -> l
            for j in range(ec-1, sc-1, -1):
                res.append(matrix[er-1][j])
            er -= 1

            if sc == ec:
                break            
            # d -> u
            for i in range(er-1, sr-1, -1):
                res.append(matrix[i][sc])
            sc += 1
        
        return res
   ```
