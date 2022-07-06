```python
from collections import defaultdict
def solution(n, k, cmd):
    graph={i:[i-1,i+1] for i in range(n)}
    graph[0] = [None, 1]    
    graph[n - 1] = [n - 2, None]

    stack=[]
    answer=['O']*n
    pointer=k

    for command in cmd:
        alphabet=command[0]
        if alphabet=='C':
            answer[pointer]='X'
            prev,next=graph[pointer]
            stack.append([prev,pointer,next])

            if graph[pointer][1]==None:
                pointer=graph[pointer][0]
            else:
                pointer=graph[pointer][1]

            if prev==None:
                graph[pointer][0]=prev
            elif next==None:
                graph[pointer][1]=next
            else:
                graph[prev][1]=next
                graph[next][0]=prev
        if alphabet=='Z':
            prev, now, next = stack.pop()            
            answer[now] = 'O'            
            if prev == None:                
                graph[next][0] = now            
            elif next == None:                
                graph[prev][1] = now            
            else:                
                graph[next][0] = now                
                graph[prev][1] = now
        else:
            if alphabet=='U':
                targetCnt=int(command[2:])
                for _ in range(targetCnt):
                    pointer=graph[pointer][0]

        if alphabet=='D':
            targetCnt=int(command[2:])

            for _ in range(targetCnt):
                pointer=graph[pointer][1]    

    return "".join(answer)
  ```
