# Rotate Array

Given an array, rotate the array to the right by ```k``` steps, where ```k``` is non-negative.

### Example:
```
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

### 접근
리스트를 따로 나누고 뒤집어서 더하자.

```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        len_nums = len(nums)
        k = len_nums - (k % len_nums)
        
        nums[:] = nums[k:] + nums[:k]
```
**Runtime: 200ms, Memory: 25.5MB**
