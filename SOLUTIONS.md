# Working with Arrays: Practice Problems – Annotated Solutions

Each solution includes explanations where helpful.

## Problem 1 — Print All Values

**Goal:** Use a loop to visit every element and print it.  
We use an index-based `for` loop from `0` up to, but not including, `nums.length`.

```java
public class Problem1 extends ConsoleProgram {
    public void run() {
        int[] nums = {5, 12, 3, 9, 1};

        // Traverse from index 0 to last index (length - 1)
        for (int i = 0; i < nums.length; i++) {
            System.out.println(nums[i]);
        }
    }
}
```



## Problem 2 — Replace by Rule

**Goal:** Replace every value less than 10 with `10`.  
We loop through the array and use an `if` condition to decide when to update an element.

```java
public class Problem2 extends ConsoleProgram {
    public void run() {
        int[] nums = {4, 11, 2, 19, 10, 7};

        // Replace all values less than 10 with 10
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] < 10) {
                nums[i] = 10;
            }
        }

        // Print updated array on one line
        System.out.print("Updated: ");
        for (int i = 0; i < nums.length; i++) {
            System.out.print(nums[i] + " ");
        }
    }
}
```



## Problem 3 — Count How Many

**Goal:** Read 5 temperatures, store them in an array, then count how many are above 20.  
We use:
- a loop for input,
- a second loop (or reuse the same) to count values above the threshold.

```java
public class Problem3 extends ConsoleProgram {
    public void run() {
        int[] temps = new int[5];

        // Read 5 temperatures from the user
        for (int i = 0; i < temps.length; i++) {
            temps[i] = readInt("Enter temperature #" + (i + 1) + ": ");
        }

        // Count how many are above 20
        int countAbove20 = 0;
        for (int i = 0; i < temps.length; i++) {
            if (temps[i] > 20) {
                countAbove20++;
            }
        }

        System.out.println("There are " + countAbove20 + " temperatures above 20.");
    }
}
```



## Problem 4 — Sum and Average

**Goal:** Compute the sum and average of all elements in an array.  
We use a running total, then compute the average as `sum / length`.

```java
public class Problem4 extends ConsoleProgram {
    public void run() {
        // Example quiz scores
        int[] scores = {7, 9, 10, 8, 6, 9, 7};

        int sum = 0;

        // Add up all the scores
        for (int i = 0; i < scores.length; i++) {
            sum += scores[i];
        }

        // Use double for average to avoid integer division
        double average = (double) sum / scores.length;

        System.out.println("Sum = " + sum);
        System.out.println("Average = " + average);
    }
}
```



## Problem 5 — Find the Minimum

**Goal:** Find the smallest value in the array.  
We start by assuming the first element is the minimum, then compare each later element to it.

```java
public class Problem5 extends ConsoleProgram {
    public void run() {
        int[] ages = {18, 22, 17, 30, 25, 20};

        // Start with first element as the current minimum
        int minAge = ages[0];

        // Compare each remaining element
        for (int i = 1; i < ages.length; i++) {
            if (ages[i] < minAge) {
                minAge = ages[i];
            }
        }

        System.out.println("Youngest age: " + minAge);
    }
}
```



## Problem 6 — Does It Exist?

**Goal:** Ask for a number and check if it exists in the array.  
We use a boolean `found` flag and a linear search.

```java
public class Problem6 extends ConsoleProgram {
    public void run() {
        int[] data = {12, 44, 29, 67, 44, 18};

        int target = readInt("Enter a number between 1 and 100: ");

        boolean found = false;

        // Linear search: check each element one at a time
        for (int i = 0; i < data.length; i++) {
            if (data[i] == target) {
                found = true;
                // We could break here to stop early, but it is optional
            }
        }

        if (found) {
            System.out.println("Found");
        } else {
            System.out.println("Not found");
        }
    }
}
```



## Problem 7 — First and Last Match

**Goal:** Check whether the first and last values in the array are equal.  
We compare index `0` to index `length - 1`.

```java
public class Problem7 extends ConsoleProgram {
    public void run() {
        double[] values = {3.5, 1.2, 6.8, 1.2, 3.5};

        // Compare first and last using indices
        boolean match = (values[0] == values[values.length - 1]);

        System.out.println("First and last match: " + match);
    }
}
```



## Problem 8 — Index of Target

**Goal:** Ask for a target number and report its index in the array, or `-1` if not found.  
We track the position in a variable and initialize it to `-1` to mean “not found”.

```java
public class Problem8 extends ConsoleProgram {
    public void run() {
        int[] points = {14, 9, 27, 31, 18};

        int target = readInt("Enter a target: ");

        int indexFound = -1;  // -1 means "not found"

        for (int i = 0; i < points.length; i++) {
            if (points[i] == target) {
                indexFound = i;
                break;  // stop once we find the first match
            }
        }

        if (indexFound == -1) {
            System.out.println("Not found (index = -1)");
        } else {
            System.out.println("Found at index: " + indexFound);
        }
    }
}
```



## Problem 9 — Print in Reverse

**Goal:** Read 5 numbers from the user and then print them in reverse order.  
We:
1. fill the array from index `0` upwards,  
2. then use a second loop from `length - 1` down to `0` to print values backwards.

```java
public class Problem9 extends ConsoleProgram {
    public void run() {
        int[] nums = new int[5];

        // Read 5 numbers
        for (int i = 0; i < nums.length; i++) {
            nums[i] = readInt("Enter number #" + (i + 1) + ": ");
        }

        // Print in reverse order
        System.out.print("Reverse: ");
        for (int i = nums.length - 1; i >= 0; i--) {
            System.out.print(nums[i] + " ");
        }
    }
}
```



## Problem 10 — Above Average

**Goal:** Read 8 scores, compute the average, then print all scores above that average.  
We use:
- one loop to fill the array,
- a second loop to compute the sum,
- a third loop to print values strictly greater than the average.

```java
public class Problem10 extends ConsoleProgram {
    public void run() {
        int[] scores = new int[8];

        // Step 1: read scores into the array
        for (int i = 0; i < scores.length; i++) {
            scores[i] = readInt("Enter score #" + (i + 1) + ": ");
        }

        // Step 2: compute the sum
        int sum = 0;
        for (int i = 0; i < scores.length; i++) {
            sum += scores[i];
        }

        // Step 3: compute the average as a double
        double average = (double) sum / scores.length;
        System.out.println("Average = " + average);

        // Step 4: print all scores above the average
        System.out.print("Above average: ");
        for (int i = 0; i < scores.length; i++) {
            if (scores[i] > average) {
                System.out.print(scores[i] + " ");
            }
        }
    }
}
```
