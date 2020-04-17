## Two Pointer

### Linked List
Linked List Cycle I `龟兔赛跑`                      
Linked List Cycle II                    
Remove Nth Node From End of List                        
Partition List                      
Rotate List                     
Palindrome Linked List                      


### Meeting Pointers (2-Sum, water): 排除法
2Sum (unsorted) `Hash`           
2Sum (sorted) `meeting`           
2Sum Less Than K `meeting`    
3Sum (sorted) `meeting, 2Sum, 去重`                       
4Sum (sorted)   `meeting, 3Sum`      
3Sum closest to target  `meeting`                     
3Sum smaller than target count                  
3Sum With Multiplicity `去重`                         
[4Sum II (4 array)](https://leetcode.com/problems/4sum-ii/discuss/93917/Easy-2-lines-O(N2)-Python)      
Trapping Rain Water `bfs` `pop shorter bin`        
Container With Most Water  `move shorter bin`      
Find the Celebrity `排除法` `double check`       
Search a 2D Matrix II `topright start`     
Reverse String   `easy`                   
Reverse Vowels of a String `easy`                     
Squares of a Sorted Array `[-4,-1,0,3,10]`    

### Tail （洗牌问题: ABABA -> AAABB)
Move Zeros to End `AB`      
Remove Element  `AB`                    
Sort Colors `ABC`            
Sort Letters by Case `AB`              
Sort Array By Parity I `AB`           
**Sort Array By Parity II (interleaved)**       
**Remove Duplicates from Sorted Array I (allow once)** `fastforward B to last duplicate`           
**Remove Duplicates from Sorted Array II (allow twice)** `fastforward B to last duplicate`           

### Sliding Window (path in matrix of windows)

#### longest window: 越短越正确，找最长

Longest Substring with At Most K Distinct Characters `len(counter) <= k`           
Longest Substring with At Most Two Distinct Characters  `len(counter) <= 2`                 
Fruit Into Baskets  `len(counter) <= 2`           
Longest Substring Without Repeating Characters `no repeat, use set`                     
**Count Subarray Product $< K$**  `draw the matrix`                      
Max Consecutive Ones I  `dp`                
Max Consecutive Ones II (flip once) `zeros <= 1`                   
Longest Mountain in Array `difference: +, 0, -` `longest ++--`                      
Longest Repeating Character Replacement `w - count(major)<=k`

#### shortest window: 越长越正确，找最短

Minimum Size Subarray Sum $\ge k$ `window_sum`       
**Minimum Window Substring covering T** `Counter(T)`           
Minimum Window Subsequence covering T  `正向搜索右指针，反向搜索左指针`         





### Two Array
Swap Adjacent in LR String `L/R: people facing left/right`         
**Intersection of Two Arrays I**                     
**Intersection of Two Arrays II**                    
**Implement strStr()**     **Merge Sorted Array**            **The smallest difference**              



### to do
**Substring with Concatenation of All Words**                       
**Maximum Size Subarray Sum Equals k**  `hash`                
**Find the Duplicate Number**                       
**Partition Labels**                                               
**Smallest Range**                      
**K-diff Pairs in an Array**                        
**Candy Crush**                    
**Permutation in String**                       
**Backspace String Compare**                        
**Longest Word in Dictionary through Deleting**                     
**Sort Transformed Array**                    
**Push Dominoes**                       
**Unique Letter String**                        
**Boats to Save People**                        
**Most Profit Assigning Work**                      

**Binary Subarrays With Sum**                       
**Long Pressed Name**                       

``` python

【排除法搜索】
【搜索一个元素: binary search (最左，最右)】
【搜索两个元素: meeting 2pointer】
【搜索一个区间: sliding window (最长，最短)】

越左越正确，找“最右”元素
算法：binary search rightmost, double check

 + + + + - - -
 |     +     |
       |   - |
       | -|
      |+|

越右越正确，找“最左”元素
算法：binary search leftmost, double check

- - - + + + +
|     +     |
| -   |
   |- |
     |+|


越短越正确，找“最长”窗口 (at most k distinct values, no repeat) 
算法: 从正确，走到正确的边缘

O +.+.+.-
  O   +.-
    O +.+.-
      O +.+.-
        O +.-
          O.+.
            O

while True:
    while right+1<L: if OK_Add(right+1): right += 1
    res = max(res, right-left+1)
    if right == L-1: return res
    left += 1  # or, move left until right can move

越长越正确，找“最短”窗口 (covering T, sum>k)
算法: 从错误，走进正确的边缘

O -.-.-.+.
  O     +.
    O   -.+.
      O   +.
        O -.-.
          O  
            O

while True:
    while right+1<L: right += 1; if OK: break 
    if not OK: return res
    while True: left += 1; if not OK: break
    res = min(res, right-left+2)
    if right == L-1: return res

找“最佳”配对 （2sum, 3sum (closest/smaller), most water）
算法: Meeting 线路 

O       L.R.R.
  O     L.
    O   L.
      O L.
        O
          O
            O
```