**1\. Data Collections in Python**

Python provides five main collection data types to store multiple values. Each serves a different purpose.

• **String (str):** Stores text or characters. Example: "Hello".

• **List:** Stores multiple items in order. Lists are mutable, so items can be added, removed, or changed. Example: \[1,2,3\].

• **Tuple:** Stores ordered items that cannot be changed after creation. Example: (1,2,3).

• **Set:** Stores unique values only. Duplicates are removed automatically. Example: {1,2,3}.

• **Dictionary:** Stores data as key:value pairs. Example: {"name":"Shristi","age":25}.

**2\. For Loop**

A for loop repeats a block of code by iterating over a sequence such as a string, list, tuple, set, dictionary, or range. Going through each item one by one is called traversal.

Example:  
for fruit in \["Apple","Banana"\]:  
print(fruit)

**3\. range() Function**

The range() function generates a sequence of numbers. It is commonly used with for loops when you know how many times the loop should run.

Examples:  
range(5) -> 0,1,2,3,4  
range(1,6) -> 1,2,3,4,5

**4\. Looping by Value vs Index**

Loop by value gives each item directly.  
Example: for n in numbers:

Loop by index uses the position of each item.  
Example: for i in range(len(numbers)): print(numbers\[i\])

Use index when you need the position or want to update elements.

**5\. Reversing a String**

A string can be reversed using slicing.

Example: text\[::-1\] returns the string in reverse order.

**6\. While Loop**

A while loop repeats as long as a condition remains True. It is useful when you do not know beforehand how many times the loop will run.

Remember to update the condition inside the loop to avoid an infinite loop.

**7\. Counter Variable**

A counter keeps track of how many times a loop has been executed. It is usually increased by 1 in each iteration.

Example:  
count = 0  
count += 1

**8\. Difference Between for and while Loop**

| Feature   | for loop                        | while loop                     |
| --------- | ------------------------------- | ------------------------------ |
| Use       | Known number of iterations      | Unknown number of iterations   |
| ---       | ---                             | ---                            |
| Condition | Iterates over a sequence        | Runs while a condition is True |
| ---       | ---                             | ---                            |
| Best for  | Lists, strings, tuples, range() | User input, guessing games     |
| ---       | ---                             | ---                            |

**9\. break Statement**

The break statement immediately stops the loop, even if more iterations are left. It is used when the required result is found.

**10\. continue Statement**

The continue statement skips the current iteration and moves to the next one without stopping the loop.

**11\. reverse() Method**

reverse() reverses the order of elements in a list. It changes the original list and does not create a new one.

Example:  
numbers.reverse()