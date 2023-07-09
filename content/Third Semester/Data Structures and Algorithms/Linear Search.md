---
title: "Linear Search"
---

# Sequential/Linear Search
Linear Search Algorithm is a rather simple algorithm that starts at one end of the list and goes through the entire list until the desired element is found, otherwise the search continues until the end of the data set.

## Algorithm
1. Start
2. First, read the search element(Target) in the [[array]]
3. Set an [[integer]] ``i = 0`` and repeat the steps until it reaches the end of the array.
4. Match the key with ``arr[i]``
5. If they key matches, return the index, otherwise increment ``i`` by 1.
6. End

##### Note: It doesn't require the array to be sorted.

## Program in C
```C
#include <stdio.h>
int search( int arr[], int n, int x){
    int i;
    for(i=0; i<n; i++){
        if(arr[i] == x){
            return i;
        }
    }
    return -1;
}

int main(){
    int arr[] = {2,3,4,10,40};
    int x = 10;
    int n = sizeof(arr)/sizeof(arr[0]);
    int result = search(arr, n, x);
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
Worst Case Time Complexity: ``O(n)``
Best Case Time Complexity: ``O(1)``
Space Complexity: ``O(1)`` *it can be performed in place without any additional memory*

## Use Case
It is useful when the collection is small and unsorted

Related: [[Binary Search]]