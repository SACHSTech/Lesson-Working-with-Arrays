# Working with Arrays

This lesson expands on [Introduction to Arrays](https://github.com/SACHSTech/Lesson-Introduction-to-Arrays) by showing how to use arrays to perform meaningful tasks.  

Some of these techniques might help you solve the practice problems in the previous set as well, so it would be worth revisiting your solutions.

For every technique here, we'll look at:

1. **The goal** — What problem we are trying to solve  
2. **The design approach** — How arrays help us solve it  
3. **The code** — A clearly written example program  


## 1. Accessing Elements

### Goal  
Retrieve specific values from inside an array (first, last, any index).

### Design Approach  
To access an element, use:

```
arrayName[index]
```

You must know the correct index:
- First element → index `0`
- Last element → `array.length - 1`

This ensures your code works for *any* array size.

### Code

```java
int[] marks = {72, 85, 90, 66, 88};

System.out.println("First: " + marks[0]);
System.out.println("Last: " + marks[marks.length - 1]);
```

### Example Output

```
First: 72
Last: 88
```

<br>

## 2. Updating Elements

### Goal  
Change one value inside the array without touching the others.

### Design Approach  
Select the index you want to modify and assign a new value.  
This is just like assigning a variable—except you choose *which* element.

### Code

```java
int[] marks = {72, 85, 90, 66, 88};

marks[2] = 95;   // Update index 2 with a new mark
```

<br>

## 3. Traversing Arrays

### Goal  
Process **every** element in the array.

### Design Approach  
Use an index-based loop that runs from `0` to `array.length - 1`.  
This ensures the loop scales for any array length.

### Code

```java
for (int i = 0; i < marks.length; i++) {
    System.out.println(marks[i]);
}
```

### Example Output

```
72
85
90
66
88
```

<br>

## 4a. Computing Aggregate Values - Sum of All Elements

This section covers common operations over entire arrays.

### Goal  
Add all values in the array.

### Design Approach  
Use a running total and loop through every index.

### Code

```java
int sum = 0;

for (int i = 0; i < marks.length; i++) {
    sum += marks[i];
}

System.out.println("Sum = " + sum);
```

## 4b. Computing Aggregate Values - Average

### Goal  
Compute mean score from a list of numbers.

### Design Approach  
Use a double calculation:  
`average = sum / length`

### Code

```java
double avg = (double) sum / marks.length;
System.out.println("Average = " + avg);
```

## 4c. Computing Aggregate Values - Minimum and Maximum

### Goal  
Find the smallest and largest elements.

### Design Approach  
Start with the first element, then compare each remaining one.

### Code

```java
int min = marks[0];
int max = marks[0];

for (int i = 1; i < marks.length; i++) {
    if (marks[i] < min) {
        min = marks[i];
    }
    if (marks[i] > max) {
        max = marks[i];
    }
}
```

<br>

## 5. Searching an Array (Linear Search)

### Goal  
Check whether a target value exists in the array.

### Design Approach  
Move index by index until the value is found.

### Code (existence only)

```java
boolean found = false;
int target = 90;

for (int i = 0; i < marks.length; i++) {
    if (marks[i] == target) {
        found = true;
    }
}
```

### Code (recording the index)

```java
int pos = -1; // means “not found”

for (int i = 0; i < marks.length; i++) {
    if (marks[i] == target) {
        pos = i;
    }
}
```

<br>

## 6. Counting Occurrences

### Goal  
Count how many elements satisfy a condition.

### Design Approach  
Use an index loop and increment a counter whenever the condition is true.

### Code

```java
int count = 0;

for (int i = 0; i < marks.length; i++) {
    if (marks[i] >= 80) {
        count++;
    }
}
```

<br>

## 7. Reversing Output (Printing Backwards)

### Goal  
Print array values backwards without changing the array.

### Design Approach  
Start the loop at `length - 1`, stop at `0`, and move downward.

### Code

```java
for (int i = marks.length - 1; i >= 0; i--) {
    System.out.println(marks[i]);
}
```

### Example Output

```
88
66
90
85
72
```

<br>

# Practice Problems — Working With Arrays

Complete the following practice problems. Starter code template files can be found in the `src/` folder of this repo.

## Problem 1 — Print All Values  

Given:

```java
int[] nums = {5, 12, 3, 9, 1};
```

Print each value on its own line using a loop.

### Example Output
```
5
12
3
9
1
```


## Problem 2 — Replace by Rule  

Given an array of **6 integers**, replace every value **less than 10** with `10`.  
Print the updated array on one line.

### Example Input
```
Original array: [4, 11, 2, 19, 10, 7]
```

### Example Output
```
Updated: 10 11 10 19 10 10
```


## Problem 3 — Count How Many  

Ask the user for **5 temperatures**, store them in an array, and count how many are **above 20**.

### Example Input
```
Enter 5 temperatures:
18
22
25
17
21
```

### Example Output
```
There are 3 temperatures above 20.
```



## Problem 4 — Sum and Average  

Create an array of **7 quiz scores**.  
Compute and print the **sum** and **average**.

### Example Input
```
Scores: [7, 9, 10, 8, 6, 9, 7]
```

### Example Output
```
Sum = 56
Average = 8.0
```



## Problem 5 — Find the Minimum  

Given:

```java
int[] ages = {18, 22, 17, 30, 25, 20};
```

Print the youngest age.

### Example Output
```
Youngest age: 17
```



## Problem 6 — Does It Exist?  

Ask the user for a number between 1 and 100.

Given:

```java
int[] data = {12, 44, 29, 67, 44, 18};
```

Print **“Found”** or **“Not found”**.

### Example Input
```
Enter a number: 44
```

### Example Output
```
Found
```



## Problem 7 — First and Last Match  

Given:

```java
double[] values = {3.5, 1.2, 6.8, 1.2, 3.5};
```

Check if the **first** and **last** values are the same.

### Example Output
```
First and last match: true
```



## Problem 8 — Index of Target  

Given:

```java
int[] points = {14, 9, 27, 31, 18};
```

Ask the user for a target number and print the **index** where it appears, or `-1` if not found.

### Example Input
```
Enter a target: 27
```

### Example Output
```
Found at index: 2
```



## Problem 9 — Print in Reverse  

Ask the user for **5 numbers**.  
Print them in **reverse order**.

### Example Input
```
Enter 5 numbers:
3
9
1
4
7
```

### Example Output
```
7 4 1 9 3
```



## Problem 10 — Above Average  

Ask the user for **8** test scores.  
Compute the average.  
Print all scores **above the average**.

### Example Input
```
Scores:
10
7
8
9
6
12
11
5
```

### Example Output
```
Average = 8.5
Above average: 10 9 12 11
```
