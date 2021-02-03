## Check If Two String Arrays are Equivalent
--------------------

> Given two string arrays word1 and word2, return true if the two arrays represent the same string, and false otherwise.\
A string is represented by an array if the array elements concatenated in order forms the string.

> Input: word1 = ["ab", "c"], word2 = ["a", "bc"] \
Output: true \
> Input: word1 = ["a", "cb"], word2 = ["ab", "c"] \
> Output: false

--------------------

## Solution: 


> ✏️ Pseudocode:
1. Iterate over each item in both arrays and concatenate to two different strings
2. Compare strings


> 👩🏼‍💻 Code

```
def are_array_str_equal(word1, word2) -> bool:
        
        string_word_1 = ""
        string_word_2 = ""
        
        for word in word1:
            string_word_1 += word
            
        for word in word2:
            string_word_2 += word
            
        if string_word_1 != string_word_2:
            return False
        
        return True
```


[Leetcode Original](https://leetcode.com/problems/check-if-two-string-arrays-are-equivalent/)