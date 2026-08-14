# Python

## Level 1 - Python Fundamentals


<details>
  <summary> 1. Python basics and execution </summary>



### **What exactly is Python?** <br/>
> Python is a **high-level, dynamically typed, interpreted programming language with 
automatic memory management**.

- [x] **High-level** : we don't need to directly manage hardware/memory like
      it would in lower-level languages.

<details>
  <summary> code </summary>

```py
name = "Rama"
# Python handles the underlying memory details for you.
```

</details>

- [x] **Dynamically typed** : We don't have to explicitly declare a variable's type.

<details>
  <summary> code </summary>

```py
x = 10
# Python knows x is int
x = "hello"
# x is now str
```
- So the object has a type, while the variable name can refer to different objects.

</details>

- [x] **Interpreted** : Python programs are executed by the Python runtime rather than being
      compiled directly into native machine code in the same way as languages such as C/C++.

<details>
  <summary> ByteCode Execution </summary>

```py
Python source code
       ↓
     Bytecode
       ↓
 Python Virtual Machine
       ↓
     Execution
```
- CPython first compiles source code to bytecode and then executes that bytecode.

</details>

</details>
<!------------------------------------>



<details>
  <summary> 2. Variables and data types </summary>


### Variables
> Variables are **containers for storing data values**.

- Variables do not need to be declared with any particular type,
   and can even change type after they have been set.

If we want to specify the data type of a variable, this can be done with **casting**.
```py
x = str(5)    # x will be '5'
y = int(5)    # y will be 5
z = float(5)  # z will be 5.0
```

We can get the data type of a variable with the `type()` function.
```py
x = 5
y = "Rama"
print(type(x)) # int
print(type(y)) # str
```

String variables can be declared **either by using single or double quotes**.
```py
x = "Rama"
x = 'Rama'

# both are same
```

Variable names are **case-sensitive**.
```py
a = 2
A = "Rama"
# Both are different, A will not overwrite a
```

### Rules for Python variables naming:
- must start with **_a letter or the underscore character_**
- can't start with **_a number_**
- can only contain **_alpha-numeric characters and underscores_** (A-z, 0-9, and _ )
- **_case-sensitive_** (age, Age and AGE are three different variables)
- can't be any of the **_Python keywords_**.


### Python Keywords
Python has **a set of keywords that are reserved words** that can't be used as variable names, 
function names, or any other identifiers.

<details>
  <summary> 38 Keywords in Python </summary>

<br/>

| Keyword	   | Description                                               |
|------------|-----------------------------------------------------------|
| `and`	     | A logical operator                                        |
| `as`	     | To create an alias                                        |
| `assert`	 | For debugging                                             |
| `async`	   | Define an asynchronous function                           |
| `await`	   | Wait for and get a result from an awaitable               |
| `break`	   | To break out of a loop                                    |
| `case`	   | Pattern in a match statement                              |
| `class`	   | To define a class                                         |
| `continue` | To continue to the next iteration of a loop               |
| `def`	     | To define a function                                      |
| `del`      | To delete an object                                       |
| `elif`     | Used in conditional statements, same as `else if`         |
| `else`     | Used in conditional statements                            |
| `except`   | Used with exceptions, what to do when an exception occurs |
| `False`    | Boolean value, result of comparison operations            |
| `finally`  | Used with exceptions, a block of code that will be executed no matter if there is an exception or not |
| `for`      | To create a for loop                                      |
| `from`     | To import specific parts of a module                      |
| `global`   | To declare a global variable                              |
| `if`       | To make a conditional statement                           |
| `import`   | To import a module                                        |
| `in`       | To check if a value is present in a list, tuple, etc.     |
| `is`       | To test if two variables are equal                        |
| `lambda`   | To create an anonymous function                           |
| `match`    | Start a match statement (compare a value against cases)   |
| `None`     | Represents a null value                                   |
| `nonlocal` | To declare a non-local variable                           |
| `not`      | A logical operator                                        |
| `or`       | A logical operator                                        |
| `pass`     | A null statement, a statement that will do nothing        |
| `raise`    | To raise an exception                                     |
| `return`   | To exit a function and return a value                     |
| `True`     | Boolean value, result of comparison operations            |
| `try`      | To make a try...except statement                          |
| `while`    | To create a while loop                                    |
| `with`     | Used to simplify exception handling                       |
| `yield`    | To return a list of values from a generator               |

