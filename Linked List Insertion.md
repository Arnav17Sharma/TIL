
---
[Linked List Insertion](https://www.geeksforgeeks.org/problems/linked-list-insertion-1587115620/0?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=linked-list-insertion)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-06-2024-06-26

---
## Approach

- Insert functions for bot begin and end insertions. 

## Code 

```cpp
class Solution{
  public:
    //Function to insert a node at the beginning of the linked list.
    Node *insertAtBegining(Node *head, int x) {
        Node* temp = new Node(x);
        temp->next = head;
        return temp;
    }
    
    
    //Function to insert a node at the end of the linked list.
    Node *insertAtEnd(Node *head, int x)  {
        Node* temp = head;
        if(head == NULL) return new Node(x);
        while(temp->next != NULL) {
            temp = temp->next;
        }
        Node* temp2 = new Node(x);
        temp->next = temp2;
        return head;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
