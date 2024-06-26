
---
[Introduction to Doubly Linked List](https://www.geeksforgeeks.org/problems/introduction-to-doubly-linked-list/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=introduction-to-doubly-linked-list)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---
## Approach 

**Example 1:**

**Input:**
n = 5
arr = \[1,2,3,4,5]
**Output:**
1 2 3 4 5
**Explanation:** Linked list for the given array will be 1<->2<->3<->4<->5.

**Example 2:**

**Input:**
n = 1
arr = \[1]
**Output:**
1
Explanation: Linked list for the given array will be 1.

**Constraints:**  
1 <= n <= 105  
1 <= arr\[i] <= 100
## Code 

```cpp
class Solution {
  public:
    Node* constructDLL(vector<int>& arr) {
        Node* head = new Node(arr[0]);
        Node* temp = head;
        for(int i=1; i<arr.size(); i++) {
            Node * newNode = new Node(arr[i]);
            temp->next = newNode;
            newNode->prev = temp;
            temp = newNode;
        }
        return head;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
