
---
[Word Ladder - I](https://leetcode.com/problems/word-ladder/)
Topic: [[Graphs]]
tags: #dsa #graphs #bfs 
date: 18-06-2024-06-18

---
## Approach

**Example 1:**

**Input:** beginWord = "hit", endWord = "cog", wordList = \["hot","dot","dog","lot","log","cog"]
**Output:** 5
**Explanation:** One shortest transformation sequence is "hit" -> "hot" -> "dot" -> "dog" -> cog", which is 5 words long.

**Example 2:**

**Input:** beginWord = "hit", endWord = "cog", wordList = \["hot","dot","dog","lot","log"]
**Output:** 0
**Explanation:** The endWord "cog" is not in wordList, therefore there is no valid transformation sequence.

![[Pasted image 20240618210642.png]]
## Code 

```cpp

class Solution {
public:
    int ladderLength(string beginWord, string endWord, vector<string>& wordList) {
        if(find(wordList.begin(), wordList.end(), endWord) == wordList.end()) return 0;
        
        queue<pair<string, int>> q;
        q.push({ beginWord, 1 });
        unordered_set<string> st(wordList.begin(), wordList.end());
        
        while(!q.empty()) {
            string word = q.front().first;
            int steps = q.front().second;
            q.pop();
            
            if(word == endWord) return steps;
            
            for(int i=0; i<word.size(); i++) {
                char original = word[i];
                for(char ch = 'a'; ch <= 'z'; ch++) {
                    word[i] = ch;
                    if(st.find(word) != st.end()) {
                        st.erase(word);
                        q.push({word, steps+1});
                    }
                }
                word[i] = original;                
            }
        }
        return 0;
    }
};

```

---
# 🦚 राधे राधे 🦚
---
