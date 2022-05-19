```python
from collections import defaultdict
class Solution:
    def firstUniqChar(self, s: str) -> int:
        dictionary=defaultdict(int)
        for char in s:
            dictionary[char]+=1
        dictionary=dict(dictionary)
        
        for i in range(len(s)):
            if s[i] in dictionary and dictionary[s[i]]==1:
                return i
        return -1
  ```
