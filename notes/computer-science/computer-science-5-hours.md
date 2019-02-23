# 4 Semesters of Computer Science in 5 Hours

By Brian Holt

## Intro

He wrote this material because he was frustrated on engineer interviews. Interviews sometimes asks complicated theory concepts even when they are not related to that job. So he made this to, at least in theory, let the people know some computer concepts.

### Science of tradeoffs

He mentioned that you'll always decide between readable code, more efficient code, optimized code.

But his advice 95% go for readable code. As Kyle simpson said, you're saving it for other people or your future self.

## Big O

Big O is the theoretical formula of how complex the algorithm is. It is broad strokes comparison on how would our code could perform on big data. It is like 300ms vs 30s. It isn't like 300ms vs 330ms.

## Recursion

Define something in terms of itself.

### Basic structure

- Base Case - The one that will terminate the loop. When you start recursing.

### Recursion tips

Be aggressive with your base case. The condition should prevent infinite loops that will stop stackoverflow.

Examples:

- Fibonacci sequence
- Factorial

```js
const factorial = n => {};
```

## Bubble Sort

Bubble sort is the easiest to comprehend on all the sorting algorithms.
The process is broken down like this:
[4, 2, 1, 3]

- compare 4, 2, swap if 4 > 2 `[2, 4, 1, 3]`
- compare 4, 1, swap if 4 > 1 `[2, 1, 4, 3]`
- compare 4, 3, swap if 4 > 3 `[2, 1, 3, 4]`
- and then go through the loop until it isn't all sorted.

an example code could be like this:

```js
function bubbleSort(nums) {
  do {
    var swapped = false;
    for (var i = 0; i < nums.length; i++) {
      if (nums[i] > nums[i + 1]) {
        var temp = nums[i];
        nums[i] = nums[i + 1];
        nums[i + 1] = temp;
        swapped = true;
      }
    }
  } while (swapped);
}
```

the `do` loop won't stop going through the array until it doesn't stop swapping.

## Insertion Sort

Insertion sort is great for arrays that almost close to get sorted. Worst case it will be bubble sort. It uses two loops also like bubble sort.

The process will be broken down like this.
[3,4,1,2]

- 3 > 4, do nothing
- 3 > 1, insert 1 in place of 3. `[1,4,3,2]`
- 1 > 2, do nothing
- 4 > 3, insert 3 in place of 4. `[1,3,4,2]`
- 3 > 2, insert 2 in place of 3. `[1,2,3,4]`

## Merge Sort

You'll always use this. It's reliable. Divide and conquer algorithm that is easier to understand. It uses recursion.

It will be divided into two functions, `mergeSort` and `stitch`.

- Merge sort will recursively divide the array roughly into half. There must be consistent side if ever the array is not equally divided into half.

- Stitch will be a function that will compare left and right, and sort them. Sorting will be like this.

- `[1, 2] and [3, 4]`. Compare 1 > 3, put 1 into result array. `[2] [3,4]`, result arr `[1]`.
- `[2] and [3,4]`, Compare 2 > 3, put 2 into result array. `[], [3,4]`, result arr `[1,2]`
- `[] and [3,4]` Concat result arr to left and right. `[1,2].concat([]).concat([3,4])`

example code:

```js
function mergeSort(nums) {
  if (nums.length < 2) {
    return nums;
  }
  var length = nums.length;
  var middle = Math.floor(length / 2);
  var left = nums.slice(0, middle);
  var right = nums.slice(middle, length);
  var stitched = stitch(mergeSort(left), mergeSort(right));
  return stitched;
}

function stitch(left, right) {
  var results = [];
  console.log('left:', left, ' right:', right);
  // whichever's lower, put it to new list
  while (left.length && right.length) {
    if (left[0] <= right[0]) {
      results.push(left.shift());
    } else {
      results.push(right.shift());
    }
  }
  console.log('results: ', results.concat(left, right));
  return results.concat(left, right);
}
```

### Median Values

Median values said by Brian are asked at reddit. The question is given two sorted lists, find the median values.

One solution is sort and concat them and find the median index. But it will be too slow. A good solution is like the `stitch` function at mergeSort. Instead of concatenating them, run the stitch algorithm and stop at the middle. that way you don't have to go through all the loop.

## Quick Sort

Quick sort is also a 'divide and conquer' algorithm. It uses less memory than merge sort but not all the times. Worst is case when you give it a wrong pivot at a already sorted list.

It goes like this

- Get a pivot value
- Compare the all the values to the pivot and break them into left and right list. (sort)
- after sorting, concat left, pivot value, and right list.
- Quick sort the left and right list until it cannot sort anymore.

Sample code

```js
function quickSort(nums) {
  if (nums.length < 2) return nums;
  var pivot = nums[nums.length - 1];
  var left = [];
  var right = [];
  for (var i = 0; i < nums.length - 1; i++) {
    if (nums[i] < pivot) {
      left.push(nums[i]);
    } else {
      right.push(nums[i]);
    }
  }
  return [...quickSort(left), pivot, ...quickSort(right)];
}
```
