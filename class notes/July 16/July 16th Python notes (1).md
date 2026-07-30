**1\. Type Casting**

Type casting means changing a value from one data type into another. It is useful when the value we have is not in the correct form for the operation we want to perform.

**Implicit Type Casting**

Python changes the data type automatically. This normally happens when Python can safely convert a smaller or simpler type into a larger type.

a = 10 # integer  
b = 2.5 # float  
result = a + b  
print(result) # 12.5

Python automatically treats 10 as 10.0 so that it can be added to the float value 2.5.

**2\. Explicit Type Casting**

We manually change the data type by using functions such as int(), float(), str(), or bool().

age = "25"  
age = int(age)  
print(age + 5) # 30

The original value "25" is text. int(age) converts it into the integer 25, so it can be used in a calculation.

**3\. Basic Data Types**

A data type tells Python what kind of value is stored in a variable. The data type also determines what operations can be performed on that value.

**Integer (int)**

Stores whole numbers without decimals.

age = 30  
score = -5

**Float (float)**

Stores numbers that contain a decimal point.

price = 19.99  
temperature = 72.5

**Boolean (bool)**

Stores only True or False. Booleans are often used in conditions and decision-making.

is_student = True  
is_logged_in = False

**String (str)**

Stores text, letters, numbers, or symbols inside quotation marks. Even "123" is a string because it is inside quotes.

name = "Shristi"  
message = "Hello"  
code = "123"

**Complex (complex)**

Stores a number with a real part and an imaginary part. It is mainly used in advanced mathematics and science.

number = 3 + 4j

**4\. Naming Conventions for Variables**

Variable names should clearly describe the information they store. Good names make code easier to read and understand.

A variable name can contain letters, numbers, and underscores.

It cannot start with a number.

It cannot contain spaces.

It cannot use Python keywords such as if, for, while, or class.

Python commonly uses snake_case, where words are separated with underscores.

student_name = "Shristi"  
total_marks = 85  
phone_number = "937-000-0000"

Names like student_name and total_marks are better than unclear names such as x or a because they explain what the values represent.

**5\. Variables and Dynamic Typing**

A variable is a named container used to store a value. The equals sign (=) assigns a value to the variable.

name = "Shristi"  
age = 30

Here, name stores the string "Shristi", and age stores the integer 30.

**Dynamic Typing**

Python is dynamically typed. This means we do not need to declare a variable's data type before using it. Python identifies the type from the value assigned.

x = 10 # x is an integer  
x = "Hello" # now x is a string  
x = 3.5 # now x is a float

Although Python allows this, changing the meaning of the same variable too often can make code confusing.

**6\. Operators**

Operators are symbols or words that perform operations on values and variables.

**6.1Comparison Operators**

Comparison operators compare two values. The result is always True or False.

| Operator | Meaning                  |
| -------- | ------------------------ |
| \==      | equal to                 |
| ---      | ---                      |
| !=       | not equal to             |
| ---      | ---                      |
| \>       | greater than             |
| ---      | ---                      |
| <        | less than                |
| ---      | ---                      |
| \>=      | greater than or equal to |
| ---      | ---                      |
| <=       | less than or equal to    |
| ---      | ---                      |

age = 20  
print(age >= 18) # True

**6.2Logical Operators**

Logical operators combine or reverse conditions.

and returns True only when both conditions are True.

or returns True when at least one condition is True.

not reverses True to False or False to True.

age = 25  
print(age >= 18 and age < 30) # True  
print(age &lt; 18 or age &gt; 60) # False  
print(not age == 25) # False

**6.3Assignment Operators**

Assignment operators store or update values in variables.

x = 10 # assign 10 to x  
x += 5 # same as x = x + 5  
x -= 2 # same as x = x - 2  
x \*= 3 # same as x = x \* 3  
x /= 2 # same as x = x / 2

**7\. Input Function**

The input() function allows a user to enter information while the program is running. The prompt inside the parentheses tells the user what to enter.

name = input("Enter your name: ")  
print("Hello", name)

Important: input() always returns a string. To use the entered value as a number, convert it with int() or float().

age = int(input("Enter your age: "))  
print(age + 1)

**8\. f-Strings**

An f-string is a simple and modern way to place variables or expressions inside a string. Write the letter f before the opening quotation mark and put variables inside curly brackets {}.

name = "Shristi"  
age = 30  
print(f"My name is {name} and I am {age} years old.")

The values of name and age are inserted automatically when the string is printed. Expressions can also be used inside the braces.

price = 20  
quantity = 3  
print(f"Total: \${price \* quantity}") # Total: \$60

**9\. The .format() Method**

The .format() method is another way to insert values into a string. Empty curly brackets act as placeholders, and .format() supplies the values.

name = "Shristi"  
age = 30  
print("My name is {} and I am {} years old.".format(name, age))

It produces the same result as an f-string. f-strings are usually preferred because they are shorter and easier to read, but .format() is still common in older code.

**10\. Branching: if, elif, and else**

Branching allows a program to make decisions. Python checks a condition and runs a particular block of code depending on whether that condition is True or False.

**10.1if Statement**

The if block runs only when its condition is True.

age = 20  
<br/>if age >= 18:  
print("Adult")

**10.2if...else Statement**

Use else when there are two possible outcomes. If the if condition is False, the else block runs.

age = 15  
<br/>if age >= 18:  
print("Adult")  
else:  
print("Minor")

**10.3if...elif...else Statement**

Use elif when several conditions must be checked. Python checks them from top to bottom and runs the first block whose condition is True.

marks = 85  
<br/>if marks >= 90:  
print("Grade A")  
elif marks >= 80:  
print("Grade B")  
else:  
print("Grade C")

**10.4Nested if**

A nested if is an if statement inside another if statement. The inner condition is checked only after the outer condition is True.

age = 20  
has_id = True  
<br/>if age >= 18:  
if has_id:  
print("Entry allowed")

Indentation is very important in Python because it shows which statements belong to each condition.

**11\. Loops and the for Loop**

A loop repeats a block of code. A for loop is mainly used to visit each item in a sequence, such as a list or string, or to repeat code a known number of times.

**11.1Using range()**

range(5) produces the numbers 0, 1, 2, 3, and 4. The ending number is not included.

for i in range(5):  
print(i)

**11.2Looping Through a List**

The loop takes one item from the list during each repetition.

fruits = \["Apple", "Banana", "Mango"\]  
<br/>for fruit in fruits:  
print(fruit)

**11.3Looping Through a String**

A string is a sequence of characters, so a for loop can process one character at a time.

for letter in "Python":  
print(letter)

The indented code under the for statement is called the loop body. It runs once for every item.

