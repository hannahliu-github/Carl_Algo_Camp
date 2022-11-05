# [Offer 05. Replace Spaces](https://leetcode.cn/problems/ti-huan-kong-ge-lcof/)


#### Description:

请实现一个函数，把字符串 s 中的每个空格替换成 `"%20"`。


#### Understanding:

Given a list of string, replace the spaces into `"%20"`:

- `s` = `"We are happy."`
- `Output`: `"We%20are%20happy."`



#### Approach `O(N) O(1)`:
- Construct a list based on the string length and extend the list to be able to contain all characters, then loop backwards to reduce the TC from `O(N^2)` to `O(N)`.

- Use two pointers. Similar logic to `LC. 27 Remove Elements`.
	- One is to `read` the original string. 
	- One is to `fill in` the correct chars for the return res. 


#### Python:
```python
class Solution:
    def replaceSpace(self, s: str) -> str:

        cnt = s.count(' ')
        print(cnt)

        res = list(s)
        res.extend([' '] * cnt * 2)

        left, right = len(s) - 1, len(res) - 1

        while left >= 0:

            if s[left] == ' ':

                res[right - 2: right + 1] = '%20'

                right -= 3

            else:
                res[right] = s[left]

                right -= 1

            left -= 1

        return ''.join(res)
```