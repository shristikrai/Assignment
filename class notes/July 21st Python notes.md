**1\. String Properties**

A string is a sequence of characters enclosed in single or double quotes. Strings are immutable, which means once a string is created, its value cannot be changed. If you modify a string, Python creates a new string instead.  
<br/>Example:  
name='Shristi'  
name=name+' Rai'

**2\. String Concatenation**

Concatenation means joining two or more strings together using the '+' operator.  
Example:  
first='Hello'  
second='World'  
print(first+' '+second)  
Output: Hello World

**3\. Basic Built-in String Methods**

Common methods include upper(), lower(), title(), capitalize(), strip(), replace(), find(), count(), startswith(), endswith(). These methods help modify or check strings without changing the original string.

**4\. split()**

split() breaks a string into a list using a separator.  
Example:  
text='apple,banana,mango'  
text.split(',')  
Output: \['apple','banana','mango'\]

**5\. String Formatting**

String formatting inserts variables into text.  
Modern method:  
name='Shristi'  
print(f'Hello {name}')  
Older method:  
print('Hello {}'.format(name))

**6\. String Check Methods**

isspace() -> True if all characters are spaces.  
istitle() -> True if every word starts with a capital letter.  
isupper() -> True if all letters are uppercase.  
islower(), isdigit(), isalpha(), isalnum() work similarly.

**7\. Regular Expressions (Introduction)**

Regular Expressions (regex) are patterns used to search or validate text. They are commonly used to validate emails, phone numbers, and passwords.

**8\. Copy in Python**

Assignment (=) points two variables to the same object.  
Shallow Copy copies only the outer object.  
Deep Copy copies the entire object including nested objects.  
Use copy.copy() for shallow copy and copy.deepcopy() for deep copy.

**9\. Lists**

A list stores multiple items in order. Lists are mutable, so you can add, remove, or modify items.  
Example:  
fruits=\['Apple','Banana'\]  
fruits.append('Mango')

**10\. List vs String**

Strings store characters and cannot be modified. Lists store multiple values and can be changed after creation.

**11\. Indexing and Slicing**

Indexing accesses one element.  
Example: fruits\[0\]  
Slicing accesses multiple elements.  
Example: fruits\[1:3\]

**12\. Common List Methods**

append(x): adds item at end.  
extend(iterable): adds multiple items.  
insert(index,item): inserts at a position.  
pop(): removes by index and returns value.  
remove(value): removes first matching value.  
count(x): counts occurrences.  
index(x): returns first position.  
reverse(): reverses the list.  
sort(): sorts ascending.

**13\. Nested Lists**

A list inside another list is called a nested list.  
Example:  
marks=\[\[80,90\],\[70,85\]\]  
marks\[0\]\[1\] returns 90.

**14\. List Comprehension**

A short way to create lists.  
Example:  
squares=\[x\*x for x in range(5)\]  
Output: \[0,1,4,9,16\]

**15\. Tuples**

A tuple is similar to a list but is immutable. Once created, its values cannot be changed.  
Example:  
colors=('Red','Blue')

**16\. Tuple Methods**

Only two main methods are available:  
count() and index().  
To modify a tuple, convert it into a list, make changes, then convert it back.

**17\. Sets**

A set is an unordered collection of unique elements. Duplicate values are automatically removed.  
Useful methods: add(), discard(), remove(), pop(), clear().

**18\. Dictionaries**

A dictionary stores data as key:value pairs.  
Example:  
student={'name':'Shristi','age':25}  
Access using student\['name'\].

**19\. Nested Dictionaries**

A dictionary can contain another dictionary as its value.  
Useful for storing structured information like employee or student records.

**20\. Dictionary Comprehension**

Creates dictionaries in a single line.  
Example:  
squares={x:x\*x for x in range(5)}

**21\. Revision Tips**

• Strings are immutable.  
• Lists are mutable.  
• Tuples are immutable.  
• Sets store unique values.  
• Dictionaries store key:value pairs.  
• Use list comprehensions for cleaner code.  
• Use shallow/deep copy when working with nested collections.