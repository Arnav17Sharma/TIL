
---
Topic : [[Linked Lists]]
date : 25-06-2024
tags : #dsa #linked-lists 

---

## Linked List 

- Self defined data-type.
## Uses of Linked Lists
- Implementation of Stacks/Queues.
- Browser navigation.
- Every element of the linked list has 2 attributes `data` & `next`.
- Every element is called a `Node`.
## Concept of Pointers

```cpp
int x = 2;
int * y = &x;
```
Here, y stores the pointer pointing at the address of the memory location of variable x. 

## Define a Class for data-type of Linked List

```cpp
class Node {
	public:
		int data;
		Node* next;
		Node(int data1, Node* next1) {
			data = data1;
			next = next1;
		}
		Node(int data1) {
			data = data1;
			next = nullptr;
		}
}
```

## Memory Space Used

- For 32-bit system `data` will take 4 bytes + `next` will take 4 bytes. \[ 8 bytes ]
- For 64-bit system `data` will take 4 bytes + `next` will take 8 bytes. \[ 16 bytes ]

## Questions

- [[Arrays to LinkedLists]]
- [[Linked List Insertion]]
- [[Delete Node in a Linked List]]
- [[Count Linked List Nodes]]
- [[Search in Linked List]]
- [[Introduction to Doubly Linked List]]
- [[Doubly linked list Insertion at given position]]
- 
