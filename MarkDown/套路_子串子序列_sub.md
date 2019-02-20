### Substring
Longest Substring Without Repeating Characters `sliding window 找最长`                          
Longest Substring with At Most Two Distinct Characters `sliding window 找最长`                          
Longest Substring with At Most K Distinct Characters  `sliding window 找最长`                           
**Substring with Concatenation of All Words**                            
Minimum Window Substring covering T  `sliding window 找最短`                          

Longest Palindromic Substring  `dp[i][j]: s[@i..@j] is panlidromic`                          
Count Palindromic Substrings   `dp[i][j]: s[@i..@j] is panlidromic`                          
Longest Valid Parentheses  `dp[i] for s[..@i]` `前左 ?()` `前右 ??(--))`         

Count Binary Substrings (equal number of consecutive 1's and 0's)  `group 00/111/00 => 2/3/2`                       
Unique Substrings in Wraparound String  `group zabcfab => zabc/f/ab`                         

Longest Substring with At Least K Repeating Characters  `用少于K个的字母分割`                         
**Repeated Substring Pattern** `divisible` `kmp`                          

### Subarray
Subarray Product Less Than K  `sliding window 计数`                           
Shortest Subarray Sum >= K (no negative) `sliding window 找最短`                            
Longest Increasing Subarray `sliding window 找最长`      

Maximum Subarray Sum  `dp[i]: maximum sum for n[..@i]`                           
Maximum Sum Circular Subarray `两种情况: max_subarray_sum; all_sum - min_subarray_sum`                           
Maximum Product Subarray  `dp, 注意负负得正`                           

Count Subarray Sum = K `S[j] - x == k` `cumsum2count`                          
Longest Subarray Sum = K  `S[j] - x == k` `cumsum2leftmost`                                                   

Maximum Subarray Sum <= K  `cumsum[j] - x <= k` `bisect, O(nlogn)`            
Minimum Subarray Sum >= K  `cumsum[j] - x >= k` `bisect, O(nlogn)`            
Shortest Subarray Sum >= K `cumsum[j] - x >= k` **`deque as solution space`**                          
       
Shortest Unsorted Continuous Subarray `从左往右找连续最大A[i]，从右往左找连续最小A[j]，求A[i..j]最小最大，以此掐头去尾`                           

**Subarray Sum Multiples of K**                         


**Maximum Sum of 3 Non-Overlapping Subarrays**                           
**Maximum Length of Repeated Subarray**                          
**Sum of Subarray Minimums**                             
**Bitwise ORs of Subarrays**                             
**Number of Subarrays with Bounded Maximum**                             
**Binary Subarrays With Sum**                            
**Maximum Average Subarray I**                           
**Maximum Average Subarray II**                          
             
             
### Sub-Rectangle

Max Rectangle Sum `max subarray sum` `left,right,dp`       
Max Rectangle Sum <= K  `max sumarray sum <= k` `left,right,cumsum-bisect`       
Smallest Rectangle Enclosing Black Pixels `遍历` `1D投影 + binary search`                                  
**Maximum Rectangular Area in Histogram**         
**Maximal Rectangle containing only 1's**      
**Number Of Corner Rectangles**        

### Subsequence
Is Subsequence  `双指针` `把t表示为char2idxs, 二分搜索`                        
Number of Matching Subsequences `char2idxs: 二分搜索`                        

Longest Increasing Subsequence  `dp[i], longest of n[..@i]` `最小尾数: 6 1 3 4 2 5 7 => 1(6) 2(3) 4 5 7`            
Increasing Subsequences  `dfs + backtracking`                       


Number of Longest Increasing Subsequence  `dp[i], solution of n[..@i]`                          

**Count Palindromic Subsequences**  `dp[i][j], solution of s[i..j]` `去重case`                          
Longest Palindromic Subsequence  `dp[i][j]: longest of s[i..j]` `s[i]==s[j]?`                      




**Sum of Subsequence Widths**  `sort + math`                         
**Split Array into Consecutive Subsequences**              
**Increasing Triplet Subsequence**                          
**Longest Harmonious Subsequence**                          
**Longest Uncommon Subsequence I**           
**Longest Uncommon Subsequence II**                         


**Minimum Window Subsequence**  `dp`                        


Length of Longest Fibonacci Subsequence  `dp`                       

Wiggle Subsequence  `dp`                        


Distinct Subsequences I `dp`                         
Distinct Subsequences II  `dp`                          
  

Arithmetic Slices II - Subsequence `dp`                         

### 无序 subsequence
longest consecutive sequence `Union Find`       
longest arithmetic sequence        