</details>

Variable names with more than one word can be difficult to read. <br/>
There are several techniques you can use to make them more readable:
- Camel Notation `myVariableName = "Ram"`
- Snake Notation `my_variable_name = "Ram"`
- Pascal Notation `MyVariableName = "Ram"`


Python allows us to assign values to multiple variables in one line:
```py
a, b, c = "mango", "Orange", "Banana"
print(a)
print(b)
print(c)
```

And we can assign the same value to multiple variables in one line:
```py
a = b = c = "mango"
print(a)
print(b)
print(c)
```

If we have a collection of values in a list, tuple etc. <br/>
Python allows us to extract the values into variables. This is called **unpacking**.
```py
fruits = ["apple", "banana", "mango"]
a, b, c = fruits
print(a)
print(b)
print(c)
```

### Printing Variables

<details>
  <summary> Example </summary>

```py
x = "Python"
print(x)   # Python
----------------------------------
a = "Python"
b = "is"
c = "great"
print(a, b, c) # Python is great
----------------------------------
x = "Python"
y = "is"
z = "great"
print(x + y + z) # Pythonisgreat
----------------------------------
a = 5
b = 10
print(a + b)  # 15
----------------------------------
a = 2
b = "good"
print(a + b)  # TypeError: unsupported operand type(s) for +: 'int' and 'str'
----------------------------------
a = 2
b = "good"
print(a, b)  # 2 good
```
</details>


### Global Variables
Variables that are created outside of a function are known as **global variables**.

Global variables can be used by everyone, both inside of functions and outside.

```py
x = 5

def myfunc():
  print(10 + x)

myfunc() # 15
```

If we create a variable with the same name inside a function, this variable will be local, and 
can only be used inside the function. <br/>
The global variable with the same name will remain as it was, global and with the original value.

```py
x = 5

def myfunc():
  x = 2
  print(10 + x)

myfunc()       # 12
print(10 + x)  # 15

```

To create a global variable inside a function, we have to use the `global` keyword.
```py
def myfunc():
  global x
  x = 7

myfunc()

print(10 + x)  # 17
---------------------------
x = 5

def myfunc():
  global x
  x = 7

myfunc()
print(10 + x)  # 17
```

### Variable : with a different views

```py
x = 10
# Beginner : x is a box(container) having the value 10
----------------------------------------------------------------------
# Advance : x ───► 10, x is a name/reference associated with an object
----------------------------------------------------------------------
x = 10
y = x

      ┌───────┐
x ───►│       │
      │  10   │
y ───►│       │
      └───────┘
# Both names x, y refer to the same integer object at that moment.
# Later we will see mutable objects.
```


</details>
<!------------------------------------>



<details>
  <summary> 3. <code> int </code>, <code> float </code>, <code> str </code>, <code> bool </code>,
    <code> None </code> </summary>


### Built-in data types in python

`int`, `float`, `str`, `bool`, `list`, `tuple`, `set`, `dict`, `NoneType`

|  Type          |        datatype                     |
|----------------|-------------------------------------|
| Text Type      |	`str`                              |
| Numeric Types  |	`int`, `float`, `complex`          |
| Sequence Types |	`list`, `tuple`, `range`           |
| Mapping Type   |	`dict`                             | 
| Set Types      |	`set`, `frozenset`                 |
| Boolean Type   | `bool`                              |
| Binary Types   |	`bytes`, `bytearray`, `memoryview` |
| None Type      |	`NoneType`                         |

