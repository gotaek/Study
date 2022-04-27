```python
from collections import deque
def bfs(place):
    startP=[]

    for i in range(5):
        for j in range(5):
            if place[i][j]=='P':
                startP.append([i,j])


    for p in startP:
        que=deque([p])
        visited = [[0]*5 for i in range(5)]   
        distance = [[0]*5 for i in range(5)]  
        visited[p[0]][p[1]]=1

        while que:
            x,y=que.popleft()

            dx=[-1,0,1,0]
            dy=[0,1,0,-1]

            for i in range(4):
                nx=x+dx[i]
                ny=y+dy[i]
                if 0<=nx<5 and 0<=ny<5 and visited[nx][ny]==0:
                    if place[nx][ny]=='O':
                        que.append([nx,ny])
                        visited[nx][ny]=1
                        distance[nx][ny]=distance[x][y]+1
                    if place[nx][ny]=='P' and distance[x][y]<=1:
                        return 0
    return 1

def solution(places):
    answer = []
    for place in places:
        answer.append(bfs(place))


    return answer
```
