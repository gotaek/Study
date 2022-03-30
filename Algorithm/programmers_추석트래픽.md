```python
def solution(lines):
    start_time=[]
    end_time=[]
    answer=0
    for t in lines:
        time = t.split(" ")
        start_time.append(get_start_time(time[1],time[2]))
        end_time.append(get_time(time[1]))
    for i in range(len(lines)):
        cur_end_time=end_time[i]
        cnt=0
        for j in range(i,len(lines)):
            if cur_end_time+1000>start_time[j]:
                cnt+=1
        answer=max(answer,cnt)
    return answer

def get_time(time):
    hour = int(time[:2]) * 3600
    minute = int(time[3:5]) * 60
    second = int(time[6:8])
    millisecond = int(time[9:])
    return (hour + minute + second) * 1000 + millisecond

def get_start_time(time, duration_time):
    n_time = duration_time[:-1]
    int_duration_time = int(float(n_time) * 1000)
    return get_time(time) - int_duration_time + 1
```

출처: https://velog.io/@mrbartrns/%ED%8C%8C%EC%9D%B4%EC%8D%AC-1%EC%B0%A8%EC%B6%94%EC%84%9D-%ED%8A%B8%EB%9E%98%ED%94%BD-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4-%EB%A0%88%EB%B2%A83
