#  Binary_search_algorithm
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

In programming, we translate the "repeat the process" part into a loop. We also use special variables, often called pointers, to mark the boundaries of our search area.

The Key Code Concepts
Pointers (low and high): These are simple variables that store the index numbers (the positions) of the first and last items in the portion of the list we are currently searching.

The Loop (while): This is the core of the algorithm. The code will repeat the same set of instructions over and over as long as the low pointer is less than or equal to the high pointer. As soon as low moves past high, the loop stops, meaning we have searched the entire list without finding the number.

Midpoint Calculation: Inside the loop, the code calculates the midpoint index.

The if/else Statement: This is where the comparison happens. The code checks if the number at the midpoint is equal to, less than, or greater than our target number. Based on the result, it moves the low or high pointer, effectively shrinking the search area by half.

This process of moving the pointers is what "clears" or "throws away" half of the list in each step, making the algorithm so fast.

E.g (JavaScript Example)

function binarySearch(sortedArray, target) {
    // Initialize the search boundaries with pointers
    let low = 0;
    let high = sortedArray.length - 1;

    // The loop repeats as long as our search area is valid
    while (low <= high) {
        // Calculate the middle index for the current search range
        const mid = Math.floor((low + high) / 2); // Math.floor handles integer division
        const midValue = sortedArray[mid];

        // Compare the middle value to our target
        if (midValue === target) {
            return mid; // Found it! Return the index
        } else if (midValue < target) {
            // The target is in the upper half.
            // We move the 'low' pointer to the element after the middle.
            low = mid + 1;
        } else { // midValue > target
            // The target is in the lower half.
            // We move the 'high' pointer to the element before the middle.
            high = mid - 1;
        }
    }
    
    return -1; // The loop finished, so the target was not found.
}
