```python
words = []
dictionary = {}

n = int(input())
for i in range(n):
    string = input()
    words.append(string)

for word in words:
    for i in range(len(word)):
        if word[i] in dictionary:
            dictionary[word[i]] += 10**(len(word)-i-1)
        else:
            dictionary[word[i]] = 10**(len(word)-i-1)

values = sorted(dictionary.values(), reverse=True)
m = 9
answer = 0
for i in values:
    answer += m*i
    m -= 1
print(answer)

```
