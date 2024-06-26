
---
[Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---

## Code 

```cpp
class Solution {
public:
    void deleteNode(ListNode* node) {
        swap(node->val, node->next->val);
        ListNode*temp = node->next;
        node->next = node->next->next;
        delete temp;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
