## Trapping Rain Water (hard)
--------------------

> Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.

![image](https://assets.leetcode.com/uploads/2018/10/22/rainwatertrap.png)

> Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]\
Output: 6\
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.

--------------------

## Solution: 

> ✏️ Pseudocode:
1. Set two pointers at the very sides of the array: 0 and -1
2. We need the following containers  
    1. containers for the maximum seen height on the left and right (max_left and max_right)
    2. container for collected water (this is our return val) 
3. Iterate while two pointers haven't crossed:
* find which pointer's value is smaller and compare it to the corresponing side's max_height (max_left or max_right)
* if the value is less than side's max height, update the water container with side's max height - pointer's value
* if side's max height is smaller than pointer's value, update side's max height to the value of that pointer

> 👩🏼‍💻 Code

``` 
def trapping_water_optimal(height):
    pl = 0
    pr = len(height) - 1
    max_left, max_right = 0, 0
    total_water = 0

    while pl < pr:
        if height[pl] <= height[pr]:
            if height[pl] <= max_left:
                total_water += max_left - height[pl]
            else:
                max_left = height[pl]
            pl += 1
        else:
            if height[pr] <= max_right:
                total_water += max_right - height[pr]
            else:
                max_right = height[pr]
            pr -= 1

    return total_water
```

[Leetcode Original](https://leetcode.com/problems/trapping-rain-water/)