## Container With Most Water (medium)
--------------------

> Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate (i, ai). n vertical lines are drawn such that the two endpoints of the line i is at (i, ai) and (i, 0). Find two lines, which, together with the x-axis forms a container, such that the container contains the most water. Notice that you may not slant the container.

![image](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg) 

> Input: height = [1,8,6,2,5,4,8,3,7]\
Output: 49\
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.

--------------------

## Solution: 


> ✏️ Pseudocode:
Using a two pointers technique
1. Establish pointers at the 0 and -1 indexes (first and last) elements in the list
2. Make a bucket to keep track of the max area
3. Iterate `while` your pointers don't cross and calculate the area per each iteration, recording it under `max_area`
(`height` is the lowest value out of two, `width` is the length of the array between two numbers)
4. Important! 
* if the value at your left pointer less than your the value at your right pointer, move your LEFT pointer --> 
* if the value at your right pointer less than your the value at your left pointer, move your RIGHT pointer <--

> 👩🏼‍💻 Code

```
def maxArea(height) -> int:
        
        p1 = 0
        p2 = len(height)-1
        max_area = 0

        while p1 < p2:
            high = min(height[p1], height[p2])
            wide = p2 - p1
            current_area = high*wide
            max_area = max(max_area, current_area)

            if height[p1] <= height[p2]:
                p1 += 1
            else:
                p2 -= 1

        return max_area
        
```

[Leetcode Original](https://leetcode.com/problems/container-with-most-water/)
