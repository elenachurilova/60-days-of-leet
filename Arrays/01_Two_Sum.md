## 1. Two Sum

--------------------

> Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.\
You may assume that each input would have exactly one solution, and you may not use the same element twice.\
You can return the answer in any order.

> Input: nums = [2,7,11,15], target = 9\
Output: [0,1]\
Output: Because nums[0] + nums[1] == 9, we return [0, 1].

--------------------

## Solution: 

> ✏️ Pseudocode:

1. Initialize a dictionary ```seen``` to keep track of numbers (as keys) and indices (as values)
2. Loop over enumerated array (```array.enumerate```)
3. Difine how much you have to go to get the target == what number you need to match to your first iterative to get to the target? => Define ```remaining``` 
4. Check if ```remaining``` is in ```seen```
5. If yes, return your current iterator ```i``` and ```seen``` entry at the ```remaining``` key.
6. If not, add the current iterator to the dictionary 


> 👩🏼‍💻 Code

```    def twoSum(self, nums: List[int], target: int) -> List[int]:
       seen = {}
       for i, value in enumerate(nums):
           remaining = target - nums[i]
           
           if remaining in seen:
               return [i, seen[remaining]]
           else:
               seen[value] = i  
```

[Leetcode Original](https://leetcode.com/problems/two-sum)