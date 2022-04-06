```python

def solution(board, moves):
    bucket=[]
    answer=0
    for m in moves:
        for i in range(len(board)):
            if board[i][m-1]!=0:
                bucket.append(board[i][m-1])
                board[i][m-1]=0
                if len(bucket)>1:
                    if bucket[-1]==bucket[-2]:
                        bucket.pop(-1)
                        bucket.pop(-1)
                        answer+=2
                break
            
    return answer
```


문제만 잘 읽으면 쉽게 풀리는 문제인데 문제를 확실하게 안읽어서 삽질을 했다. 문제 잘 읽는 습관 좀 기르자