```py
age = 25                             # int
salary = 50000.50                    # float
a = 1j                               # complex
name = "Ram"                         # str
is_active = True                     # bool
numbers = [1, 2, 3]                  # list
point = (10, 20)                     # tuple
unique = {1, 2, 3}                   # set
person = {"name": "Ram", "age": 25}  # dict
result = None                        # NoneType
```
We can inspect a type using : `type(age)`.

</details>
<!------------------------------------>



<details>
  <summary> 4. Type conversion </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 5. Operators </summary>

<br/>

> Operators are used to perform operations on variables(Operands) and values.

### Arithmetic operators : `+`,`-`,`*`,`/`,`%`,`**`,`//`
<details>
  <summary> Arithmetic operators </summary>

> Arithmetic operators are used to perform common mathematical operations:

| Operator | Name           | Expression |   Example     |
|----------|----------------|------------|---------------|
| `+`	     | Addition	      | `x + y`	   | `5 + 7 = 12`  |
| `-`	     | Subtraction	  | `x - y`	   | `7 - 5 = 2`   |
| `*`	     | Multiplication	| `x * y`	   | `5 * 7 = 35`  |
| `/`	     | Division	      | `x / y`	   | `10 / 2 = 5`  |
| `%`	     | Modulus	      | `x % y`	   | `5 / 2 = 1`   |
| `**`	   | Exponentiation	| `x ** y`   | `2 ** 5 = 32` |
| `//`     |	Floor division|	`x // y`   | `15 // 2 = 7` |

</details>

### Assignment operators : `=`,`+=`,`&=`,`>>=`
<details>
  <summary> Assignment operators </summary>

> Assignment operators are used to assign values to variables:

| Operator | Example	      | Same As	    |
|----------|----------------|-------------|
| `=`	     | x = 5	        | x = 5	      |
| `+=`	   | x += 3	        | x = x + 3	  |
| `-=`	   | x -= 3	        | x = x - 3	  |
| `*=`     | x *= 3	        | x = x * 3	  |
| `/=`     | x /= 3	        | x = x / 3	  |
| `%=`     | x %= 3	        | x = x % 3	  |
| `//=`    | x //= 3	      | x = x // 3	|
| `**=`    | x **= 3	      | x = x ** 3	|
| `&=`     | x &= 3	        | x = x & 3	  |
| l=       | x l= 3	        | x = x l 3	  |
| `^=`     | x ^= 3	        | x = x ^ 3	  |
| `>>=`    | x >>= 3	      | x = x >> 3	|
| `<<=`    | x <<= 3	      | x = x << 3	|
| `:=`     | print(x := 3)	| x = 3 print(x) |

**The Walrus Operator (`:=`)**
- Python 3.8 introduced the := operator, known as the "walrus operator".
- It assigns values to variables as part of a larger expression:

```py
# Example : The count variable is assigned in the if statement, and given the value 5:

numbers = [1, 2, 3, 4, 5]

if (count := len(numbers)) > 3:
    print(f"List has {count} elements")

# output : List has 5 elements
```
</details>

### Ternary Operator : `a if a>b else b`
<details>
  <summary> Ternary Operator </summary>

> The ternary operator allows you to assign one value if a condition is true, and another if it is false:

```py
num = 7

x = "Even" if num % 2 == 0 else "Odd"

print(x) # Odd
```

```py
num = 1

x = "Sat" if num == 6 else "Sun" if num == 7  else "weekday"

print(x)  # weekday

```
</details>

### Comparison operators : `==`,`!=`,`>`,`<`,`>=`,`<=`
<details>
  <summary> Comparison operators </summary>

> Comparison operators are used to compare two values.

- Comparison operators return `True` or `False` based on the comparison:

