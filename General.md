# General

 - Uses arrays when you need order, otherwise use objects

![Screen Shot 2022-09-08 at 7.40.03 PM.png](/screenshots/Screen%20Shot%202022-09-08%20at%207.40.03%20PM.png)

![Screen Shot 2022-09-08 at 7.50.14 PM.png](/screenshots/Screen%20Shot%202022-09-08%20at%207.50.14%20PM.png)

# Frequency Counter Example

 - Good for comparing two items inputs
 - If numeric inputs, may need to convert to strings first

![Screen Shot 2022-09-10 at 6.28.28 PM.png](/screenshots/Screen%20Shot%202022-09-10%20at%206.28.28%20PM.png)


![Screen Shot 2022-09-10 at 5.13.58 PM.png](/screenshots/Screen%20Shot%202022-09-10%20at%205.13.58%20PM.png)

```
function validAnagram(str1, str2){
    if (str1.length !== str2.length) {
        return false;
    }

    let frequencyCounter1 = {};
    let frequencyCounter2 = {};

    for (let key of str1) {
        frequencyCounter1[key] = (frequencyCounter1[key] || 0) + 1;
    }

    for (let key of str2) {
        frequencyCounter2[key] = (frequencyCounter2[key] || 0) + 1;
    }

    // Custom logic here

    console.log(frequencyCounter1);
    console.log(frequencyCounter2);
}
```

# Multiple Pointers

 - May need to sort array first
 - There are 'variable' & 'fixed' windows, determined if a window size is given
 - Implementations
   - while (left < right)
   - while (right < arr.length)

![Screen Shot 2022-09-10 at 6.27.14 PM.png](/screenshots/Screen%20Shot%202022-09-10%20at%206.27.14%20PM.png)

![Screen Shot 2022-09-10 at 6.27.24 PM.png](/screenshots/Screen%20Shot%202022-09-10%20at%206.27.24%20PM.png)

```
function countUniqueValues(arr){
    // Set pointers
    let left = 0;
    let right = 1;

    if(arr.length === 0) {
        return 0;
    }

    // Custom code below
    while (right < arr.length) {
        if (arr[left] == arr[right]) {
            right++;
        }
        if (arr[left] !== arr[right]) {
            left++;
            arr[left] = arr[right];
            right++;
        }
    }
    return left + 1;
}
```

# Sliding Window
 - while([...new Set(window)].length < window.length)

![Screen Shot 2022-09-11 at 11.31.40 AM.png](/screenshots/Screen%20Shot%202022-09-11%20at%2011.31.40%20AM.png)

![Screen Shot 2022-09-11 at 11.32.18 AM.png](/screenshots/Screen%20Shot%202022-09-11%20at%2011.32.18%20AM.png)

```
function maxSubarraySum(arr, num){
  let maxSum = 0;
  let tempSum = 0;
  if (arr.length < num) return null;
  for (let i = 0; i < num; i++) {
    maxSum += arr[i];
  }
  tempSum = maxSum;
  for (let i = num; i < arr.length; i++) {
    tempSum = tempSum - arr[i - num] + arr[i];
    maxSum = Math.max(maxSum, tempSum);
  }
  return maxSum;
}

maxSubarraySum([2,6,9,2,1,8,5,6,3],3)
```

# Divide and Conquer

![Screen Shot 2022-09-11 at 11.39.57 AM.png](/screenshots/Screen%20Shot%202022-09-11%20at%2011.39.57%20AM.png)

![Screen Shot 2022-09-11 at 11.40.04 AM.png](/screenshots/Screen%20Shot%202022-09-11%20at%2011.40.04%20AM.png)



# Recursion
![Screen Shot 2022-09-14 at 7.27.43 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.27.43%20PM.png)

![Screen Shot 2022-09-14 at 7.27.18 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.27.18%20PM.png)
![Screen Shot 2022-09-14 at 7.27.37 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.27.37%20PM.png)
![Screen Shot 2022-09-14 at 7.27.51 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.27.51%20PM.png)

![Screen Shot 2022-09-14 at 7.37.18 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.37.18%20PM.png)
![Screen Shot 2022-09-14 at 7.37.31 PM.png](/screenshots/Screen%20Shot%202022-09-14%20at%207.37.31%20PM.png)


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

# Sorting

Video: https://www.youtube.com/watch?v=kPRA0W1kECg </br>
Animations: https://www.toptal.com/developers/sorting-algorithms

## Built in JS Sorting
![built-in-js-sorting.png](screenshots/built-in-js-sorting.png)


## Swapping Method

![swappping.png](screenshots/swapping.png)

### Naieve Bubble Sort code (optimized)

```
function bubbleSort(arr) {
    var noSwaps;
    //DOUBLE LOOP!
    for (let i = arr.length; i > 0; i--) {
        noSwaps = true;
        for (let j = 0; j < i - 1; j++) {
            //COMPARE!
            if (arr[j] > arr[j+1]) {
                //SWAP!
                let temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
                noSwaps = false;
            }
        }
        if(noSwaps) break;
    }
    return arr;
}
```

### Selection Sort
![selectionsort.png](screenshots/selectionsort.png)