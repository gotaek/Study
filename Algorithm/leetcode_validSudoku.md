```python
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        return checkRows(board) and checkColumns(board) and checkSubBox(board)
    
def checkRows(board):
    for i in range(len(board)):
        dictionary={}
        for j in range(len(board[0])):
            current=board[i][j]
            if current!='.' and current in dictionary:
                return False
            else:
                dictionary[current]=1
    return True
        
def checkColumns(board):
    for i in range(len(board[0])):
        dictionary={}
        for j in range(len(board)):
            current=board[j][i]
            if current!='.' and current in dictionary:
                return False
            else:
                dictionary[current]=1
    return True

def checkSubBox(board):
    for i in range(0,len(board),3):
        for j in range(0,len(board[0]),3):
            dictionary={}
            for w in range(3):
                for x in range(3):
                    current=board[i+w][j+x]
                    if current !='.' and current in dictionary:
                        return False
                    else:
                        dictionary[current]=1
    return True
```
