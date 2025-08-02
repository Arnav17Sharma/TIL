
---
[[Implement Queue using Stack]]
Topic: [[STACKS & QUEUES]]
tags: #dsa 
date: 07-06-2025-06-07

---
## Code 

```cpp
struct Queue {
  stack < int > input, output;
  void Push(int data) {
    while (!input.empty()) {
      output.push(input.top());
      input.pop();
    }
    cout << "The element pushed is " << data << endl;
    input.push(data);
    while (!output.empty()) {
      input.push(output.top());
      output.pop();
    }
  }
  int Pop() {
    if (input.empty()) {
      cout << "Stack is empty";
      exit(0);
    }
    int val = input.top();
    input.pop();
    return val;
  }
  int Top() {
    if (input.empty()) {
      cout << "Stack is empty";
      exit(0);
    }
    return input.top();
  }
  int size() {
    return input.size();
  }
};
```

---
# 🦚 राधे राधे 🦚
---
