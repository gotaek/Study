```python
n, k = tuple(map(int, input().split()))

string = list(input().rstrip())
answer = 0

for i in range(len(string)):
    if string[i] == 'P':
        index = i
        for j in range(index-k, index+k+1):
            if 0 <= j < n and string[j] == 'H':
                answer += 1
                string[j] = "none"
                break

print(answer)
```