| Operator | Name	                     | Example	|
|----------|---------------------------|----------|
| `==`     |	Equal	                   | x == y	  |
| `!=`     |	Not equal	               | x != y	  |
| `>`      |	Greater than             | x > y	  |
| `<`      |	Less than	               | x < y	  |
| `>=`     |	Greater than or equal to | x >= y	  |
| `<=`     |	Less than or equal to	   | x <= y	  |


```py
x = 5
y = 3

print(x == y)  # False
print(x != y)  # True
print(x > y)   # True
print(x < y)   # False
print(x >= y)  # True
print(x <= y)  # False
```

**Chaining Comparison Operators**
- Python allows us to chain comparison operators:
```py
x = 5
print(1 < x < 10)        # True
print(1 < x and x < 10)  # True
```
</details>

### Logical operators : `and`, `or`, `not` 
<details>
  <summary> Logical operators </summary>

> Logical operators are used to combine conditional statements.

| Operator | Description	                                           | Example	             |
|----------|---------------------------------------------------------|-----------------------|
| `and` 	 | Returns True if both statements are true	               | x < 5 and  x < 10	   |
| `or`	   | Returns True if one of the statements is true	         | x < 5 or x < 4	       |
| `not`	   | Reverse the result, returns False if the result is true |	not(x < 5 and x < 10)|

```py
x = 5
print(x > 0 and x < 10)       # True
print(x < 5 or x > 10)        # False
print(not(x > 3 and x < 10))  # False
```
</details>

### Identity operators : `is`, `is not`
<details>
  <summary> Identity operators </summary>

> Identity operators are used to compare the objects, not if they are equal,
> but if they are actually the same object, with the same memory location.

| Operator | Description	                                          | Example	   |
|----------|--------------------------------------------------------|------------|
| `is`     | Returns True if both variables are the same object     |	x is y	   |
| `is not` | Returns True if both variables are not the same object	| x is not y |

```py
x = ["apple", "banana"]
y = ["apple", "banana"]
z = x

print(x is z)  # True   bcuz z is pointing the same x
print(x is y)  # False  bcuz checking reference
print(x == y)  # True   bcuz checking value not reference

----------------------------------------------------------

x = ["apple", "banana"]
y = ["apple", "banana"]

print(x is not y)  # True bcuz both x, y are pointing two objects
```

**Difference Between `is` and `==`**
- `is` : Checks if both variables point to the same object in memory
- `==` : Checks if the values of both variables are equal

</details>

### Membership operators : `in`, `not in`
<details>
  <summary> Membership operators </summary>

> Membership operators are used to test if a sequence is presented in an object.

| Operator	| Description	                                                                | Example |
|-----------|-----------------------------------------------------------------------------|---------|
| `in` 	    | Returns True if a sequence with the specified value is present in the object| x in y	|
| `not in`	| Returns True if a sequence with the specified value is not present in the object| x not in y |

```py
fruits = ["apple", "banana", "mango"]
print("mango" in fruits)          # True
print("orange" in fruits)         # False
print("apple" not in fruits)      # False
print("pineapple" not in fruits)  # True
```

The membership operators also work with strings.
```py
sentence = "Hello World"

print("H" in sentence)      # True
print("hello" in sentence)  # False
print("m" not in sentence)  # True
```
</details>

### Bitwise operators : `&`, l, `^`, `~`, `<<`, `>>` 
<details>
  <summary> Bitwise operators </summary>

> Bitwise operators are used to compare (binary) numbers.

| Operator | Name	| Description	                        | Example |
|----------|------|-------------------------------------|---------|
| `&`      | AND	| Sets each bit to 1 if both bits are 1 |	x & y	|
|  l       | OR	  | Sets each bit to 1 if one of two bits is 1 |	x l y |	
| `^`      | XOR	| Sets each bit to 1 if only one of two bits is 1 |	x ^ y |	
| `~`      | NOT	| Inverts all the bits |	~x  |	
| `<<`     | Zero fill left shift	| Shift left by pushing zeros in from the right and let the leftmost bits fall off	| x << 2	|
| `>>`     | Signed right shift	| Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off | x >> 2 |

