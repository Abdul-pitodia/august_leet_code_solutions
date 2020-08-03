Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

Note: For the purpose of this problem, we define empty string as valid palindrome.

Example 1:

Input: "A man, a plan, a canal: Panama"
Output: true
Example 2:

Input: "race a car"
Output: false


```

class Solution:
    def isPalindrome(self, s: str) -> bool:
        new_str = ''
        for i in range(len(s)):
            if (s[i].isalnum()):
                new_str += s[i]
            else:
                continue
        new_str = new_str.lower()
        test_str = new_str[::-1]
        print(test_str)
        print(new_str)
        
        if (test_str == new_str):
            return True
        else:
            return False
            
            
```      
