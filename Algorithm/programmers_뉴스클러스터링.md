```python
def solution(str1, str2):
    answer = 0
    str1=str1.upper()
    str2=str2.upper()
    str1_list=[]
    str2_list=[]
    for i in range(len(str1)-1):
        candidate=str1[i]+str1[i+1]
        if candidate.isalpha():
            str1_list.append(candidate)
        else:
            continue
    for j in range(len(str2)-1):
        candidate=str2[j]+str2[j+1]
        if candidate.isalpha():
            str2_list.append(candidate)
        else:
            continue
    cnt=0  
    
    common=[]
    for str1_item in str1_list:
        if str1_item in str2_list:
            str2_list.remove(str1_item)
            common.append(str1_item)

    str1_length=len(str1_list)
    str2_length=len(str2_list)
    cnt=len(common)
    total=str1_length+str2_length
    if total==0:
        return 1*65536
    else:
        return int(65536*(cnt/total))
    return answer
```
