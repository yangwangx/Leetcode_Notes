## Sampling
### Resavoir Sampling (Single Pass, Anytime Stop)
``` python
bag[0:k] = reservoir[0:k]
for cur in range(k, len(reservoir)):
    replace = random.randint(0, i)
    if replace < k: bag[replace] = reservoir[cur]
```    

Linked List Random Node  `k=1`    
Random Pick Index   `k=1`    
  
### Inverse Transform Sampling， Rejection Sampling

Generate Random Point in a Circle  `Rejection sampling` `Inverse Transform Sampling`         
Random Pick with Weight `Inverse Transform Sampling` `前缀和，二分查找`      
Random Point in Non-overlapping Rectangles  `按面积随机选择矩形`        

### Rand-M -> Rand-N
Implement Rand-N() Using Rand-M() `MxM square, divide among 1..N`      
