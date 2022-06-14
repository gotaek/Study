```python
from collections import Counter
w = input()
l = Counter(w)
odd = ''
for key, val in l.items():
    if val % 2 != 0:
        odd += key
if len(odd) > 1:  
    print("I'm Sorry Hansoo")
else:
    d = sorted(l.items())
    for j in d:
        print(j[0]*(j[1]//2), end='')
    print(odd, end='')
    for j in d[::-1]:
        print(j[0]*(j[1]//2), end='')
```
출처: https://asadal.github.io/2021-01-24-%E1%84%91%E1%85%A2%E1%86%AF%E1%84%85%E1%85%B5%E1%86%AB%E1%84%83%E1%85%B3%E1%84%85%E1%85%A9%E1%86%B7-%E1%84%86%E1%85%A1%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%80%E1%85%B5/
