# binary_search_algorithm
Know more about the binary search algorithm

#Algorithm
As we know, algorithms are sets of instructions or processes that guide us on how to complete a particular task. One example of these algorithms is the Binary Search algorithm. The Binary Search algorithm is an efficient method for finding an item in a sorted list or array. Essentially, it works by repeatedly dividing the list in half until the desired value or result is found. Here’s a breakdown of the process involved.

Let’s explain it in a relatable way. 

Imagine you have a list of numbers: `[2, 6, 1, 34, 12, 5, 7]`, and you want to find the number `1`.

First, you need to sort this list in either ascending or descending order. For our example, we will sort it in ascending order. After sorting, the list will look like this: `[1, 2, 5, 6, 7, 12, 34]`. If we were to sort it in descending order, it would appear as: `[34, 12, 7, 6, 5, 2, 1]`.

Next, find the midpoint of the sorted list. In our case, the middle number is `6`. Now, compare this midpoint with the number you’re searching for, which is `1`. Since `6` is greater than `1`, we can eliminate all numbers to the right of `6`, leaving us with `[1, 2, 5]`. 

We then repeat the process: pick the middle number from the remaining list. Check if it is greater than, less than, or equal to the number you are seeking. Continue this way until only the desired number remains in the list. That will be your answer.

--- 
Now lets explain it in code terms....

