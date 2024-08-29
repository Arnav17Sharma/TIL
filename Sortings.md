
---
Topic : [[Sortings]]
date : 21-07-2024
tags : #dsa 

---
# Types of sorts: 

- ### Bubble Sort
	- For all elements
	- `if(arr[i] < arr[i+1])` then swap `arr[i]` and `arr[i+1]` 
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

- ### Selection Sort
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
	int a = i;
	int b = a;
	while(a <= n-1) {
		if(arr[a] < arr[b]) {
			b = a;
		}
		a += 1;
	}
	return b;
}
 
void selectionSort(int arr[], int n)
{
	int i = 0;
	while(i <= n-1) {
		int small = select(arr, i, n);
		int temp = arr[small];
		arr[small] = arr[i];
		arr[i] = temp;
		i++;
	}
}
```

- ### Insertion Sort
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

