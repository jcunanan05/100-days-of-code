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
