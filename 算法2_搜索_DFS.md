## DFS (tree/graph 之外)  

``` python
"""
1. 画 DFS 递归调用树
2. 思考 DFS 节点之间的信息传递
	1. 向下👇传递信息：dfs() 的输入
	2. 向上👆传递信息：dfs() 的返回值
	3. 用全局变量保存全局信息
"""

#### DFS @ List #####
def dfs(node):
    dfs(node.next)

#### DFS @ Tree #####
def dfs(node):
    dfs(node.left)
    dfs(node.right)

#### DFS @ Implicit Tree (Backtracking) #####
def dfs(path, rest):
    if accept(path): results.append(path)
    for node in rest:
        path.append(node)
        dfs(path,  rest-node)
        path.pop()
    
#### DFS @ Graph #####
def dfs(u):
    visited[u] = 1   # 1 表示开始访问 u 节点
    for v in E[u]:
        if visited[v] == 0 : dfs(v)
        elif visited[v] == 1: # Do Something
        elif visited[v] == 2: # Do Something
    visited[u] = 2   # 2 表示结束访问 u 节点
```


### tree or graph
Loud and Rich  `dfs @ graph` `draw dfs calling tree`   
Employee Tree Importance `dfs @ tree`   

### string
Decode String `example: "0[1[]]23[ab]cd"`  `dfs`   
Ternary Expression Parser `example: T?T?F:5:3` `dfs`  

### Grid
Minesweeper `dfs`     
Flood Fill  `dfs`  
Number of Islands `dfs`    
Number of Distinct Islands I `descriptor` `srrd____ != srr_d___`    
**Number of Distinct Islands II (rotation)** `list of coords` **`normalize?`**     

### Done
Nested-List Weight Sum I (depth as weight) `dfs`  
Nested-List Weight Sum II (height as weight) `dfs` 
Pyramid Transition Matrix  `dfs` `itertools.product`   

### To-Do       
**Robot Room Cleaner**     
**House Robber III**      

**Cracking the Safe**     
**Contain Virus**     
**24 Game**   
**Increasing Subsequences**   
**Longest Increasing Path in a Matrix**   
**Zuma Game**     
**Matchsticks to Square**     


