
---
[[Check for Balanced Parentheses]]
Topic: [[STACKS & QUEUES]]
tags: #dsa 
date: 07-06-2025-06-07

---
## Code 

```cpp
bool isValid(string s) {
    stack<char>st; 
    for(auto it: s) {
        if(it=='(' || it=='{' || it == '[') st.push(it); 
        else {
            if(st.size() == 0) return false; 
            char ch = st.top(); 
            st.pop(); 
            if((it == ')' and ch == '(') or  (it == ']' and ch == '[') or (it == '}' and ch == '{')) continue;
            else return false;
        }
    }
    return st.empty(); 
}
```

---
# 🦚 राधे राधे 🦚
---
