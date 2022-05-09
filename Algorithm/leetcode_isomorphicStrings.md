```python
from collections import defaultdict
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        dictS=defaultdict(list)
        dictT=defaultdict(list)
        for i,(s_char, t_char) in enumerate(zip(s,t)):
            dictS[s_char].append(i)
            dictT[t_char].append(i)
            if (s_char in dictS or t_char in dictT) and dictS[s_char]!=dictT[t_char]:
                return False

        return True
```
