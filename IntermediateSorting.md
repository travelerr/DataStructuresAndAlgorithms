# Intermediate Sorting

## Quick Sort

## Merge Sort

 - Break array into single item ( [x] ) arrays
 - Uses a helper function to merge two sorted arrays

 ![image](screenshots/merge.png)
 
 ![image](screenshots/mergep.png)


 The Merge:

 ```
 function mergeArray(arr1, arr2) {
     let result = [];
     let i = 0;
     let j = 0;
     while (i < arr1.length && j < arr2.length){
         if(arr1[i] < arr2[j]){
             result.push(arr1[i]);
             i++;
         } else {
             result.push(arr2[j])
             j++
         }
         while(i < arr1.length) {
             result.push(arr1[i]);
             i++;
         }
         while(j < arr2.length) {
             result.push(arr2[j]);
             j++;
         }
     }
     return result;
 }

 mergeArray([2, 3, 7], [4, 6, 9, 10])
 ```

 ![image](screenshots/mergesortp.png)

 Full Merge Sort implementation

 ```
 function mergeSort(arr) {
    if (arr.length <= 1) return arr
    let midPoint = Math.floor(arr.length / 2)
    let left = mergeSort(arr.slice(0, midPoint))
    let right = mergeSort(arr.slice(midPoint))
    return mergeArray(left, right)
}

 function mergeArray(arr1, arr2) {
     let result = [];
     let i = 0;
     let j = 0;
     while (i < arr1.length && j < arr2.length){
         if(arr1[i] < arr2[j]){
             result.push(arr1[i]);
             i++;
         } else {
             result.push(arr2[j])
             j++
         }
         while(i < arr1.length) {
             result.push(arr1[i]);
             i++;
         }
         while(j < arr2.length) {
             result.push(arr2[j]);
             j++;
         }
     }
     return result;
 }

mergeSort([3, 34, 53, 2,6, 2, 99])
```

![image](screenshots/mergesortbigo.png)

## Radix Sort