```py

"""
& operator compares each bit and set it to 1 if both are 1, otherwise it is set to 0
 6 =     0110
 3 =   & 0011
      -----------
         0010      ---> 2
      -----------
"""
print(6 & 3) # 2
----------------------------------------
"""
| operator compares each bit and set it to 1 if one or both is 1, otherwise it is set to 0
 6 =     0110
 3 =   | 0011
      -----------
         0111      ---> 7
      -----------
"""
print(6 | 3) # 7
----------------------------------------
"""
^ operator compares each bit and set it to 1 if only one is 1, otherwise it is set to 0
 6 =     0110
 3 =   ^ 0011
      -----------
         0101      ---> 5
      -----------
print(6 ^ 3)  # 5
-----------------------------------------
"""
~ operator inverts each bit (0 becomes 1 and 1 becomes 0).

Inverted 3 becomes -4:
 3 = 0000000000000011
-4 = 1111111111111100

Decimal numbers and their binary values:
 4 = 0000000000000100
 3 = 0000000000000011
 2 = 0000000000000010
 1 = 0000000000000001
 0 = 0000000000000000
-1 = 1111111111111111
-2 = 1111111111111110
-3 = 1111111111111101
-4 = 1111111111111100
"""
print(~3) # -4
--------------------------------------------
"""
<< operator inserts the specified number of 0's (in this case 2) from the right and
 let the same amount of leftmost bits fall off:

If you push 00 in from the left:
 3 = 0000000000000011
becomes
12 = 0000000000001100

Decimal numbers and their binary values:
 0 = 0000000000000000
 1 = 0000000000000001
 2 = 0000000000000010
 3 = 0000000000000011
 4 = 0000000000000100
 5 = 0000000000000101
 6 = 0000000000000110
 7 = 0000000000000111
 8 = 0000000000001000
 9 = 0000000000001001
10 = 0000000000001010
11 = 0000000000001011
12 = 0000000000001100
"""
print(3 << 2)  # 12
---------------------------------------
"""
>> operator moves each bit the specified number of times to the right.
Empty holes at the left are filled with 0's.

If you move each bit 2 times to the right, 8 becomes 2:
 8 = 0000000000001000
becomes
 2 = 0000000000000010

Decimal numbers and their binary values:
 0 = 0000000000000000
 1 = 0000000000000001
 2 = 0000000000000010
 3 = 0000000000000011
 4 = 0000000000000100
 5 = 0000000000000101
 6 = 0000000000000110
 7 = 0000000000000111
 8 = 0000000000001000
 9 = 0000000000001001
10 = 0000000000001010
11 = 0000000000001011
12 = 0000000000001100
"""
print(8 >> 2)   # 2 
```
</details>

### Operator Precedence in python
<details>
  <summary> Operator Precedence in python </summary>

| Priority | Operator	                         | Description	                                        |
|----------|-----------------------------------|------------------------------------------------------|
| Top      | `()`	                             | Parentheses	                                        |
|          | `**`	                             | Exponentiation	                                      |
|          | `+x` `-x` `~x`                    | Unary plus, unary minus, and bitwise NOT	            |
|          | `*` `/` `//` `%`                  | Multiplication, division, floor division, and modulus|	
|          | `+` `-`	                         | Addition and subtraction	                            |
|          | `<<`  `>>`                        | Bitwise left and right shifts	                      |
|          | `&`                               | Bitwise AND	                                        |
|          | `^`                               | Bitwise XOR	                                        |
|	         | l                                 | Bitwise OR	                                          |
|          | == ,!=,>,>=,<,<=,is,is not,in,not in | Comparisons, identity, and membership operators	  |
|          | `not`	                           | Logical NOT	                                        |
|          | `and`	                           | AND	                                                |
| Least    | `or`                              | OR                                                   |

