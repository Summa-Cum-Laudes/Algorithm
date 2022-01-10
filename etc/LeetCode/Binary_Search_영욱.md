# Binary Search
Given an array of integers ```nums``` which is sorted in ascending order, and an integer ```target```, write a function to search ```target``` in nums.  
If ```target``` exists, then return its index. Otherwise, return -1.  
You must write an algorithm with ```O(log n)``` runtime complexity.


### Example:
```
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
```

### 접근
시간 복잡도: O(log(n))
이진 탐색을 사용해야한다.
#### While
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        start, end = 0, len(nums)

        while start < end:
            mid = ((end - start) // 2) + start
            if nums[mid] == target:
                return mid
            elif nums[mid] > target:
                end = mid
            elif nums[mid] < target:
                start = mid + 1
        return -1
```
**Runtime: 321ms, Memory: 15.7MB**
#### 재귀
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        def binary_search(start, end):
          if start <= end:
            mid = (end + start) // 2
            if nums[mid] == target:
              return mid
            elif nums[mid] < target:  
              return binary_search(mid + 1, end)
            elif nums[mid] > target:
              return binary_search(start, mid-1)
          else:
            return -1
        return binary_search(0, len(nums)-1)
```
**Runtime: 228ms, Memory: 23MB**
