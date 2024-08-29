
---
[[isPalindrome Linked List]](https://leetcode.com/problems/palindrome-linked-list)
Topic: [[Linked Lists]]
tags: #dsa #linked-lists 
date: 26-08-2024-08-26

---
## Approach

- Find mid.
- Reverse the second half of the linked list:  
	- Case 1 : If Odd no. of elements. ( Start from mid->next )
	- Case 2 : If Even no. of elements. ( Start from mid )
- Check from head and mid->next if each node same value ?
## Code 

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
 public:
  bool isPalindrome(ListNode* head) {
    ListNode* slow = head;
    ListNode* fast = head;

    while (fast != nullptr && fast->next != nullptr) {
      slow = slow->next;
      fast = fast->next->next;
    }

	// 1 2 3 3 2 1 NULL
	// 1 2 3 2 1

    if (fast != nullptr) // if odd number elements
      slow = slow->next;
    slow = reverseList(slow);

    while (slow) {
      if (slow->val != head->val)
        return false;
      slow = slow->next;
      head = head->next;
    }

    return true;
  }

 private:
  ListNode* reverseList(ListNode* head) {
    ListNode* prev = nullptr;

    while (head) {
      ListNode* next = head->next;
      head->next = prev;
      prev = head;
      head = next;
    }

    return prev;
  }
};
```

---
# 🦚 राधे राधे 🦚
---
