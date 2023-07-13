---
title: "Binary Search"
tags:
- algorithms
---

# Binary Search

Tags: #algorithms 

Binary Search Algorithm is another approach to the Searching where we follow a [[divide and conquer]] approach by dividing the searching space in half and comparing the search term with the middle element until the target element is found. Binary Search Algorithm is more efficient than Linear Search Algorithm when given a sorted data collection since the no. of comparisons required to find the target element is halved every iteration.

## Algorithm

1. Start
2. Set the left or first index to be 0 and last index as `n-1`; where n=no. of elements.
3. Set the middle index to be the average of first and last indices.
4. If the target element is at the middle index, return the middle index element of the [[array]]
5. If the target element is less than the element at middle index, set the last index to be `(middle-1)`
6. If the target element is greater than the element at middle index, set the first index to be `(middle+1)`
7. Iterate over the steps 3,4,5 and 6 until the target element is found or if the first index is smaller than the last index *(in this case the element was not found)*

##### Note: This requires the array to be sorted

## Program in C

```C
#include <stdio.h>

int binarysearch (int arr[], int size, int searchitem) {
    int first = 0;
    int last = size-1;
    int middle = (first+last)/2;

    while(first<=last) {
        if(arr[middle]<searchitem) {
            first = middle+1;
            middle = (first+last)/2;
        } else if ( arr[middle] == searchitem) {
            return middle;
        } else {
            last = middle-1;
            middle = (first+last)/2;
        }
        if (first>last) {
            return -1;
        }
    }
}

int main() {
    int arr[] = {2,3,4,10,40};
    int x = 10;
    int n = sizeof(arr)/sizeof(arr[0]);
    int result = binarysearch(arr, n, x);
    if(result == -1){
        printf("Element is not present in array");
    }
    else{
        printf("Element is present at index %d", result);
    }
    return 0;
}
```

## Asymptotic Notation

Worst Case Time Complexity: `O(logn)`
Best Case Time Complexity: `O(1)`
Space Complexity: `O(1)` *it may require additional memory to store collection in a random access data structure like an [[array]]*

## Use Case

It is useful when the collection is large and sorted.

Related: [[Third Semester/Data Structures and Algorithms/Linear Search|Linear Search]]