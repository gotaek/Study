# 프로그래머스 징검다리 
## 이분 탐색

```python
def solution(distance, rocks, n):
    answer = 0
    rocks.sort()
    rocks.append(distance)
    left,right=0,distance

    while left<=right:
        mid=(left+right)//2

        current=0
        remove_cnt=0
        for rock in rocks:
            diff=rock-current
            if diff<mid :
                remove_cnt+=1
            else:
                current=rock


        if remove_cnt>n:
            right=mid-1
        else:
            left=mid+1
            answer=mid
    return answer

```

출처  
https://deok2kim.tistory.com/122
