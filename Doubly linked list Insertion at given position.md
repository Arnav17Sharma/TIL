
---
[Doubly linked list Insertion at given position](https://www.geeksforgeeks.org/problems/insert-a-node-in-doubly-linked-list/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=insert-a-node-in-doubly-linked-list)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---
## Approach

**Example 1:**

**Input:**
LinkedList: 2<->4<->5
p = 2, x = 6 
**Output:** 2 4 5 6
**Explanation:** p = 2, and x = 6. So, 6 is
inserted after p, i.e, at position 3
(0-based indexing).

**Example 2:**

**Input:**
LinkedList: 1<->2<->3<->4
p = 0, x = 44
**Output:** 1 44 2 3 4
**Explanation:** p = 0, and x = 44 . So, 44
is inserted after p, i.e, at position 1
(0-based indexing).

## Code 

```cpp
void addNode(Node *head, int pos, int data)
{
    Node* temp = head;
    int cnt = 0;
    while(temp->next != NULL) {
        if(cnt == pos) {break;}
        temp = temp->next;
        cnt++;
    }
    Node* final = new Node(data);
    final->next = temp->next;
    if(temp->next != NULL)
        temp->next->prev = final;
    temp->next = final;
    final->prev = temp;
}
```

---
# 🦚 राधे राधे 🦚
---
