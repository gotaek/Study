```python
def solution(gems):
    answer = []
    setlen = len(set(gems))
    gemdict = {}

    start = 0 
    end = 0 
    sect = len(gems)+1

    while end < len(gems): 
        if gems[end] not in gemdict: 
            gemdict[gems[end]] = 1
        else: # 기존에 존재하는 보석
            gemdict[gems[end]] += 1

        end += 1 #보석을 새로 추가했으니 end칸 한 칸 뒤로

        if len(gemdict) == setlen: 
            while start < end:
                if gemdict[gems[start]] > 1: 
                    gemdict[gems[start]] -= 1 
                    start += 1  # start칸을 뒤로 한칸 이동
                elif end-start < sect: # 지정한 구간보다 현재 구간이 짧으면
                    sect = end-start # 지정한 구간 바꿔주기
                    answer = [start+1, end]
                    break
                else:
                    break

    return answer
  ```
  https://hongcoding.tistory.com/66
