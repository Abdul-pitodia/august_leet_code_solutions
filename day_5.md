IMPLEMENT TRIE DATA STRUCTURE TO STORE AND SEARCH STRINGS

Design a data structure that supports the following two operations:

void addWord(word)
bool search(word)

search(word) can search a literal word or a regular expression string containing only letters a-z or .. A . means it can represent any one letter.

Example:

addWord("bad")
addWord("dad")
addWord("mad")
search("pad") -> false
search("bad") -> true
search(".ad") -> true
search("b..") -> true

Note:
You may assume that all words are consist of lowercase letters a-z.



```
class TrieNode:
    def __init__(self):
        self.child = {}
        self.ends = False

class WordDictionary:
    alp_lst = []

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.root = TrieNode()
        
        
        
        

    def addWord(self, word: str) -> None:
        """
        Adds a word into the data structure.
        """
        node = self.root
        self.alp_lst.append(word[0])
        for w in word:
            if (w not in node.child):
                node.child[w] = node
            node = node.child[w]
        node.ends = True
        
                
        

    def search(self, word: str) -> bool:
        """
        Returns if the word is in the data structure. A word could contain the dot character '.' to represent any one letter.
        """
        print(self.alp_lst)
        if (word[0] != '.'):
            node = self.root
            for w in word:
                if (w not in node.child):
                    return False
                else:
                    node = node.child[w]
            return node.ends 
        else:
            node = self.root
            new_wrd = word[1:]
            for alp in self.alp_lst:
                if (alp in node.child):
                    for wrd in new_wrd:
                        if (wrd not in node.child):
                            return False
                        else:
                            node = node.child[wrd]
                    return node.ends
                    
                    
```                    
