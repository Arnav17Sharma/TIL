
---
[[Implement Stack using Array]]
Topic: [[STACKS & QUEUES]]
tags: #dsa 
date: 07-06-2025-06-07

---
# Code 

```cpp
class Stack {
  int size;
  int * arr;
  int top;
  public:
    Stack() {
      top = -1;
      size = 1000;
      arr = new int[size];
    }
  void push(int x) {
    top++;
    arr[top] = x;
  }
  int pop() {
    int x = arr[top];
    top--;
    return x;
  }
  int Top() {
    return arr[top];
  }
  int Size() {
    return top + 1;
  }
};
```

---
# 🦚 राधे राधे 🦚
---
