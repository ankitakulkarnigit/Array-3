# Array-3

## Problem1 Trap Rain Water (https://leetcode.com/problems/trapping-rain-water/)

Time: O(n) for finding max, then O(n-h) for left pass and O(n-h) for right pass so total O(n)
Space: O(1)

class Solution:
    def trap(self, height: List[int]) -> int:
        # find max height
        maxH = float('-inf')
        max_idx = 0
        area = 0
        for i in range(len(height)):
            if height[i] > maxH:
                maxH = height[i]
                max_idx = i

        # left -> max
        leftmax = 0
        l = 0
        while l < max_idx:
            l += 1
            if height[l] >= height[leftmax]:
                leftmax = l
            area += (height[leftmax]-height[l])

        # max <- right
        rightmax = len(height)-1
        r = len(height)-1
        while r > max_idx:
            r -= 1
            if height[r] >= height[rightmax]:
                rightmax = r
            area += (height[rightmax] - height[r])
        
        return area


## Problem2 H-Index (https://leetcode.com/problems/h-index/)


## Problem3  Rotate Array by K Places(https://leetcode.com/problems/rotate-array/)

