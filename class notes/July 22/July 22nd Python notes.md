**1\. Functions**

A function is a reusable block of code that performs a specific task. Instead of writing the same code multiple times, we write it once inside a function and call it whenever needed.  
<br/>**Real-life example:** Think of a coffee machine. Every time you press the button, it performs the same steps. Similarly, a function performs the same task whenever it is called.  
<br/>Example:  
<br/>def greet():  
print('Hello!')  
<br/>greet()

**2\. Why do we create Functions?**

• Avoid repeating code.  
• Make programs easier to read.  
• Make debugging easier.  
• Reuse code anywhere in the program.

**3\. def Statement**

The keyword 'def' is used to define (create) a function.  
<br/>Example:  
<br/>def add(a,b):  
print(a+b)  
<br/>add(5,6)  
Output: 11

**4\. Parameters and Arguments**

Parameters are variables written in the function definition. Arguments are the actual values passed when calling the function.  
<br/>Example:  
<br/>def multiply(x,y):  
return x\*y  
<br/>multiply(3,4)  
Here x and y are parameters, while 3 and 4 are arguments.

**5\. return Statement**

The return statement sends a value back to the place where the function was called. Unlike print(), the returned value can be stored in a variable.  
<br/>Example:  
<br/>def square(n):  
return n\*n  
<br/>result = square(5)  
print(result)  
Output: 25

**6\. Iterators**

An iterator is an object that allows you to access elements one at a time instead of all at once. Lists, tuples, strings, dictionaries and sets are iterable objects.  
<br/>Example:  
nums=\[10,20,30\]  
for n in nums:  
print(n)

**7\. Generators**

A generator is a special type of function that uses the 'yield' keyword instead of 'return'. It produces one value at a time, saving memory.  
<br/>Example:  
<br/>def count():  
yield 1  
yield 2  
yield 3

**8\. yield vs return**

return ends the function immediately.  
yield pauses the function, remembers its state, and continues from the same place the next time it is called.  
Generators are useful when working with large amounts of data.

**9\. Fibonacci Sequence**

The Fibonacci sequence starts with 0 and 1. Every next number is the sum of the previous two.  
<br/>0, 1, 1, 2, 3, 5, 8, 13...

**10\. map()**

map() applies a function to every element of an iterable.  
Syntax:  
map(function, iterable)  
<br/>Example:  
nums=\[1,2,3\]  
result=map(lambda x:x\*2, nums)  
Output: \[2,4,6\]

**11\. reduce()**

reduce() repeatedly applies a function to an iterable until only one value remains. It is available in the functools module.  
<br/>Example:  
from functools import reduce  
reduce(lambda x,y:x+y,\[1,2,3,4\])  
Output: 10

**12\. lambda Function**

A lambda function is a small anonymous function used for short operations.  
<br/>Example:  
square=lambda x:x\*x  
print(square(5))  
Output:25

**13\. filter()**

filter() selects only those elements that satisfy a condition.  
Syntax:  
filter(function, iterable)  
<br/>Example:  
nums=\[1,2,3,4,5,6\]  
even=filter(lambda x:x%2==0, nums)  
Output: \[2,4,6\]

**14\. Quick Comparison**

| Concept   | Purpose                          |
| --------- | -------------------------------- |
| Function  | Reuse code                       |
| ---       | ---                              |
| return    | Send back one final value        |
| ---       | ---                              |
| yield     | Generate values one at a time    |
| ---       | ---                              |
| Iterator  | Read one element at a time       |
| ---       | ---                              |
| Generator | Memory-efficient iterator        |
| ---       | ---                              |
| map()     | Apply a function to every item   |
| ---       | ---                              |
| filter()  | Keep only matching items         |
| ---       | ---                              |
| reduce()  | Reduce many values into one      |
| ---       | ---                              |
| lambda    | Create a quick one-line function |
| ---       | ---                              |

