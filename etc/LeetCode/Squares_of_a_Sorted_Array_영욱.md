# Squares of a Sorted Array

Given an integer array ```nums``` sorted in **non-decreasing** order, return *an array of **the squares of each number** sorted in non-decreasing order*.

### Example:
```
Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].
```


### 접근
Sol 1. nums의 요소들을 for문으로 하나씩 꺼내면서 제곱을 해주고 리스트 정렬을 사용해주면 된다.
```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        return sorted(i ** 2 for i in nums)
```
**Runtime: 196ms, Memory: 16.1MB**

