```python
n = int(input())
sides = list(map(int, input().split()))
answer = 0
if(n == 1):
    nums = sorted(sides)
    for i in range(0, 5):
        answer += nums[i]
else:
    sideOne = 4*(n-2)*(n-1)+(n-2)**2
    sideTwo = 4*(n-2)+4*(n-1)
    sideThree = 4

    sidesToUse = []
    for i in range(3):
        sidesToUse.append(min(sides[i], sides[5-i]))
    sidesToUse=sorted(sidesToUse)
    
    min1 = sidesToUse[0]
    min2 = min1+sidesToUse[1]
    min3 = min2+sidesToUse[2]

    answer = sideOne*min1+sideTwo*min2+sideThree*min3
print(answer)

```

출처:https://kkk4872.tistory.com/130
