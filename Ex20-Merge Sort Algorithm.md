# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE: 20-02-2026
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.

## Algorithm

1. Start
2. Read number of elements (n)
3. Input array elements
4. Build a max heap from the array:
5. For i from n/2 - 1 down to 0:
6.Apply heapify to maintain max heap property
7. Perform heap sort:
8. For i from n - 1 down to 0:
9.Swap the first element (root) with element at index i
10. Reduce heap size by 1
11. Apply heapify on root
12. Repeat until heap size becomes 1
13. Display the sorted array
14. Stop

## Program:
```JAVA
/*
Program tosorts a given array of integers in ascending order without using built-in sorting functions
Developed by: DILLI PRATHAP
RegisterNumber:  212224110014  
*/

import java.util.*;

public class Solution {
    
    private void swap(int[] arr, int index1, int index2) {
 int temp = arr[index1];
 arr[index1] = arr[index2];
 arr[index2] = temp;
    }

    private void heapify(int[] arr, int n, int i) {
 int largest = i;
 int left = 2 * i + 1;
 int right = 2 * i + 2;

 if (left < n && arr[left] > arr[largest]) {
   largest = left;
 }

 if (right < n && arr[right] > arr[largest]) {
   largest = right;
 }

 if (largest != i) {
   swap(arr, i, largest);
   heapify(arr, n, largest);
 }
    }

    private void heapSort(int[] arr) {
 int n = arr.length;
 for (int i = n / 2 - 1; i >= 0; i--) {
   heapify(arr, n, i);
 }

 for (int i = n - 1; i >= 0; i--) {
   swap(arr, 0, i);
   heapify(arr, i, 0);
 }
    }

    public int[] sortArray(int[] nums) {
 heapSort(nums);
 return nums;
    }

    public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 Solution solution = new Solution();

 int n = sc.nextInt();
 
 int[] nums = new int[n];
 for (int i = 0; i < n; i++) {
   nums[i] = sc.nextInt();
 }

 int[] sorted = solution.sortArray(nums);
 System.out.println("Sorted array:");
 System.out.println(Arrays.toString(sorted));

 sc.close();
    }
}
```

## Output:

<img width="561" height="182" alt="516885494-835de331-6065-4b64-bb5d-ca95365f75eb" src="https://github.com/user-attachments/assets/fbda42dc-a1db-4140-b747-1473c89537b4" />


## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
