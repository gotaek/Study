```python
def goto(x,cards,cnt):
    nextStep=cards[x]-1
    cards[x]=-1
    cnt+=1
    if cards[nextStep]==-1:
        return cnt
    return goto(nextStep,cards,cnt)

def solution(cards):
    answer = 0
    candidate1=0
    candidate2=0
    for i in range(len(cards)):
        cnt=0
        if cards[i]!=-1:
            cnt=goto(i,cards,cnt)
            newList=[candidate1,candidate2,cnt]
            newList.sort(reverse=True)
            candidate1,candidate2=newList[0],newList[1]

    answer=candidate1*candidate2
    return answer
  ```
