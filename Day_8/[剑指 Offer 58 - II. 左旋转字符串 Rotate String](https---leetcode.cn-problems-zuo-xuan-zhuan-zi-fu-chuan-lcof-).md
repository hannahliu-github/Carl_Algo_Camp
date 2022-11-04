# [剑指 Offer 58 - II. 左旋转字符串 Rotate String](https://leetcode.cn/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)


#### Description:

Given an array, rotate the array to the left by k steps, where k is non-negative.


#### Understanding:

Given a string, rotate the chars inside the string to the left by k steps.

- Input: `"abcdefg", k = 2`
- Output: `"cdefgab"`

#### Approach `O(N) O(1)`:

Similar approach to LC 189. Rotate Array:


- first reverse s[:k]
	- 'bacdefg' 

- second, reverse s[k:]	
	- 'bagfedc'
	
-  third, reverse all 	
	- 'cdefgab'


#### Python:
```python
class Solution:
    def reverseLeftWords(self, s: str, k: int) -> str:
        """
        Do not return anything, modify nums in-place instead.
        """
        k = k % len(s)
        
        s = list(s)

        s[:k] = s[:k][::-1]
        s[k:] = s[k:][::-1]        
        s = s[::-1]

        return "".join(s)
        
        
"""
1. nettee LC. 189 Rotate Array
O(N)
O(1)
"""
```