**If two operators have the same precedence, the expression is evaluated from left to right.**
```py
print(5 + 4 - 7 + 3)  # 5
```

</details>

</details>
<!------------------------------------>



<details>
  <summary> 6. Conditionals : <code> if / elif / else </code> </summary>

<details>
  <summary> <code> if </code> </summary>

```py
a = 5
b = 10
if b > a:
print("b is greater than a") # Indentation Error
```

**Indentation**
- Python relies on **indentation (whitespace at the beginning of a line)** to define scope in the code. 
- Other programming languages often use curly-brackets `{}` for this purpose.

We can use **`spaces` or `tabs` for indentation**, but you must use the same amount of indentation for all statements within the same code block.

```py
a = 5
b = 10
if b > a:
  print("b is greater than a") # b is greater than a
```
Multiple Statements in `If` Block
```py
age = 20
if age >= 18:
  print("You're an adult")             # You are an adult
  print("You can vote")                # You can vote
  print("You have full legal rights")  # You have full legal rights
  print(3+7)                           # 10
```

Zero (`0`), empty strings (`""`), `None`, and empty collections are treated as `False`. Everything else is treated as `True`.
```py
isLogIn = True
if isLogIn:
  print("Welcome back!")
```
</details>



<details>
  <summary> <code> elif </code> </summary>

> `elif` is nothing but `else if`.

`elif` can't exists without `if`.

```py
a = 5
b = 5
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```

**Multiple `elif`**
```py
score = 85

if score >= 90:
  print("Grade: A")
elif score >= 80:
  print("Grade: B")
elif score >= 70:
  print("Grade: C")
elif score >= 60:
  print("Grade: D")
```

**How `elif` works?** <br/>
Only the first true condition will be executed. Even if multiple conditions are true, Python stops after executing the first matching block.

**When to use `elif`?** <br/>
`elif` is more efficient than using multiple separate `if` statements bcuz Python stops checking once it finds a true condition.

</details>


<details>
  <summary> <code> else </code> </summary>

The `else` statement is executed when the `if` condition (and any `elif` conditions) are not true.

`else` can't exists without `if`.

The `else` statement must come last. We can't have an `elif` or `if` after an `else`.

```py
a = 10
b = 20
if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```

```py
a = 10
b = 10
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```
</details>


<details>
  <summary> Short Hand <code> if </code> </summary>

> Short Hand `if` is nothing but one-liner `if` statement

```py
a = 5
b = 2
if a > b: print("a is greater than b")
```

```py
a = 2
b = 3
print("A") if a > b else print("B")

# This is called a conditional expression (sometimes known as a "ternary operator").
```

Assign a Value With `If Else`
```py
a = 10
b = 20
bigger = a if a > b else b
print("Bigger is", bigger)
```
</details>


<details>
  <summary> Nested <code> if </code> </summary>

We can have `if` inside `if` statements. This is called **nested `if`** statements.

```py
age = 25
has_license = True

if age >= 18:
  if has_license:
    print("You can drive")
  else:
    print("You need a license")
else:
  print("You are too young to drive")
```

Sometimes nested `if` statements can be simplified using logical operators `and` depends on logic.
```py
temp = 25
is_sunny = True

if temp > 20:
  if is_sunny:
    print("Perfect beach weather!")

-----------------------------------------

temp = 25
is_sunny = True

if temp > 20 and is_sunny:
  print("Perfect beach weather!")
```
</details>


</details>
<!------------------------------------>




<details>
  <summary> 7. Loops : <code> for </code> and <code> while </code> </summary>

<br/>

Python has two primitive loops :
1. `while` loop
2. `for` loop

<details>
  <summary> <code> while </code> </summary>

With the `while` loop we can execute a set of statements as long as a condition is true.
```py
i = 1
while i < 5:
  print(i)
  i += 1
```

Remember to increment i(updation), or else the loop will continue forever.

</details>

<details>
  <summary> <code>while() + else{}</code> </summary>

