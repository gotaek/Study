```python
def solution(order):
    answer = 0
    newOrder=[0]*(len(order)+1)
    for i in range(len(order)):
        newOrder[order[i]]=i+1
    target=1
    stack=[]

    for i in range(1,len(newOrder)):
        if newOrder[i]!=target:
            stack.append(newOrder[i])
        elif newOrder[i]==target:
            target+=1
            answer+=1
        if stack and stack[-1]==target:
            stack.pop()
            target+=1
            answer+=1


    while stack:
        if stack[-1]==target:
            stack.pop()
            target+=1
            answer+=1
        else:
            break

    return answer
  ```
