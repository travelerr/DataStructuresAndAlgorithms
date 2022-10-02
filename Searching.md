
# Searching

## Linear Search
 - Unsorted data

## Binary Search
 - Only works on SORTED data
 - Sorts at O(log n)

```
function binarySearch(arr, val){
    let left = 0;
    let right = arr.length - 1;
    let middle = Math.floor((left + right) / 2);
    while (arr[middle] !== val && left <= right) {
        console.log(left, middle, right)
        if (val < arr[middle]) right = middle - 1;
        else left = middle + 1;
        middle = Math.floor((left + right) / 2);
    }
    return arr[middle] === val ? middle : -1
}
```
