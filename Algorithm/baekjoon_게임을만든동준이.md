```python
n = int(input())

scoreOfLevel = []
answer = 0

for _ in range(n):
    score = int(input())
    scoreOfLevel.append(score)

if len(scoreOfLevel) == 1:
    print(0)

prevScore = scoreOfLevel[-1]
for i in range(len(scoreOfLevel)-2, -1, -1):
    currentScore = scoreOfLevel[i]
    if currentScore >= prevScore:
        answer += currentScore-(prevScore-1)
        prevScore = prevScore-1
    else:
        prevScore = currentScore
print(answer)

```
