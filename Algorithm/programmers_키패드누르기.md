```python
def solution(numbers, hand):
    answer = ''

    leftHand='*'
    rightHand='#'
    for number in numbers:
        if number in [1,4,7]:
            leftHand=number
            answer+='L'
        elif number in [3,6,9]:
            rightHand=number
            answer+='R'
        else:
            leftDistance=calculateDistance(leftHand,number)
            rightDistance=calculateDistance(rightHand,number)

            if leftDistance<rightDistance:
                leftHand=number
                answer+='L'
            elif rightDistance<leftDistance:
                rightHand=number
                answer+='R'
            else:
                if hand=='right':
                    rightHand=number
                    answer+='R'
                else:
                    leftHand=number
                    answer+='L'
    return answer

def calculateDistance(src,tar):
    if src=='*':
        src_i,src_j=3,0
    elif src=='#':
        src_i,src_j=3,2
    elif src==0:
        src_i,src_j=3,1
    else:
        if src%3==0:
            src_i,src_j=src/3-1,2
        else:
            src_i,src_j=src//3,src%3-1

    if tar==0:
        tar_i,tar_j=3,1
    else:
        if tar%3==0:
            tar_i,tar_j=tar/3-1,2
        else:
            tar_i,tar_j=tar//3,tar%3-1
    return abs(src_i-tar_i)+abs(src_j-tar_j)
 ```
