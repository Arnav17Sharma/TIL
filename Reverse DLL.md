
---
[Reverse DLL](link)
Topic: [[Linked Lists]]
tags: #dsa 
date: 12-07-2025-07-12

---
## Approach

### Brute:
- TC: O(N)
- SC: O(N)
## Code 

```cpp
Node* reverseDLL(Node* head){
    if(head==NULL || head->next == NULL){
        return head;
    }
    stack<int> st;
    Node* temp = head;
    while(temp!=NULL){
        st.push(temp->data);
        temp = temp->next;
    }
    temp = head;
    while(temp!=NULL){
        temp->data = st.top();
        st.pop();
        temp = temp->next;
    }
    return head;

}
```

### Optimal:
- TC: O(N)
- SC: O(1)
## Code 

```cpp
Node* reverseDLL(Node* head) {
    if (head == NULL || head->next == NULL) {
        return head; 
    }
    Node* prev = NULL;
    Node* current = head;
    while (current != NULL) {
        prev = current->back;
        current->back = current->next;
        current->next = prev;
        current = current->back; 
    }
    return prev->back;
}
```

---
# 🦚 राधे राधे 🦚
---
