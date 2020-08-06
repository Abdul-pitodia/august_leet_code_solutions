Find All Duplicates in an Array

Given an array of integers, 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.

Find all the elements that appear twice in this array.

Could you do it without extra space and in O(n) runtime?

Example:

Input:
[4,3,2,7,8,2,3,1]

Output:
[2,3]


- O(N) TIME AND O(N) SPACE

```
        num_count = {}
        lst = []
        #print(nums)
        for i in range(len(nums)):
            j = 0
            if (nums[i] not in num_count.keys()):
                num_count[nums[i]] = j + 1
                #print(nums[i])
            else:
                count = 1
                num_count[nums[i]] = num_count[nums[i]] + count
        #print(num_count.items())
        for k,v in num_count.items():
            if (v==2):
                lst.append(k)
            
        return lst
        
        
```


- IN O(N) AND O(1) SPACE COMPLEXITY

```
#         ans = []
#         for num in nums:
#             if nums[abs(num)-1] < 0:
#                 ans.append(abs(num))
#             else:
#                 nums[abs(num)-1] *= -1
#         return ans


```
