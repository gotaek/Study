```python
class Solution:
    def findClosestElements(self, arr: List[int], k: int, x: int) -> List[int]:
        ## Solution (1)
        
        # sorted_arr = sorted(arr, key = lambda num: abs(num-x))
        # return sorted(sorted_arr[:k])
        
        # ## Solution (2)
        # left = 0
        # right= len(arr)-1
        # while left+k <= right:
        #     if arr[right]-x >= x-arr[left]:
        #         right -=1
        #     else:
        #         left  +=1
        # return arr[left:right+1]
    
        ## Solution (3)
        left = 0
        right= len(arr)-k
        
        while left < right:                
            mid = (left+right)//2
            if x-arr[mid] >  arr[mid+k] - x: 
                left  = mid +1
            else:
                right = mid
        return arr[left:left+k]
  ```
  
  출처: https://leetcode.com/submissions/detail/740768158/?from=explore&item_id=945
