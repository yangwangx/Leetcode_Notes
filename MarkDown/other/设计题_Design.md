## Design

``` python
### LRU Cache: hash + dll ###
class ListNode:
    def __init__(self, k, v):
        self.key = k
        self.val = v
        self.prev = None
        self.next = None

    def connect(self, nextNode):
        self.next = nextNode
        nextNode.prev = self

class LRUCache:
    def __init__(self, capacity):
        self.capacity = capacity
        self.dic = dict()
        self.head = ListNode(0, 0)
        self.tail = ListNode(0, 0)
        self.head.connect(self.tail)

    def put(self, key, value):
        if key in self.dic: 
            self._remove(self.dic[key])
        n = ListNode(key, value)
        self._add(n)
        self.dic[key] = n
        if len(self.dic) > self.capacity:
            n = self.head.next
            self._remove(n)
            del self.dic[n.key]

    def get(self, key):
        if key in self.dic:
            n = self.dic[key]
            self._remove(n)
            self._add(n)
            return n.val
        return -1

    def _remove(self, node):
        node.prev.connect(node.next)

    def _add(self, node):
        self.tail.prev.connect(node)
        node.connect(self.tail)

### Insert Delete GetRandom O(1) ###
class RandomizedSet(object):
    def __init__(self):
        self.nums, self.pos = [], {}

    def insert(self, val):
        if val not in self.pos:
            self.nums.append(val)
            self.pos[val] = len(self.nums) - 1
            return True
        return False

    def remove(self, val):
        if val in self.pos:
            idx, last = self.pos[val], self.nums[-1]
            self.nums[idx] = last
            self.pos[last] = idx
            self.nums.pop()
            del self.pos[val]
            return True
        return False

    def getRandom(self):
        return random.choice(self.nums)

### Insert Delete GetRandom O(1), duplicates allowed ###
class RandomizedCollection(object):
    def __init__(self):
        self.nums, self.pos = [], collections.defaultdict(set)

    def insert(self, val):
        self.nums.append(val)
        self.pos[val].add(len(self.nums) - 1)
        return len(self.pos[val]) == 1        

    def remove(self, val):
        if self.pos[val]:
            idx, last = self.pos[val].pop(), self.nums[-1]
            self.nums[idx] = last
            # if self.pos[last]:
            if True:
                self.pos[last].add(idx)
                self.pos[last].discard(len(self.nums) - 1)
            self.nums.pop()
            return True
        return False 

    def getRandom(self):
        return random.choice(self.nums)
```

### queue/stack
Implement Queue using Stacks        
Implement Stack using Queues        
Design Circular Queue       
Min Stack       
Max Stack    
Design Circular Deque       

### hash set/map
Design HashSet      
Design HashMap      

### linked list
Design Linked List      
Design Phone Directory    

### tree
Binary Search Tree Iterator     
Serialize and Deserialize Binary Tree       

### Trie (prefix tree)
Implement Trie (Prefix Tree)        
Design Search Autocomplete System    

### data stream
Find Median from Data Stream        
Moving Average from Data Stream    

### Cache
LFU Cache       
LRU Cache       

### misc
Logger Rate Limiter    
Design Hit Counter    
Zigzag Iterator    
Design Log Storage System    
Design Tic-Tac-Toe    
Flatten Nested List Iterator        
Shortest Word Distance II    
Flatten 2D Vector    
Peeking Iterator        
Design In-Memory File System    
Design Compressed String Iterator    
Insert Delete GetRandom O(1)        
Insert Delete GetRandom O(1) - Duplicates allowed       
All O`one Data Structure        
Design Excel Sum Formula    
Design Snake Game    
Two Sum III - Data structure design    
Add and Search Word - Data structure design     
Design Twitter      
Unique Word Abbreviation    
