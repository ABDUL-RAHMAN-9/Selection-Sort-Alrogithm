# Selection-Sort-Alrogithm

Selection Sort is a comparison-based sorting algorithm. It sorts an array by repeatedly selecting the smallest (or largest) element from the unsorted portion and swapping it with the first unsorted element. This process continues until the entire array is sorted.

1.First we find the smallest element and swap it with the first element. This way we get the smallest element at its correct position.

2.Then we find the smallest among remaining elements (or second smallest) and swap it with the second element.

3.We keep doing this until we get all elements moved to correct position.

# Steps:
<div align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134343/Selection-Sort-Algorithm-1.webp" width="400">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134343/Selection-Sort-Algorithm-2.webp" width="400">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134344/Selection-Sort-Algorithm-3.webp" width="400">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134345/Selection-Sort-Algorithm-4.webp" width="400">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134345/Selection-Sort-Algorithm-5.webp" width="400">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240926134346/Selection-Sort-Algorithm-6.webp" width="400">
</div>

# Code:

```
// C++ program to implement Selection Sort
#include <bits/stdc++.h>
using namespace std;

void selectionSort(vector<int> &arr) {
    int n = arr.size();

    for (int i = 0; i < n - 1; ++i) {

        // Assume the current position holds
        // the minimum element
        int min_idx = i;

        // Iterate through the unsorted portion
        // to find the actual minimum
        for (int j = i + 1; j < n; ++j) {
            if (arr[j] < arr[min_idx]) {

                // Update min_idx if a smaller
                // element is found
                min_idx = j; 
            }
        }

        // Move minimum element to its
        // correct position
        swap(arr[i], arr[min_idx]);
    }
}

void printArray(vector<int> &arr) {
    for (int &val : arr) {
        cout << val << " ";
    }
    cout << endl;
}

int main() {
    vector<int> arr = {64, 25, 12, 22, 11};

    cout << "Original array: ";
    printArray(arr); 

    selectionSort(arr);

    cout << "Sorted array: ";
    printArray(arr);

    return 0;
}
```

# Output:

```
Original vector: 64 25 12 22 11 
Sorted vector:   11 12 22 25 64
```

# Complexity Analysis:
- Time Complexity: O(n²). It involves nested loops to find the minimum element for each position.
- Space Complexity: O(1). It's an in-place sorting algorithm that doesn't require extra space.

