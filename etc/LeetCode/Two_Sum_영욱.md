# Two Sum
Given an array of integers ```nums``` and an integer ```target```, return *indices of the two numbers such that they add up to ```target```.*  
You may assume that each input would have **exactly one solution**, and you may not use the *same* element twice.  
You can return the answer in any order.  

### Example:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

### 접근
시간복잡도 <-> 공간복잡도
#### Sol 1. brute-force: 이중 루프 n(n-1)/2
  - 시간 복잡도: O(n^2)
  - 공간 복잡도: O(1)

```python
# python
class Solution:
  def twoSum(self, nums: List[int], target: int) -> List[int]:
    for i in range(len(nums)):
      for j in range(i+1, len(nums)):
        if nums[i] + nums[j] == target:
          return [i, j]
```
**Runtime: 4064ms Memory: 14.8MB** 

#### Sol 2. hashMap: 루프를 한 번 돌면서 봤던 값은 hashMap에 넣음
  - 시간 복잡도: O(n)
  - 공간 복잡도: O(n)

```python
class Solution:
  def twoSum(self, nums: List[int], target: int) -> List[int]:
    dict = {} # {key: value} <- {value: index}
    for i, v in enumerate(nums): # i = index, v = value
      if target - v in dict:
        return [dict[target-v], i]
      else:
        dict[v] = i
```
**Runtime: 48ms Memory: 15.4MB** 