With the `else` statement we can run a block of code once when the condition no longer is true.
```py
i = 1
while i < 5:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```
</details>



<details>
  <summary> <code> for </code> </summary>

A `for` loop is used for iterating over a sequence ( `list`, `tuple`, `dictionary`, `set`, `string`).

```py
fruits = ["apple", "banana", "orange"]
for i in fruits:
  print(i)

for ch in "Apple":
  print(ch)
```

</details>

<details>
  <summary> <code> range() </code> Function </summary>


`range()` function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.

```py
for i in range(5):
  print(i)

# Output : 0, 1, 2, 3, 4
-------------------------------

for i in range(2, 5):
  print(i)

#  Output : 2, 3, 4
--------------------------------

for i in range(1, 10, 2):
  print(i)

# Output : 1, 3, 5, 7, 9
```
</details>

<details>
  <summary> <code> for() + else{} </code> </summary>

```py
for x in range(5):
  print(x)
else:
  print("Loop Ended!")

# Output : 0, 1, 2, 3, 4 and then Loop Ended
```

</details>

<details>
  <summary> Nested Loop </summary>


**A nested loop is a loop inside a loop**.

**inner loop** will be executed one time for each iteration of the **outer loop**.

```py
i = 1;
while(i < 6):
  j = 0;
  while(j < i):
    print(j+1, end=" ")
    j += 1;
    
  i += 1;
  print();
--------------------------
for i in range(1,6):
  for j in range(i):
    print(j+1, end=" ")
    
  print();

# Output :
1 
1 2 
1 2 3 
1 2 3 4 
1 2 3 4 5 
```
</details>




</details>
<!------------------------------------>



<details>
  <summary> 8. <code> break </code>, <code> continue </code>, <code> pass </code> </summary>


### `break`

With the `break` statement we can stop the loop even if the while condition is true.

```py
i = 1
while i < 5:
  print(i)
  if i == 3:
    break
  i += 1
```

### `continue` 

With the `continue` statement we can stop the current iteration, and continue with the next.

```py
i = 0
while i < 5:
  i += 1
  if i == 3:
    continue
  print(i)
```

### `pass`

`if` statements can't be empty, but if you for some reason have an `if` statement with no content, put in the `pass` statement to avoid getting an error.

 `pass` statement is a null operation - nothing happens when it executes. It serves as a placeholder.

```py
a = 100
b = 200

if b > a:
  pass
```

During development, you might want to sketch out your program structure before implementing the details. The pass statement allows you to do this without syntax errors.

```py
age = 20

if age < 18:
  pass # TODO: Add underage logic later
else:
  print("Access granted")
```

**`pass` in `while` and `for` loop**

Loops can't be empty, but if you for some reason then use `pass` otherwise it will throw an error.

```py
i = 1
while i < 5:
  # can't be empty
```

```py
i = 1
while i < 5:
  pass

for x in [1, 2, 3, 4, 5]:
  pass
```


<details>
  <summary> <code> pass </code> vs comments </summary>

A comment is ignored by python, but `pass` is an actual statement that gets executed (though it does nothing). 

You need `pass` where Python expects a statement, not just a comment.

Error :
```py
score = 85

if score > 90:
  # This is excellent   ### IndentationError

print("Score processed")
```
Success :
```py
score = 85

if score > 90:
  pass # This is excellent

print("Score processed")
```
</details>


</details>
<!------------------------------------>



## Level 2 - Data Structures


<details>
  <summary> 9. Strings </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 10. Lists </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 11. Tuples </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 12. Sets </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 13. Dictionaries </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 14. Mutable vs immutable </summary>

### Immutable
> An immutable object's value cannot be changed after creation.

Example : `int`, `float`, `bool`, `str`, `tuple`

```py
x = 10
print(x)

# We can't modify the existing 10 object.
-----------------------------------------
# When We do :

x = 20
# Python makes x refer to another object.
```

