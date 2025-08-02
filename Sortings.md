
---
Topic : [[Sortings]]
date : 21-07-2024
tags : #dsa 

---

# Case Study: Sorting Techniques

## 1. Introduction

Sorting is a fundamental operation in computer science, used to arrange elements in a specific order, typically ascending or descending. Efficient sorting algorithms improve data retrieval and processing speeds, making them crucial for applications in databases, search engines, and operating systems.

## 2. Classification of Sorting Algorithms

Sorting algorithms can be classified based on various criteria:

### A. Based on Time Complexity

- **O(n^2) Complexity**: Bubble Sort, Selection Sort, Insertion Sort
- **O(n log n) Complexity**: Merge Sort, Quick Sort, Heap Sort
- **O(n) Complexity (Special Cases)**: Counting Sort, Radix Sort, Bucket Sort (for specific input types)

### B. Based on Space Complexity

- **In-place Sorting** (Requires O(1) or O(log n) extra space): Bubble Sort, Selection Sort, Insertion Sort, Quick Sort, Heap Sort
- **Out-of-place Sorting** (Requires O(n) extra space): Merge Sort, Counting Sort, Radix Sort

### C. Based on Stability

- **Stable Sorting**: Maintains the relative order of equal elements (e.g., Merge Sort, Insertion Sort, Bubble Sort)
- **Unstable Sorting**: May change the relative order of equal elements (e.g., Quick Sort, Heap Sort, Selection Sort)

## 3. Detailed Analysis of Key Sorting Algorithms

### A. Bubble Sort

- **Concept**: Repeatedly swaps adjacent elements if they are in the wrong order.
- **Time Complexity**: O(n^2) in the worst and average cases, O(n) in the best case.
- **Space Complexity**: O(1)
- **Stable**: Yes
- **Use Case**: Suitable for small datasets or nearly sorted arrays.

### B. Selection Sort

- **Concept**: Selects the minimum element from the unsorted part and swaps it with the first element.
- **Time Complexity**: O(n^2) for all cases.
- **Space Complexity**: O(1)
- **Stable**: No
- **Use Case**: Good when memory write operations are costly.

### C. Insertion Sort

- **Concept**: Builds the sorted array one element at a time by placing each element in its correct position.
- **Time Complexity**: O(n^2) in the worst case, O(n) in the best case.
- **Space Complexity**: O(1)
- **Stable**: Yes
- **Use Case**: Suitable for small datasets or nearly sorted arrays.

### D. Merge Sort

- **Concept**: Recursively splits the array into halves, sorts them, and merges them back.
- **Time Complexity**: O(n log n) for all cases.
- **Space Complexity**: O(n)
- **Stable**: Yes
- **Use Case**: Used for large datasets and linked lists.

### E. Quick Sort

- **Concept**: Uses a pivot element to partition the array into two halves and recursively sorts them.
- **Time Complexity**: O(n log n) on average, O(n^2) in the worst case.
- **Space Complexity**: O(log n) (in-place)
- **Stable**: No
- **Use Case**: Efficient for large datasets and general-purpose sorting.

### F. Heap Sort

- **Concept**: Uses a binary heap to repeatedly extract the maximum (or minimum) element.
- **Time Complexity**: O(n log n) for all cases.
- **Space Complexity**: O(1)
- **Stable**: No
- **Use Case**: Suitable for priority queue implementations.

### G. Counting Sort

- **Concept**: Counts the occurrences of each element and places them in the correct position.
- **Time Complexity**: O(n + k), where k is the range of input values.
- **Space Complexity**: O(k)
- **Stable**: Yes
- **Use Case**: Used for small integer ranges.

### H. Radix Sort

- **Concept**: Sorts numbers digit by digit using a stable sorting algorithm like Counting Sort.
- **Time Complexity**: O(nk), where k is the number of digits.
- **Space Complexity**: O(n + k)
- **Stable**: Yes
- **Use Case**: Used for large integer datasets and fixed-length strings.

## 4. Performance Comparison

| Algorithm          | Best Case      | Average Case   | Worst Case     | Space Complexity | Stable |
| ------------------ | -------------- | -------------- | -------------- | ---------------- | ------ |
| Bubble Sort        | O(n)           | O(n^2)         | O(n^2)         | O(1)             | Yes    |
| ==Selection Sort== | ==O(n^2)==     | ==O(n^2)==     | ==O(n^2)==     | ==O(1)==         | ==No== |
| Insertion Sort     | O(n)           | O(n^2)         | O(n^2)         | O(1)             | Yes    |
| Merge Sort         | O(n log n)     | O(n log n)     | O(n log n)     | O(n)             | Yes    |
| ==Quick Sort==     | ==O(n log n)== | ==O(n log n)== | ==O(n^2)==     | ==O(log n)==     | ==No== |
| ==Heap Sort==      | ==O(n log n)== | ==O(n log n)== | ==O(n log n)== | ==O(1)==         | ==No== |
| Counting Sort      | O(n + k)       | O(n + k)       | O(n + k)       | O(k)             | Yes    |
| Radix Sort         | O(nk)          | O(nk)          | O(nk)          | O(n + k)         | Yes    |

