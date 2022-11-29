```python
def solution(babbling):
    answer = 0
    possible=['aya','ye','woo','ma']
    
    for currentBabbling in babbling:
        stack=''
        prev=''
        for char in currentBabbling:
            stack+=char
            if prev!=stack and stack in possible:
                prev=stack
                stack=''
        if len(stack)==0:
            answer+=1
            
    return answer
```