### Mutable
> Mutable objects can be modified after creation.

Example : `list`, `dict`, `set`

```py
numbers = [1, 2, 3]
numbers.append(4)

# The list itself has changed.
# [1, 2, 3] ---> [1, 2, 3, 4]
```

</details>
<!------------------------------------>


<details>
  <summary> 15. Shallow vs deep copy </summary>

<br/>

</details>
<!------------------------------------>


<details>
  <summary> 16. List/set/dict comprehensions </summary>

<br/>

</details>
<!------------------------------------>


## Level 3 - Functions


<details>
  <summary> 17. Functions </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 18. Arguments and parameters </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 19. <code>*args</code> and <code> **kwargs </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 20. Default arguments </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 21. Scope: local/global/nonlocal </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 22. Lambda </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 23. <code> map </code>, <code> filter </code>, <code> reduce </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 24. Recursion </summary>

<br/>

</details>
<!------------------------------------>



## Level 4 - OOP


<details>
  <summary> 25. Class and object </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 26. Constructor </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 27. Instance/class/static methods </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 28. Encapsulation </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 29. Inheritance </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 30. Polymorphism </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 31. Abstraction </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 32. Method overriding </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 33. <code> @property </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 34. Magic/dunder methods </summary>

<br/>

</details>
<!------------------------------------>



## Level 5 - Intermediate/Advanced Python


<details>
  <summary> 35. Exception handling </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 36. Iterators </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 37. Generators </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 38. Decorators </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 39. Context managers </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 40. <code> yield </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 41. Closures </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 42. <code> is </code> vs <code> == </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 43. <code> @staticmethod </code> vs <code> @classmethod </code> </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 44. Memory management </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 45. Garbage collection </summary>

<br/>

</details>
<!------------------------------------>


## Level 6 - Real Interview


<details>
  <summary> 46. Time & space complexity </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 47. Common coding patterns </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 48. Arrays/strings </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 49. Hash maps </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 50. Stack/queue </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 51. Two pointers </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 52. Sliding window </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 53. Recursion/backtracking </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 54. Sorting/searching </summary>

<br/>

</details>
<!------------------------------------>



<details>
  <summary> 55. Frequently asked Python coding problems </summary>

<br/>

</details>
<!------------------------------------>



## Level 7 - Experienced-Level Interview


<details>
  <summary> 56. Why is Python dynamically typed?  </summary>


</details>
<!------------------------------------>


<details>
  <summary> 57. How does Python manage memory? </summary>


</details>
<!------------------------------------>


<details>
  <summary> 58. What is the GIL? </summary>


</details>
<!------------------------------------>


<details>
  <summary> 59. Why are lists mutable but tuples immutable? </summary>


</details>
<!------------------------------------>


<details>
  <summary> 60. How does dictionary lookup work? </summary>


</details>
<!------------------------------------>


<details>
  <summary> 61. What happens when you write `a = b`? </summary>


</details>
<!------------------------------------>


<details>
  <summary> 62. Difference between iterator and iterable </summary>


</details>
<!------------------------------------>


<details>
  <summary> 63. Generator vs list </summary>


</details>
<!------------------------------------>


<details>
  <summary> 64. Decorator internals </summary>


</details>
<!------------------------------------>


<details>
  <summary> 65. MRO and multiple inheritance </summary>


</details>
<!------------------------------------>


<details>
  <summary> 66. <code> __new__ </code> vs <code> __init__ </code>  </summary>


</details>
<!------------------------------------>


<details>
  <summary> 67. Python garbage collection </summary>


</details>
<!------------------------------------>


<details>
  <summary> 68. Threading vs multiprocessing </summary>


</details>
<!------------------------------------>



<details>
  <summary> 69. Async programming </summary>


</details>
<!------------------------------------>

<details>
  <summary> 70. Writing clean, production-quality Python </summary>

</details>


## The end !

| Complete Python in 70 Question for Interview |
|----------------------------------------------|
