```python
def divide(string):
    openBracket=0
    closeBracket=0
    for i in range(len(string)):
        if string[i]=='(':
            openBracket+=1
        else:
            closeBracket+=1
        if openBracket==closeBracket:
            return string[:i+1],string[i+1:]
          
def isBalanced(string):
    stack=[]
    for char in string:
        if char=='(':
            stack.append(char)
        else:
            if not stack:
                return False

            stack.pop()
    return True
        
def solution(p):

    if p=='':
        return ''

    u,v=divide(p)
    
    if isBalanced(u):
        return u+solution(v)
    else:
        answer='('
        answer+=solution(v)
        answer+=')'
        for p in u[1:len(u) - 1]:
            if p == '(':
                answer += ')'
            else:
                answer += '('

        return answer
```
