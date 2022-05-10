```python
string = input()
subString = input()

lengthOfSubString = len(subString)

cnt = 0

while len(string) != 0:
    if string.find(subString) > -1:
        cnt += 1
        startIndex = string.find(subString)
        string = string[startIndex+lengthOfSubString:]
    else:
        break
print(cnt)
```
