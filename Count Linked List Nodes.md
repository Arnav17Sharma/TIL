
---
[Count Linked List Nodes](https://www.geeksforgeeks.org/problems/count-nodes-of-linked-list/0?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=count-nodes-of-linked-list)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---

## Code 

```cpp
class Solution
{
    public:
    //Function to count nodes of a linked list.
    int getCount(struct Node* head){
        Node* temp = head;
        int ans = 1;
        while(temp->next != NULL) {
            temp = temp->next;
            ans++;
        }
        return ans;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
