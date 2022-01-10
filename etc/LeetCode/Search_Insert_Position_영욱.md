# Search Insert Position

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with ```O(log n)``` runtime complexity.

### Example:
```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

### 접근
O(log(n))의 시간 복잡도를 가지며 nums라는 리스트에서 target을 탐색하는 것이므로 이진탐색 문제이다.

```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        start = 0
        end = len(nums) - 1
        
        while start <= end:
            mid = (start + end) // 2
            
            if nums[mid] == target:
                return mid
            elif target > nums[mid]:
                start = mid + 1
            else:
                end = mid - 1
        
        return start
```
**Runtime: 40ms, Memory: 14.9MB**
