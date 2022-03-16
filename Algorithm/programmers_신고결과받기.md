```python
from collections import defaultdict
def solution(id_list, report, k):
    answer = []
    declaration_from=defaultdict(set)
    declaration_to=defaultdict(set)
    mail_list=set([])
    for info in report:
        a,b=info.split()
        declaration_from[a].add(b)
        declaration_to[b].add(a)
        if len(declaration_to[b])>=k:
            mail_list.add(b)

    for id in id_list:
        result=declaration_from[id]&mail_list
        answer.append(len(result))
    return answer
 ```
