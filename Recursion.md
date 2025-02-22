
---
Topic : [[Recursion]]
date : 22-02-2025
tags : #dsa 

---

```cpp
// Example of infinite loop => Stack Overflow
void main() {
	void fn() {
		fn();
	}
}
```

- Stack overfow condition. 
- To solve this we need a base condition to eventually stop this. 

## Questions 

- All Subsets of an array.
```cpp
void helper(int ind, vector<int>&)

vector<vector<int>> subsets(vector<int> arr) {
	vector<vector<int>> ans;
	vector<int> temp;
	helper(0, arr, temp);
}
```