# BASIC SORTING

## BigO
- Check each sorting algorithm performance: https://www.bigocheatsheet.com/

## Bubble Sort

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order. [Reference](https://www.geeksforgeeks.org/)

### Demo
![demo for bubble sort](../_media/bubblesort.gif)

### Visualize
- [Bubble Sort Visualizer](https://algorithm-visualizer.org/brute-force/bubble-sort)

### Code

- Start looping from with a variable called i the end of the array towards the beginning
- Start an inner loop with a variable called j from the beginning until i - 1
- if array[i] is greater than array[j+1], swap those two values.
-  Return sorted array.


```javascript
function bubbleSort(array) {
    for(let i = array.length - 1; i > 0; i--) {
        for(let j = 0; j < i; j++) {
            if(array[j] > array[j+1]) {
                let temp = array[j]
                array[j] = array[j+1]
                array[j+1] = temp        
           }
        }
    }
    return array;
}
 
// Alternative
function bubbleSort(array) {
    for(let i = 0; i > array.length; i++) {
        for(let j = 1; j < array.length; j++) {
            if(array[j] < array[j-1]) {
                let temp = array[j]
                array[j] = array[j-1]
                array[j-1] = temp        
           }
        }
    }
    return array;
}
bubbleSort([4,2,6,5,1,3])
```

## Selection Sort

The selection sort algorithm sorts an array by repeatedly finding the minimum element (considering ascending order) from unsorted part and putting it at the beginning. The algorithm maintains two subarrays in a given array.
1) The subarray which is already sorted. 
2) Remaining subarray which is unsorted.
In every iteration of selection sort, the minimum element (considering ascending order) from the unsorted subarray is picked and moved to the sorted subarray. [Reference](https://www.geeksforgeeks.org/selection-sort/)

### Demo

![demo for selection sort](../_media/selectionsort.gif)

### Visualize
- [Selection Sort Visualizer](https://algorithm-visualizer.org/brute-force/selection-sort)

### Code

- Store the first element as the smallest value you've seen so far.
- Compare this item to the next in the array until you find a smaller number.
- If a smaller number if found, designate that smaller number to be the new "minimum" and continue until the end of the array.
- if the "minimum" is not the value(index) you initially began with, swap the two values.
- Repeat this with the next element until the array is sorted.

```javascript
function selectionSort(array) {
    for(let i = 0; i < array.length - 1; i++) {
        let min = i
        for(let j = i+1; j < array.length; j++) {
            if(array[j] < array[min]) {
                min = j
            }
        }
        if(i !== min) {
            let temp = array[i]
            array[i] = array[min]
            array[min] = temp
        }
    }
    return array
}

// Alternative
function selectionSort(array) {
    for(let i = 1; i < array.length; i++) {
        let cur = array[i];
        let j = i - 1;
        while(j >= 0 && array[j] > cur) {
            array[j+1] = array[j]
            j--;
        } 
        array[j+1] = cur;
    }
    return array
}
selectionSort([4,2,6,5,1,3])
```

## Insertion Sort

Insertion sort is a simple sorting algorithm that works similar to the way you sort playing cards in your hands. The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part. [Reference](https://www.geeksforgeeks.org/)

### Demo

![demo for insertion sort](../_media/insertionsort.gif)

### Visualize
- [Insertion Sort Visualizer](https://algorithm-visualizer.org/brute-force/insertion-sort)
### Code

- Start by picking the second element in the array
- Now compare the second element witht the one before it and swap if necessary.
- Continue to the next element and if it is in the incorrect order, iterate through the sorted portion (i.e. left side) to place the element in the correct place.
- Repeat until the array is sorted.

```javascript
function insertionSort(array) {
    let temp
    for(let i = 1; i < array.length; i++) {
        temp = array[i]
        for(var j = i - 1; array[j] > temp && j > -1; j--) {
            array[j+1] = array[j]
        }
        array[j+1] = temp
   }
   return array
}

// Alternative
function insertionSort(array) {
    for(let i = 1; i < array.length; i++) {
        let cur = array[i];
        let j = i - 1;
        while(j >= 0 && array[j] > cur) {
            array[j+1] = array[j]
        }
        array[j+1] = cur;
   }
   return array
}
insertionSort([4,2,6,5,1,3]);
```

