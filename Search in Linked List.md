
---
[Search in Linked List](https://www.geeksforgeeks.org/problems/search-in-linked-list-1664434326/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=search-in-linked-list-1664434326)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---
## Code 

```cpp
class Solution {
  public:
    // Function to count nodes of a linked list.
    bool searchKey(int n, struct Node* head, int key) {
        Node* temp = head;
        while(temp->next != NULL) {
            if(temp->data == key) {
                return true;
            }
            temp = temp->next;
        }
        if(temp->data == key) return true;
        return false;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