# Types of sorts: 
### **Bubble Sort** - STABLE
	- For all elements
	- `if(arr[i] < arr[i-1])` then swap `arr[i]` and `arr[i-1]` 
	- repeat until sorted.
	- Best TC : `O(n)`
	- Average TC : `O(n^2)`
	- Worst TC : `O(n^2)`
	- SC : `O(1)`
```cpp
void bubble(int arr[], int &n) {
	int i = n-1;
	while(i > 0) {
		if(arr[i] < arr[i-1]) {
			int temp = arr[i-1];
			arr[i-1] = arr[i];
			arr[i] = temp;
		}
		i--;
	}
}
void bubbleSort(int arr[], int n) {
	int i = 0;
	while(i < n) {
		bubble(arr, n);
		i++;
	}
}
```

### **Selection Sort** - UNSTABLE
	- Start from i = 0.
	- Find smallest element in the range of \[i, n-1].
	- swap with `arr[i]` and increment i.
	- Best TC : `O(n^2)`
	- Average TC : `O(n^2)`
	- Worst TC : `O(n^2)`
	- SC : `O(1)`
```cpp
int select(int arr[], int i, int n)
{
    int min_index = i;
    for (int j = i + 1; j < n; j++) {
        if (arr[j] < arr[min_index]) {
            min_index = j;
        }
    }
    return min_index;
}

 
void selectionSort(int arr[], int n)
{
	int i = 0;
	while(i <= n-1) {
		int small = select(arr, i, n);
		swap(arr[i], arr[small]);
		i++;
	}
}
```

### **Insertion Sort** - STABLE
	- Maintain a sorted sub-array.
	- for every element check for all elements in the sorted sub-array. 
	- Best TC : `O(n)`
	- Average TC : `O(n^2)`
	- Worst TC : `O(n^2)`
	- SC : `O(1)`
```cpp
void insertionSort(int a[], int n)
{
	for(int i=1; i<n; i++) {
		int j = i-1;
		int temp = a[i];
		while(j >= 0 && temp <= a[j]) {
			a[j+1] = a[j];
			j--;
		}
		a[j+1] = temp;
	}
}
```


### **Merge Sort** - STABLE
- **Concept**: Divide the array recursively into halves, sort them, and merge.
- **Approach**:
    - Recursive
    - Divide and Conquer
- **Time Complexity**:
    - Best: `O(n log n)`
    - Average: `O(n log n)`
    - Worst: `O(n log n)`
- **Space Complexity**: `O(n)` (due to extra temp arrays)
- **Use Case**: Works well with **linked lists** and external sorting.

```cpp
void merge(int arr[], int l, int m, int r) {
	int n1 = m - l + 1;
	int n2 = r - m;
	int L[n1], R[n2];
	for(int i = 0; i < n1; i++) L[i] = arr[l + i];
	for(int i = 0; i < n2; i++) R[i] = arr[m + 1 + i];
		
	int i = 0, j = 0, k = l;
	while(i < n1 && j < n2) {
		if(L[i] <= R[j]) {
			arr[k] = L[i];
			k++; i++;
		} else {
			arr[k] = R[j];
			k++;
			j++;
		}
	}
	while(i < n1) {
		arr[k] = L[i];
		k++; i++;
	}
		
	while(j < n2) {
		arr[k] = R[j];
		k++; j++;
	}
}


void mergeSort(int arr[], int l, int r) {
	if(l < r) {
		int m = l + (r - l) / 2;
		mergeSort(arr, l, m);
		mergeSort(arr, m+1, r);
		merge(arr, l, m, r);
	}
}
```

### **Quick Sort** - UNSTABLE
- **Concept**: Select a pivot and partition the array such that elements smaller than pivot come before, and greater come after.
- **Approach**:
    - Divide and Conquer
- **Time Complexity**:
    - Best: `O(n log n)`
    - Average: `O(n log n)`
    - Worst: `O(n^2)` (when pivot is min or max element).
- **Space Complexity**: `O(log n)` (due to recursion stack).
- **Use Case**: **Fastest** in practice for general-purpose arrays.

```cpp
int patition(int arr[], int low, int high) {
	int pivot = arr[high];
	int i = low - 1;
		
	for(int j = low; j < high; j++) {
		if(arr[j] <= pivot) {
			i++;
			swap(arr[i], arr[j]);
		}
	}
	swap(arr[i+1], arr[high]);
	return i + 1;
}

void quickSort(int arr[], int low, int high) {
	if(low < high) {
		int pi = partition(arr, low, high);
		quickSort(arr, low, pi - 1);
		quickSort(arr, pi + 1, high);
	}
}
```

### **Heap Sort** – UNSTABLE
- **Concept**: Build a max-heap, then repeatedly extract the max and re-heapify.
- **Approach**: Priority Queue based, in-place
- **Time Complexity**:
    - Best: `O(n log n)`
    - Average: `O(n log n)`
    - Worst: `O(n log n)`
- **Space Complexity**: `O(1)`
- **Use Case**: Useful in heap-based priority queues, real-time systems.
```cpp
```

