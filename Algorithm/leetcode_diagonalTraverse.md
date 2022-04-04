```python
class Solution:
    def findDiagonalOrder(self, mat: List[List[int]]) -> List[int]:
        dic = defaultdict(list)
        I = len(mat)
        
        for i in range(I):
            for j in range(len(mat[i])):
                dic[i+j].append(mat[i][j])
                
        res = []
        
        for k in sorted(dic.keys()):
            if k%2==0:
                res.extend(dic[k][::-1])
            else:
                res.extend(dic[k])
            
        return res
                    
```
