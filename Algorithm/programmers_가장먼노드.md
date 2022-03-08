```python
from collections import deque

def bfs(graph,visited,i):
    q=deque()
    q.append(i)
    visited[i]=1
    while q:
        cur=q.popleft()
        for j in graph[cur]:
            if visited[j]==0:
                q.append(j)
                visited[j]=visited[cur]+1
    
    
def solution(n, edge):
    answer = 0
    visited=[0*n for n in range(n+1)]
    graph=[[]for n in range(n+1)]
    for e in edge:
        graph[e[0]].append(e[1])
        graph[e[1]].append(e[0])
        
    bfs(graph,visited,1)
    
    max_visited=max(visited)
    cnt=0
    for i in range(n+1):
        if max_visited==visited[i]:
            cnt+=1
    return cnt
 ```
