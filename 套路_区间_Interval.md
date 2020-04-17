## Interval

### (OPEN, CLOSE) scanning approach
* open first: 连接相切区间 `(),() => (())`
* close first: 不连接相切区间 `(),()`

Merge Interval `(()),(),(())` `open first (open=0, close=1)`    
Employee Free Time `(()),(),(())` `open first (open=0, close=1)`    
Meeting Rooms I (no overlap) `()()()()` `close first (open=1, close=0)`       
Meeting Rooms II (room needed) `(())()` `close first (open=1, close=0)`     
Find Right Interval `(())<=()<=()<=()` `close first (open=1, close=0)` `idx, stack`                     

### interval overlap, covering
Minimum Removal to have Non-overlapping Intervals  `双指针: 删除结束晚的`            
Overlaps of Two List of Intervals `双指针：移动结束早的 + 区间合并`                          
Minimum Intervals to cover the Target Interval `贪婪: 覆盖 target.start，结束最晚`       

### Calendar
**My Calendar I (no double booking)**  `binary search tree`          
**My Calendar II (no triple booking)**  `events, overlaps`                 
**My Calendar III (max K booking)**  `(OPEN, CLOSE)` `balance[s] += 1; balance[e] -= 1`                

### insert interval
**Insert Interval**  `Binary Search`                
**Data Stream as Disjoint Intervals**  `BST`    

### Misc
**Maximum Sum of 3 Non-Overlapping Subarrays ?**                   
**Random Pick with Blacklist**                    
**Set Intersection Size At Least Two**                   



### 还没做

Teemo Attacking      
Add Bold Tag in String        
Range Module       
Partition Labels       
Interval List Intersections     
Remove Covered Intervals    
Remove Interval     
Integer Replacement      