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

Longest Increasing Subarray `easy` `two poinster`      
**Shortest Unsorted Continuous Subarray** [`stack: leftmost/rightmost poped`](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/solution/)                           
**Sum of Subarray Minimums** [`stack: prev_larger, next_larger`]                 

#### `subarray sum (没有负数)`
Shortest Subarray Sum >= K (没有负数) `sliding window 找最短`                            
Count Subarray Product <= K (全正数)  `sliding window 计数`                           

#### `subarray sum (有负数)`

Maximum Subarray Sum  `dp[i]: maximum sum for n[..@i]`                           
Maximum Subarray Sum (Circular) `两种情况: max_subarray_sum; all_sum - min_subarray_sum`                           
Maximum Subarray Product  `dp, 注意负负得正`                           

Longest Subarray Sum = K  `Sj - Si == k` `leftmost i, Si == Sj - k` `Hash<cumsum, leftmost>`                                                   
Count Subarray Sum = K `Sj - Si == k` `count i, Si == Sj - k` `Hash<cumsum, count>`                          
Count Subarray Sum Divisible by K `(Sj - Si) % k == 0` `count i, Si % k == Si % k`                        
Maximum Subarray Sum <= K  `Sj - Si <= k` `smallest Si >= Sj - k ` `SortedSet<cumsum>, binary search`            
Minimum Subarray Sum >= K  `Sj - Si >= k` `largest Si <= Sj - k` `SortedSet<cumsum>, binary search`            
**Shortest Subarray Sum >= K (有负数)** `Sj - Si >= k` `rightmost i, Si <= Sj - k` [**`mono queue as solution space`**](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/discuss/143726/C%2B%2BJavaPython-O(N)-Using-Deque)                          

##### `没做`

**Maximum Sum of 3 Non-Overlapping Subarrays**                           
**Maximum Length of Repeated Subarray**                          

**Bitwise ORs of Subarrays**                             
**Number of Subarrays with Bounded Maximum**                             
**Binary Subarrays With Sum**                            
**Maximum Average Subarray I**                           
**Maximum Average Subarray II**                          

             
### Sub-Rectangle  (Subarray 2d) (PrefixSum, Row_ij压缩投影, 1D 算法)

#### `sub-rectangle sum (带负数)`
Max Rectangle Sum (带负数) [`Row_ij压缩`  `max subarray sum``dp[i]`]()        
Max Rectangle Sum <= K (带负数) [`Row_ij压缩` `max subarray sum <= k``sorted_set(cumsum)`](https://leetcode.com/problems/max-sum-of-rectangle-no-larger-than-k/discuss/445540/Python-bisect-solution-(960ms-beat-71.25))        

Count Rectangle Sum = K (Number of Submatrices That Sum to Target) [`prefix sum` `Row_ij压缩` `count subarray sum = K` `HashMap<cumsum, count>`](https://leetcode.com/problems/number-of-submatrices-that-sum-to-target/discuss/344440/Simple-Python-DP-solution)

Maximal Rectangle containing only 1's `Row 0 to i, 加(plus)投影 + mono stack`     
Count Rectangles containing only 1's `Row i to j, 与(and)投影, 1d DP`      

Maximal Square containing only 1's `dp[i][j]`     
Count Squares containing only 1's `sum(dp[i][j])`      

Smallest Rectangle Enclosing Black Pixels [`或(or)投影 + binary search`](https://leetcode.com/problems/smallest-rectangle-enclosing-black-pixels/solution/)        
                          
Number Of Corner Rectangles [`Row i & j, 与(&)投影, count 1's`] [`for row: for c1: for c2: if row[c1]== row[c2]==1:` `count += corner[c1][c2], corner[c1][c2]+1`](https://leetcode.com/problems/number-of-corner-rectangles/solution/)       



### Subsequence
Is Subsequence  `双指针` `把t表示为char2idxs, 二分搜索`                        
Number of Matching Subsequences `char2idxs: 二分搜索`                        

**Minimum Window Subsequence**  `S:a(bcde)bdde, T:bde` [`two pointer`](https://leetcode.com/submissions/detail/289564316/)                        

Longest Increasing Subsequence  `dp[i], longest of n[..@i]` `最小尾数: 6 1 3 4 2 5 7 => 1(6) 2(3) 4 5 7`            
Increasing Subsequences  `dfs + backtracking`                       
Increasing Triplet Subsequence `最小尾数`                          
Number of Longest Increasing Subsequence  `dp[i], solution of n[..@i]`                          

Split Array into Consecutive Subsequences  `顺子牌, greedy, 优先做尾，其次当头`    
Longest Consecutive Sequence (可乱序) [`HashSet<num>, Just walk each streak`](https://leetcode.com/problems/longest-consecutive-sequence/discuss/41057/Simple-O(n)-with-Explanation-Just-walk-each-streak)         
Binary Tree Longest Consecutive Sequence I (路径由上到下，数字递增) [`dfs`](https://leetcode.com/problems/binary-tree-longest-consecutive-sequence/discuss/74468/Easy-Java-DFS-is-there-better-time-complexity-solution)         
Binary Tree Longest Consecutive Sequence II (路径连续即可，数字递增或递减) [`dfs, count increase, decrease`](https://leetcode.com/problems/binary-tree-longest-consecutive-sequence-ii/solution/)             

Longest Arithmetic Subsequence  [`dp[i][diff]: length of arithmetic sequence with diff until A[i]`](https://leetcode.com/problems/longest-arithmetic-sequence/discuss/274611/JavaC%2B%2BPython-DP)      
Longest Arithmetic Subsequence of Given Difference [`dp[num]=1+dp[num-diff]`]()    


Longest Palindromic Subsequence  `dp[i][j]: longest of s[i..j]` `s[i]==s[j]?`                      
**Count Palindromic Subsequences**  `dp[i][j], solution of s[i..j]` `去重case`                          


**Sum of Subsequence Widths**  `sort + math`                                                   
**Longest Uncommon Subsequence I**           
**Longest Uncommon Subsequence II**                         

Length of Longest Fibonacci Subsequence  `dp`                       

Wiggle Subsequence  `dp`                        

Distinct Subsequences I: Count Distinct Subsequence of S equals T [`dp[i][j] (Si==Tj?)(use Si?)`]()                         
Distinct Subsequences II: Count Distinct Subsequences of S   [`dp[abcb] = dp[abc] (drop 'b') + (dp[abc]-dp[a]) (use 'b')`](https://leetcode.com/problems/distinct-subsequences-ii/solution/)                          
  
Arithmetic Slices II - Subsequence `dp`                         

### Subset (Knapsack)

Partition to 2 Equal Subset Sum `target is totalSum//2` `dp[i][s] = dp[i-1][s] or dp[i-1][s-A[i]], O(N*S)` [`possible sums as bitset` `for a in A: SET |= SET << a`](https://leetcode.com/problems/partition-equal-subset-sum/discuss/90590/Simple-C++-4-line-solution-using-a-bitset/94973)     
Partition to K Equal Subset Sums               
Split Array (K=2) With Same Sum `同上` `SET |= SET << a`        
Split Array (K=2) With Same Average [`for a in A: for k in reverse: SET[k] |= SET[k-1] << a`](https://leetcode.com/problems/split-array-with-same-average/discuss/120842/DP-with-bitset-over-*sum*-(fast-PythonRuby-decent-C++)/420312) `Early Pruning: len(subset)*totalSum%n==0`     
