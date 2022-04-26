```python
from collections import deque
n = int(input())

numbers = []
for i in range(n):
    numbers.append(int(input()))
numbers = sorted(numbers, reverse=True)

positive = deque([])
negative = deque([])
zero = deque([])
one = deque([])
answer = 0

for number in numbers:
    if number == 0:
        zero.append(0)
    elif number == 1:
        one.append(1)
    elif number > 1:
        positive.append(number)
    else:
        negative.append(number)


for i in range(len(positive)//2):
    answer += positive.popleft()*positive.popleft()

for j in range(len(negative)//2):
    answer += negative.pop()*negative.pop()

while negative and zero:
    answer += zero.pop()*negative.pop()
answer += sum(positive)+sum(negative)+sum(zero)+sum(one)

print(answer)
```
