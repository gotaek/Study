```python
board = input()
answer = ''
i = 0
while i < len(board):
    cnt = 0
    j = i
    if board[j] == '.':
        answer += '.'
        i += 1
        continue

    while j < len(board) and board[j] != '.':
        cnt += 1
        j += 1
    q, r = divmod(cnt, 4)
    answer += 'AAAA'*q
    if r % 2 == 0:
        answer += 'BB'*(r // 2)
    else:
        answer = -1
        break
    i += cnt


print(answer)
```
