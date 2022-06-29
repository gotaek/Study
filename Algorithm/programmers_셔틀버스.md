```python
def solution(n, t, m, timetable):
    answer=''

    for i in range(len(timetable)):
        string=timetable[i]
        hour,minute=string.split(':')
        timetable[i]=int(hour)*60+int(minute)
    timetable.sort()

    busTimes=[540+i*t for i in range(n)]

    index=0
    for busTime in busTimes:
        cnt=0
        while index<len(timetable) and timetable[index]<=busTime and cnt<m  :
            cnt+=1
            index+=1
        if cnt<m:
            answer=busTime
        else:
            answer=timetable[index-1]-1

    answer=str(answer//60).zfill(2)+":"+str(answer%60).zfill(2)
    return answer
```

출처: https://mjmjmj98.tistory.com/121
