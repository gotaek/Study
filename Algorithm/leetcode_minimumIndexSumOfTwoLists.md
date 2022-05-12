```python
class Solution:
    def findRestaurant(self, list1: List[str], list2: List[str]) -> List[str]:
        dictionary={}
        answer_list=[]
        for index,item in enumerate(list1):
            dictionary[item]=index
        
        min_index=20000
        for index,item in enumerate(list2):
            if item in dictionary:
                if dictionary[item]+index<min_index:
                    answer_list=[item]
                    min_index=dictionary[item]+index
                elif dictionary[item]+index==min_index:
                    answer_list.append(item)
        
        return answer_list

```
