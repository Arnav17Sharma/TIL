
---
[Delete in DLL](link)
Topic: [[Linked Lists]]
tags: #dsa 
date: 12-07-2025-07-12

---
## Approach

- Explain your approach

## Code 

```cpp
Node* deleteHead(Node* head) {
    if (head == nullptr || head->next == nullptr) {
        return nullptr; 
    }
    Node* prev = head;
    head = head->next;    
    head->back = nullptr;   
    prev->next = nullptr;  
    return head;          
}

Node* deleteTail(Node* head) {
    if (head == nullptr || head->next == nullptr) {
        return nullptr;  
    }
    
    Node* tail = head;
    while (tail->next != nullptr) {
        tail = tail->next; 
    }
    
    Node* newTail = tail->back;
    newTail->next = nullptr;
    tail->back = nullptr;
    delete tail;  
    
    return head;
```

---
# 🦚 राधे राधे 🦚
---
