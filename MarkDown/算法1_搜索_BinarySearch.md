## Binary Search

``` python
#### binary search center match(x) ####
while l <= r:
    mid = l + (r-l)//2
    direction = match(mid)
    if direction == FOUND:   return mid
    elif direction == LEFT:  r = mid - 1
    elif direction == RIGHT: l = mid + 1
return NotFound

#### binary search leftmost match(x) ####
#### 元素越右越正确，找最左
while l < r:
    mid = l + (r-l)//2       # mid 偏左
    if match(mid): r = mid
    else: l = mid + 1
if match(l): return l; else: ?  # 可能没有正确元素，需要检查

#### binary search rightmost match(x) ####
#### 元素越左越正确，找最右
while l < r: 
    mid = l + (r-l+1)//2     # mid 偏右
    if match(mid): l = mid
    else: r = mid - 1
if match(r): return r; else: ?  # 可能没有正确元素，需要检查

# bisect.bisect_left;  bisect.bisect_right
# bisect.insort_left;  bisect.insort_right
```

### search center
Peak Index in a Mountain Array         
Find Peak Element     
Guess Number Higher or Lower      
Binary Search Target        
Valid Perfect Square      
Search in a Sorted Array of Unknown Size `find right first`       


### search leftmost/rightmost
Find Smallest Letter Greater Than Target  `leftmost`         
First Bad Version  `leftmost`         
Search Insert Position  `leftmost` `rightmost`                         
Find First and Last Position of Element in Sorted Array         
Sqrt(x) `rightmost`      

Single Element in a Sorted Array `(1 1)(2 2)(3 4)(4 5) 5` `找最左的不配对`             
Find the Duplicate Number `二分查找最左 count_le(x) > x`              
Heaters (min radius)  `heater排序,每个house二分查找左右heater`              

H-Index I `sort in descending order`       
H-Index II (ascending) `Binary Search`            

### rotated sorted array
Search in Rotated Sorted Array I `binary search`        
**Search in Rotated Sorted Array II (duplicate)**           
Find Minimum in Rotated Sorted Array I `binary search`          
**Find Minimum in Rotated Sorted Array II (duplicate)**         

``` python
def search_rotated_sorted_array(self, nums, target):
    l, r = 0, len(nums) - 1
    while l <= r:
        m = l + (r - l)//2
        if target == nums[m]: return m
        if nums[m] <= nums[l]:
            if nums[l] <= target <= nums[m]: r = m - 1
            else: l = m + 1
        else:
            if nums[m] <= target <= nums[r]: l = m + 1
            else: r = m - 1
    return -1

def min_rotated_sorted_array(self, nums):
    l, r = 0, len(nums) - 1
    while l < r:
        m = l + (r - l) // 2
        if nums[m] > nums[r]: l = m + 1
        else: r = m
    return nums[l]
```

### two arrays
Intersection of Two Arrays I         
Intersection of Two Arrays II           
Median of Two Sorted Arrays  `二分查找最左 m1: A[m1]>=B[k-m1-1]`       


### 还没做

**Smallest Good Base**          

Valid Perfect Square            

Arranging Coins         

4Sum II         
Kth Smallest Element in a BST           
Kth Smallest Element in a Sorted Matrix         
Find the Duplicate Number with O(1) space            
Maximum Length of Repeated Subarray         
Koko Eating Bananas         
Find Right Interval         

Search a 2D Matrix          
Search a 2D Matrix II           

Longest Increasing Subsequence          

Find K Closest Elements         

Minimum Size Subarray Sum           

Count Complete Tree Nodes        
Pow(x, n)           
Divide Two Integers         
Split Array Largest Sum         
Preimage Size of Factorial Zeroes Function          
Kth Smallest Number in Multiplication Table         

Minimize Max Distance to Gas Station        
K-th Smallest Prime Fraction            
Max Sum of Rectangle No Larger Than K             

Russian Doll Envelopes            
Random Pick with Blacklist            
Find K-th Smallest Pair Distance          
Maximum Average Subarray II          
Dungeon Game            

Nth Magical Number           
Super Egg Drop          