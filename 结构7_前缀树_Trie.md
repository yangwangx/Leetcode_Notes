## Trie (Prefix Tree)

[Youtube Video on Trie Data Structure](https://www.youtube.com/watch?v=AXjmTQ8LEoI)

Implement Trie (Prefix Tree)  `trie`        
Add and Search Word - Data structure design `trie` `search "a..c"` `dfs写法`        
Delete Word `dfs 写法见下`    
Map Sum Pairs (insert("apple", 3); insert("app", 2); sum("ap"))  `delta update`     
Implement Magic Dictionary `trie` `mismatch:=1`    
Replace Words `trie` `first word in search`       
Longest Word in Dictionary   `self.is_word, self.word` `bfs` `word_path`    
Longest Word in Dictionary through Deleting `heap(word), isSubsequence?`           

Stream of Characters [`build trie & track pointers`](https://leetcode.com/problems/stream-of-characters/discuss/278250/Python-Trie-Solution)     


### hard，还没做
**Word Search II**      
**Concatenated Words**      
**Palindrome Pairs** `字符串双拼` `Hash O(nw^2)` `Trie`       
**Word Squares**    
**Prefix and Suffix Search**        
**Design Search Autocomplete System**    
**Maximum XOR of Two Numbers in an Array**      

``` python
class TrieNode:
    def __init__(self):
        self.children = collections.defaultdict(TrieNode)
        self.is_word = False
        # self.word = ''

class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        p = self.root
        for c in word:
            p = p.children[c]
        p.is_word = True
        p.word = word

    def search(self, word):
        p = self.root
        for c in word:
            if c in p.children: p = p.children[c]
            else: return False
        return p.is_word

    def startsWith(self, prefix):
        p = self.root
        for c in prefix:
            if c in p.children: p = p.children[c]
            else: return False
        return True

    def delete(self, word):
        p = self.root
        self.delete_helper(p, word, index=0)

    def delete_helper(self, node, word, index): # return (delete_me)
        # at the end
    	if index == len(word):
            if not node.is_word: return False
	    	node.is_word = False
	    	return len(node.children) == 0
     	# in the middle
 	    c = word[index]
 	    if c not in node.children: return False
 	    del_c = self.delete_helper(node.children[c], word, index+1)
        if del_c: del node.children[c]
        return len(node.children) == 0 and (not node.is_word)

    # def bfs(self):
    # def dfs(self):
```