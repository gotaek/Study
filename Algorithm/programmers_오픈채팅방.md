```python
def solution(record):
    answer = []
    name_dict={}
    for r in record:
        new_r=r.split()
        command=new_r[0]
        uid=new_r[1]
        if command=="Leave":
            continue
        name=new_r[2]
        if command=="Enter":
            name_dict[uid]=name
        else:
            name_dict[uid]=name
    for r in record:
        new_r=r.split()
        command=new_r[0]
        uid=new_r[1]
        if command=="Leave":
            answer.append(f'{name_dict[uid]}님이 나갔습니다.')
        elif command=="Enter":
            answer.append(f'{name_dict[uid]}님이 들어왔습니다.')
    return answer
 ```
