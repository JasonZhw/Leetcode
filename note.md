# 2025.1.13
2270. number of ways to spilt array
简单的使用枚举法

class Solution:
    def waysToSplitArray(self, nums: List[int]) -> int:
        n, left, right = len(nums), 0, sum(nums)
        ans = 0
        for i in range(n - 1):
            left += nums[i]
            right -= nums[i]
            if left >= right:
                ans += 1
        return ans

notes：we just need to enumerate all the spilt positions and find the legal spilts. 
specifically, use left and right to represent the sum of all elements on the left and right sides of the spilt,respectively
initially, left=0,and the value of the right is the sum of all element in the given array. we enumerate each spilt postion from small to large. when we enumerate to position i, we add nums[i] to left and subtract num[i] from right. so that we can compare these two values if left>right then we find a legal spilt postiion.

# 2025.1.24
3065. Minimum Operations to Exceed threshold Value 1
简单的遍历
class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        m =0
        for num in nums:
            if k > num:
                m+=1
        return m

(dynamic programming)
70. Climbing Stairs
class Solution:
    def climbStairs(self, n: int) -> int:
        dp=[0]*(n+1)
        dp[0]=1
        dp[1]=1
        for i in range(2,n+1):
            dp[i]=dp[i-1]+dp[i-2]
        return dp[n]

        
        
