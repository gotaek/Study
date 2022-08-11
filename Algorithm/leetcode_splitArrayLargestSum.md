```python
def canSplit(nums, m, s):
            cnt, curr_sum = 1, 0
            for num in nums:
                curr_sum += num
                if curr_sum > s:
                    curr_sum = num
                    cnt += 1
            return cnt <= m

        left, right = 0, 0
        for num in nums:
            left = max(left, num)
            right += num

        while left <= right:
            mid = left + (right - left) / 2;
            if canSplit(nums, m, mid):
                right = mid - 1
            else:
                left = mid + 1
        return 
```

출처: https://github.com/yizhou-wang/LeetCode/blob/master/Python/split-array-largest-sum.py
