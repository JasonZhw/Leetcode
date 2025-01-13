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
