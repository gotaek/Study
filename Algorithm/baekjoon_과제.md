```python
  n = int(input())
  homeworks = []
  schedule = [False]*1001
  for i in range(n):
      homeworks.append(tuple(map(int, input().split())))


  homeworks = sorted(homeworks, key=lambda x: (-x[1]))

  total = 0

  for homeworkDeadline, homeworkScore in homeworks:
      i = homeworkDeadline
      while i > 0:
          if schedule[i] == False:
              schedule[i] = True
              total += homeworkScore
              break
          i -= 1

  print(total)
```
