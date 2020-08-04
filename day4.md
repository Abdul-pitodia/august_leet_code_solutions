Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

Example 1:

Input: 16
Output: true
Example 2:

Input: 5
Output: false
Follow up: Could you solve it without loops/recursion?


Approach 1 - Using String

```
def isPowerOfFour(self, num: int) -> bool:
    #Power of 4 with string bit manipulation
    
        bin_num = bin(num)
        if (num == 1 ):
            return True
        else:
            if ((bin_num[2]=='1') and (len(bin_num[3:])%2==0) and (int(bin_num[3:])==0)):
                return True
            else:
                return False
                
                
```

Approach 2 - Using Bit manipulation

```
def isPowerOfFour(n): 
	
	count = 0
	
	# Check if there is only one 
	# bit set in n 
	if (n and (not(n & (n - 1)))): 
		
		# count 0 bits before set bit 
		while(n > 1): 
			n >>= 1
			count += 1
			print(n)
		
		# If count is even then return 
		# true else false 
		if(count % 2 == 0): 
			return True
		else: 
			return False

# Driver code 
test_no = 64
if(isPowerOfFour(64)): 
	print(test_no, 'is a power of 4') 
else: 
	print(test_no, 'is not a power of 4') 
  
  
```


Power of 2 Code -

```
  
        if ((num & (num-1) == 0 ) and num != 0):
            return True
        else:
            return False
            
```            
