```python
def move(x, y):

    for dx in dxl:
        nextX = x+dx
        if y+1 == c-1:
            return True
        if 0 <= nextX < r and board[nextX][y+1] != 'x' and visited[nextX][y+1] == False:
            visited[nextX][y+1] = True
            if move(nextX, y+1):
                return True
    return False


r, c = map(int, input().split())
answer = 0
board = []
visited = [[False] * c for _ in range(r)]
dxl = [-1, 0, 1]

for i in range(r):
    board.append([j for j in input()])


for i in range(r):
    if board[i][0] == '.':
        if move(i, 0):
            answer += 1
print(answer)
```
출처: https://suri78.tistory.com/187
