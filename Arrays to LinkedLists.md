
---
[Arrays to LinkedLists](https://www.geeksforgeeks.org/problems/introduction-to-linked-list/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=introduction-to-linked-list)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---

## Code 

```cpp
class Solution {
  public:
    Node* constructLL(vector<int>& arr) {
        Node* start = new Node(arr[0]);
        Node* temp = start;
        for(int i=1; i<arr.size(); i++) {
            Node* newNode = new Node(arr[i]);
            temp->next = newNode;
            temp = newNode;
        }
        return start;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
