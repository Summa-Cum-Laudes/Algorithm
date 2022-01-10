# First_Bad_Version

You are a product manager and currently leading a team to develop a new product. Unfortunately, the latest version of your product fails the quality check. Since each version is developed based on the previous version, all the versions after a bad version are also bad.

Suppose you have ```n``` versions ```[1, 2, ..., n]``` and you want to find out the first bad one, which causes all the following ones to be bad.

You are given an API ```bool isBadVersion(version)``` which returns whether ```version``` is bad. Implement a function to find the first bad version. You should minimize the number of calls to the API.

### Example:
```
Input: n = 5, bad = 4
Output: 4
Explanation:
call isBadVersion(3) -> false
call isBadVersion(5) -> true
call isBadVersion(4) -> true
Then 4 is the first bad version.
```

### 접근
versions의 범위가 n으로 주어져 있고 그 중 특정 타겟값 bad값을 찾아내는 것이므로 이진탐색을 이용한 문제이다.  
탐색의 시작 지점과 종료 지점을 정하고 그 중간 지점을 mid로 둔다.  
mid값이 타겟값보다 이후에 있다면, 시작 지점을 mid로 옮기고 반대라면 종료지점을 mid로 둔다.

```python
class Solution:
    def firstBadVersion(self, n):
        """
        :type n: int
        :rtype: int
        """

        start = 1
        end = n
        while start < end:
            mid = start + (end - start)//2
            if isBadVersion(mid):
                end = mid
            else:
                start = mid + 1
        return start
                
```

**Runtime: 20ms, Memory: 14.2MB**
