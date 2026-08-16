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

If you want to specify a type on to a variable. This can be done with casting. 

Python is an object-orientated language, and as such it uses classes to define data types, including its primitive types.

Casting in python is therefore done using constructor functions.

```py
x = int(1)        # x will be 1
y = int(2.8)      # y will be 2
z = int("3")      # z will be 3
-----------------------------------
x = float(1)      # x will be 1.0
y = float(2.8)    # y will be 2.8
z = float("3")    # z will be 3.0
w = float("4.2")  # w will be 4.2
-----------------------------------
x = str("s1")     # x will be 's1'
y = str(2)        # y will be '2'
z = str(3.0)      # z will be '3.0'
```

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
  <summary> 9. <b> Strings </b> </summary>

<br/>

<details>
  <summary> - printing string </summary>

```py
print("Hello")                    # Hello
print('Hello')                    # Hello
print("It's amazing")             # It's amazing
print("'Abc'")                    # 'Abc'
print('"xyz"')                    # "xyz"
--------------------------------------------------
a = "Hello"
print(a)             # Hello
--------------------------------------------------
# Multi-Line Strings

b = """India is my country,
We all are Indian,
All Indians are my brothers and sisters."""
print(b)    # Line breaks included as mentioned in the text.

c = 'India is my country,
We all are Indian,
All Indians are my brothers and sisters.'
print(c)  #  line breaks are inserted at the same position.
```
</details>

<details>
  <summary> - strings are arrays </summary>

> Python does not have a character data type, a single character is simply a `string` with a length of 1.

```py
a = "Hello"
print(a[0])    # H
```

Since strings are arrays, we can loop through the characters in a string, with a for loop.

```py
for i in "Hello":
  print(i)

# H, e, l, l, o
```

`len()` function returns the length of a string
```py
a = "Hello"
print(len(a)) # 5
```

To check if substring is present or not in a string, we can use the keyword `in` or `not in`
```py
string1 = "India is my country."

print("is" in string1)        # True
print("is" not in string1)    # False

```

</details>


<details>
  <summary> - slicing string </summary>

```py
b = "Hello World"
print(b[2:5])      # llo
print(b[:5])       # Hello
print(b[2:])       # llo World
print(b[-5:-2])    # Wor

#  [`H` `e` `l` `l` `o` ` ` `W` `o` `r` `l` `d`] 
#  [ 0   1   2   3   4   5   6   7   8   9   10]
#  [                    -6  -5  -4  -3  -2   -1]
```

</details>

<details>
  <summary> - modify strings </summary>

```py

# Upper Case : eturns the string in upper case

a = "Hello World!"
print(a.upper())            # HELLO WORLD!

---------------------------------------------------------

# Lower Case : returns the string in lower case

a = "Hello World!"
print(a.lower())            # hello world!

----------------------------------------------------------

# Remove Whitespace : removes any whitespace from the beginning or the end:

a = " Hello World! "
print(a.upper())            # Hello World

----------------------------------------------------------

# Replace String :  replaces a string with another string:

a = "Hello World!"
print(a.replace("H", "Y"))  # Yello World!

------------------------------------------------------------

# Split String : returns a list where the text between the specified separator becomes the list items

a = "Hello, World!"
print(a.split(","))         # ['Hello', ' World!']

------------------------------------------------------------

```

</details>

<details>
  <summary> - string concatenation </summary>

To concatenate, or combine, two strings we use the `+` operator.

```py
a = "Hello"
b = "World"
c = a + b
print(c)            # HelloWorld

d = a + " " + b
print(d)            # Hello World
```

</details>

<details>
  <summary> - string : format and f-strings </summary>

we can't combine strings and numbers without formatting it or typecasting it. otherwise it will throw TypeError.

```py
age = 21
str = "My name is Ram, I am " + age
print(str)          # TypeError
```
To resolve this we can either use `format()` or something called **f-strings**

Using `format()`
```py
age = 21
str = "My name is Ram, I am " + format(age)
print(str)          # My name is Ram, I am 21
```

Using f-string : declare string with f"The sum of {a}, {b} is {a+b}" and use curly braces.
```py
age = 21
name = "Ram"
str = f"My name is {name}, I am {age}"
print(str)        # My name is Ram, I am 21
```

</details>

<details>
  <summary> - Escape Characters </summary>

An escape character is a backslash `\` followed by the character you want to insert.

| Code	| Result          |
|-------|-----------------|
| `\'`  |	Single Quote	  |
| `\\`  |	Backslash	      |
| `\n`	| New Line	      |
| `\r`	| Carriage Return	|
| `\t`	| Tab	            |
| `\b`	| Backspace	      |
| `\f`  |	Form Feed	      |
| `\ooo`|	Octal value	    |
| `\xhh`|	Hex value       |

```py
str1 = 'Hello\'s World!'
print(str1)        # Hello's World!      
 
str2 = "Hello\\World!"
print(str2)        # Hello\World!

str3 = "Hello\nWorld!"
print(str3)       # Hello
                  # World!

str4 = "Hello\rWorld!"
print(str4)       # World!

str5 = "Hello\tWorld!"
print(str5)       # Hello  World! 

str6 = "Hello \bWorld!"
print(str6)       # HelloWorld!

str7 = "\110\145\154\154\157"
print(str7)       # Hello

str8 = "\x48\x65\x6c\x6c\x6f"
print(str8)       # Hello
```

</details>

<details>
  <summary> - string methods </summary>


Python has a set of built-in methods that you can use on strings.

> All string methods return new values. They do not change the original string.


| Method         | Description                                                      |
|----------------|------------------------------------------------------------------|
| `capitalize()` | Converts the first character to upper case                       |
| `casefold()`   | Converts string into lower case                                  | 
| `center()`	   | Returns a centered string                                        |
| `count()`      | Returns the number of times a specified value occurs in a string |
| `encode()`     | Returns an encoded version of the string                         |
| `endswith()`   | Returns true if the string ends with the specified value         |
| `expandtabs()` | Sets the tab size of the string                                  |
| `find()`       | Searches the string for a specified value and returns the position of where it was found |
| `format()`     | Formats specified values in a string                             |
| `format_map()` | Formats specified values in a string                             |
| `index()`      | Searches the string for a specified value and returns the position of where it was found |
| `isalnum()`    | Returns True if all characters in the string are alphanumeric    |
| `isalpha()`    | Returns True if all characters in the string are in the alphabet |
| `isascii()`	   | Returns True if all characters in the string are ascii characters|
| `isdecimal()`	 | Returns True if all characters in the string are decimals        |
| `isdigit()`    | Returns True if all characters in the string are digits          |
| `isidentifier()`| Returns True if the string is an identifier                     |
| `islower()`     | Returns True if all characters in the string are lower case     |
| `isnumeric()`   | Returns True if all characters in the string are numeric        |
| `isprintable()`	| Returns True if all characters in the string are printable      |
| `isspace()`     |	Returns True if all characters in the string are whitespaces    |
| `istitle()`     |	Returns True if the string follows the rules of a title         |
| `isupper()`     |	Returns True if all characters in the string are upper case     |
| `join()`        |	Joins the elements of an iterable to the end of the string      |
| `ljust()`       |	Returns a left justified version of the string                  |
| `lower()`       |	Converts a string into lower case                               |
|  `lstrip()`     |	Returns a left trim version of the string                       |
| `maketrans()`   |	Returns a translation table to be used in translations          |
| `partition()`   |	Returns a tuple where the string is parted into three parts     |
| `replace()`     |	Returns a string where a specified value is replaced with a specified value  |
| `rfind()`       |	Searches the string for a specified value and returns the last position of where it was found |
| `rindex()`      |	Searches the string for a specified value and returns the last position of where it was found |
| `rjust()`       |	Returns a right justified version of the string                 |
| `rpartition()`  |	Returns a tuple where the string is parted into three parts     |
| `rsplit()`      |	Splits the string at the specified separator, and returns a list|
| `rstrip()`      |	Returns a right trim version of the string                      |
| `split()`       |	Splits the string at the specified separator, and returns a list|
| `splitlines()`  |	Splits the string at line breaks and returns a list             |
| `startswith()`  |	Returns true if the string starts with the specified value      |
| `strip()`       |	Returns a trimmed version of the string                         |
| `swapcase()`    |	Swaps cases, lower case becomes upper case and vice versa       |
| `title()`       |	Converts the first character of each word to upper case         |
| `translate()`   |	Returns a translated string                                     |
| `upper()`       |	Converts a string into upper case                               |
| `zfill()`       |	Fills the string with a specified number of 0 values at the beginning |

 
```py
str1 = "hello world"
print(str1.capitalize()) # Hello world
--------------------------------------------------
str2 = "Hello World Welcome"
print(str2.casefold())   # hello world welcome
--------------------------------------------------
str3 = "Hello"
print(str3.center(20))        #         Hello       
print(str3.center(20, "A"))   # SSSSSSSSHelloSSSSSSS
---------------------------------------------------
str4 = "World Hello World Hello Hello"
print(str4.count("Hello"))          # 3
print(str4.count("Hello", 7, 25))   # 2
---------------------------------------------------
str5 = "Hello, welcome to my world."
print(str5.endswith("."))            # True
print(str5.endswith(".", 10, 20))    # False
---------------------------------------------------
str6 = "Hello welcome Hello welcome."
print(str6.find("welcome"))          # 7
print(str6.find("welcome",14, 28))   # 20
print(str6.find("happy"))            # -1

# Note : The find() method is almost the same as the index() method,
# the only difference is that the index() method raises an exception if the value is not found.

str7 = "Hello world"
print(str7.find("a"))        # -1
print(str7.index("a"))       # ValueError
-------------------------------------------------
str8 = "Hello12"
print(str8.isalnum())       # True

str9 = "Hello a1 a2 "
print(str9.isalnum())       # False

str10 = "Hello 12"
print(str10.isalnum())       # False

```

</details>

</details>
<!------------------------------------>


<details>
  <summary> 10. <b> Lists </b> </summary>

<br/>

> `Lists` are used to store multiple items in a single variable.

Lists are one of 4 built-in data types in Python used to store collections of data, the other 3 are `Tuple`, `Set`, and `Dictionary`, all with different qualities and usage.

```py
mylist = ["apple", "mango", "banana"]
```

<details>
  <summary> - List Intro </summary>

List items are **ordered, changeable, and allow duplicate values**.

List items are **indexed**, the first item has index `[0]`.

List items can be of any data type.
```py
list1 = ["apple", "mango", "banana"]
print(list1)  # apple, mango, banana

list2 = [1, 2, 3, 4, 5]
print(list2)   # 1, 2, 3, 4, 5

list3 = [True, True, False]
print(list3)   # True, True, False

list4 = ["Ram", 21, True, "male"]
print(list4)   # Ram, 21, True, male

print(type(list1))  # <class 'list'>

print(len(list1))   # 3
```
</details>

<details>
  <summary> - Operations on List Items </summary>

```py
list1 = [10, 20, 30, 40, 50]

print(list1[1])     # 20
print(list1[-1])    # 50
print(list1[2:5])   # [30, 40, 50]
print(list1[:4])    # [10, 20, 30, 40]
print(list1[2:])    # [30, 40, 50]
print(list1[-4:-1]) # [20, 30, 40]

list2 = ["apple", "mango", "banana"]

if "mango" in list2:
  print(" mango is in the list")
```

</details>

<details>
  <summary> - modifying List Items </summary>

```py
list1 = [10, 20, 30, 40, 50]
       #  0   1   2   3   4

list1[1] = 21
print(list1)              # [10, 21, 30, 40, 50]

list1[1:3] = [22, 32]
print(list1)              # [10, 22, 32, 40, 50]

list1[1:2] = [23, 24]
print(list1)              # [10, [23,24], 32, 40, 50]

list1[1:3] = [2]
print(list1)              # [10, 2, 32, 40, 50]
```

</details>

<details>
  <summary> - list methods </summary>

`insert()` insert element at any position
```py
list1 = ["apple", "mango", "banana"]
list1.insert(2, "orange")
print(list1)           # ['apple', 'mango', 'orange', 'banana']
```

`append()` : add elements at the end
```py
list2 = ["apple", "mango", "banana"]
list2.append("orange")
print(list2)          # ['apple', 'mango', 'banana', 'orange']
```

`extend()` add list elements or any other tuple, set into list
```py
list1 = [1, 2, 3, 4, 5]
list2 = [6, 7, 8, 9, 10]

list1.extend(list2)    
print(list1)         #  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

----------------------------------------------------------

list1 = ["apple", "mango", "banana"]
tuple1 = ("kiwi", "orange")

list1.extend(tuple1)

print(list1)         # ['apple', 'mango', 'banana', 'kiwi', 'orange']
```

`remove()` remove the specified element and if many only first occurence
```py
list1 = ["apple", "mango", "banana"]
list1.remove("mango")

print(list1)         # ['apple', 'banana']
-------------------------------------------------

list2 = ["apple", "mango", "banana", "mango"]
list2.remove("mango")

print(list2)         # ['apple', 'banana', 'mango']
```

`pop()` method removes the last item and also return it.
```py
list3 = ["apple", "mango", "banana"]
list3.pop()
print(list3)         # ['apple', 'mango']
-----------------------------------------------------
x = list3.pop() 
print(x)             # 'mango'
print(list3)         # ['apple']
```
`del` delete the specified index element and it can also delete the list completely.
```py
list4 = ["apple", "banana", "mango"]
del list4[0]
print(list4)         # ['banana', 'mango']
-------------------------------------------------------
list5 = ["apple", "banana", "mango"]
del list5            # delete list completely, it de
print(list5)         # Error : NameError
```

`clear()` method empties the list.The list still remains, but it has no content.
```py
list6 = ["apple", "banana", "mango"]
list6.clear()
print(list6)         # []
```

</details>


<details>
  <summary> - loop through a List </summary>

`for()` loop
```py
mylist = ["apple", "banana", "mango"]

for i in range(len(mylist)):
  print(mylist[i])
--------------------------------
for e in mylist:
  print(e)

# Output :
#  apple
#  banana
#  mango
```

`while()` loop
```py
mylist = ["apple", "banana", "mango"]

i = 0
while i < len(mylist):
  print(mylist[i])
  i = i + 1
```

 A short hand for loop that will print all items in a list i.e. List Comprehension
```py
mylist = ["apple", "banana", "mango"]
[print(x) for x in mylist]
```

</details>

<details>
  <summary> - list Comprehension </summary>

List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list.

Syntax :
```py
newlist = [expression for item in iterable if condition == True]
```

```py
fruits = ["apple", "banana", "litchi", "kiwi", "mango"]
newlist = []

for x in fruits:
  if "a" in x:
    newlist.append(x)

print(newlist)
---------------------------------------------------------
# Using List Comprehension, we can do this in one line
----------------------------------------------------------
fruits = ["apple", "banana", "litchi", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]

print(newlist)
```

</details>

<details>
  <summary> - sort Lists </summary>

List objects have a `sort()` method that will sort the list alphanumerically, ascending, by default:

```py
mylist = ["orange", "mango", "cherry", "apple", "banana"]
mylist.sort()
print(mylist)     # [apple, banana, cherry, mango, orange]
mylist.sort(reverse = True)
print(mylist)     # [orange, mango, cherry, banana, apple]

# Note : sort() method is case sensitive, resulting in all capital letters being sorted before lower case letters.
----------------------------------------------------------

mylist = [50, 20, 45, 10, 35]
mylist.sort()
print(mylist)   # [10, 20, 35, 45, 50]
mylist.sort(reverse = True)
print(mylist)   # [50, 45, 35, 20, 10]

-----------------------------------------------------------
## Sort the list based on how close the number is to 50.

def myfunc(n):
  return abs(n - 50)

mylist = [50, 20, 45, 10, 35]
mylist.sort(key = myfunc)
print(mylist)     # [50, 45, 35, 20, 10]
```

`reverse()` method reverses the current sorting order of the elements.
```py
mylist = ["orange", "mango", "cherry", "apple", "banana"]
mylist.reverse()
print(mylist)   # [banana, apple, cherry, mango, orange]
```

</details>

<details>
  <summary> - copy a List </summary>

We can't copy a list simply by typing `list2 = list1`. <br/>
bcuz `list2` will only be a reference to `list1`, and <br/>
changes made in `list1 will` automatically also be made in `list2`.

```py
list1 = [1, 2, 3, 4, 5]
list2 = list1

list2[0] = 20

print(list2);  # [20, 2, 3, 4, 5]
print(list1);  # [20, 2, 3, 4, 5]

```
So, We can have to use the built-in List method `copy()` to copy a list.
```py
list1 = [1, 2, 3, 4, 5]
list2 = list1.copy()

list2[0] = 20

print(list2)     # [20, 2, 3, 4, 5]
print(list1)     # [1, 2, 3, 4, 5]
``` 

Another way to make a copy is to use the built-in method `list()`.
```py
list1 = [1, 2, 3, 4, 5]
list2 = list(list1)

list2[1] = 20

print(list2)    # [1, 20, 3, 4, 5]
print(list1)    # [1, 2, 3, 4, 5]
```

We can also make a copy of a list by using the `: `(slice) operator.

```py
list1 = [1, 2, 3, 4, 5]
list2 = list1[:]

list2[0] = 10

print(list2)   # [10, 2, 3, 4, 5]
print(list1)   # [1, 2, 3, 4, 5]
```

</details>

<details>
  <summary> - join two lists </summary>

There are several ways to join, or concatenate, two or more lists in python.

Concatenate `+`
```py
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)             #  ['a', 'b', 'c', 1, 2, 3]
```

Appending list items `append()`
```py
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)             #  ['a', 'b', 'c', 1, 2, 3]
```

`extend()` to add list2 at the end of list1.
```py
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)              #   ['a', 'b', 'c', 1, 2, 3]
```

</details>

<details>
  <summary> - list methods  </summary>

Python has a set of built-in methods that we can use on lists.

| Method	    |                Description                                                   |
|-------------|------------------------------------------------------------------------------|
| `append()`  | Adds an element at the end of the list                                       |
| `clear()` 	| Removes all the elements from the list                                       |
| `copy()`  	| Returns a copy of the list                                                   |
| `count()` 	| Returns the number of elements with the specified value                      |
|  `extend()`	| Add the elements of a list (or any iterable), to the end of the current list |
| `index()`  	| Returns the index of the first element with the specified value              |
| `insert()` 	| Adds an element at the specified position                                    |
| `pop()`   	| Removes the element at the specified position                                |
| `remove()` 	| Removes the item with the specified value                                    |
| `reverse()` | Reverses the order of the list                                               |
| `sort()`    | Sorts the list                                                               |

</details>

</details>
<!------------------------------------>


<details>
  <summary> 11. <b> Tuples </b> </summary>

<br/>

**Tuples** are used to store multiple items in a single variable.

A tuple is a collection which is **_ordered and unchangeable_**.

Tuples are written with round brackets `()`.

```py
tuple1 = ("abc", "pqr", "xyz")
```

<details>
  <summary> - tuple intro </summary>


> Tuples are unchangeable, meaning that we cannot change, add or remove items after the tuple has been created.

```py
mytuple = ("apple", "banana", "mango")
print(mytuple)         # ('apple', 'banana', 'mango')

print(mytuple[0])      # 'apple'

mytuple2 = ("apple", "banana", "apple", "mango")
print(mytuple2)         # ('apple', 'banana', 'apple', 'mango')

print(len(mytuple2))    #  4

mytuple3 = ()
print(type(mytuple3))   # <class 'tuple'>

tuple1 = ("abc", "pqr", "xyz")
tuple2 = (1, 5, 7, 9, 3)
tuple3 = (True, False, False)
tuple4 = ("Ram", 21, True, "male")

# tuple() constructor to create a tuple
tuple5 = tuple(("abc", "pqr", "xyz"))
print(tuple5)          # ('abc', 'pqr', 'xyz')

tuple6 = tuple(("apple"))
print(tuple6)          #  ('a', 'p', 'p', 'l', 'e')
```

To create a tuple with only one item, you have to add a comma after the item, otherwise python will not recognize it as a tuple rather it will be string.
```py
mytuple1 = ("apple",)
print(type(mytuple1))   # <class 'tuple'> 


mytuple2 = ("apple")    # NOT a tuple
print(type(mytuple2))   # <class 'str'>
```

</details>

<details>
  <summary> - access tuple items </summary>

```py
tuple1 = ("apple", "banana", "cherry", "mango", "orange")

print(tuple1[1])        # banana
print(tuple1[-1])       # orange
print(tuple1[2:5])      # ('cherry', 'mango', 'orange')
print(tuple1[:4])       # ('apple', 'banana', 'cherry', 'mango')
print(tuple1[2:])       # ('cherry', 'mango', 'orange')
print(tuple1[-4:-1])    # ('banana', 'cherry', 'mango')

if "apple" in tuple1:
  print("'apple' is present")
```

</details>

<details>
  <summary> - update tuple even though it is immutable </summary>

Since tuples are immutable, they do not have a built-in `append()` method, but there are other ways to add items to a tuple. So workaround  are :

Convert into a list, add item into list and convert this list back to tuple.
```py
tuple1 = ("apple", "banana", "mango")
list1 = list(tuple1)
list1.append("orange")

tuple2 = tuple(list1)   # ('apple', 'banana', 'mango')
```

Add tuple to a tuple
```py
tuple1 = ("apple", "banana", "mango")
tuple2 = ("orange",)
tuple1 += tuple2

print(tuple1)        # ('apple', 'banana', 'mango', 'orange')
```

Similar way we can remove items from tuple by converting it into list delete items and convert it back to tuple.

</details>

<details>
  <summary> - packing and unpacking a tuple </summary>


When we create a tuple, we normally assign values to it. This is called **packing a tuple**.
```py
fruits = ("apple", "banana", "mango")
```

But, in Python, we are also allowed to extract the values back into variables. This is called **unpacking a tuple**.
```py
fruits = ("apple", "banana", "mango")

(red, yellow, green) = fruits

print(red)        # apple
print(yellow)     # banana
print(green)      # mango
```
The number of variables must match the number of values in the tuple, if not, you must use an **asterisk `*`** to collect the remaining values as a list.
```py
fruits = ("apple", "banana", "mango", "papaya")

(red, yellow, *green) = fruits

print(red)       # apple
print(yellow)    # banana 
print(green)     # ['mango', 'papaya']
```

</details>

<details>
  <summary> - loop through a tuple </summary>

`for` and `while` loop
```py
tuple1 = ("apple", "banana", "mango")

for i in tuple1:
  print(i)                    # apple, banana, mango

for i in range(len(tuple1)):
  print(tuple1[i])            # apple, banana, mango


i = 0
while i < len(tuple1):
  print(tuple1[i])            # apple, banana, mango
  i = i + 1
```

</details>

<details>
  <summary> - join two tuples </summary>

To join two or more tuples, we use the `+` operator.

```py
tuple1 = ("a", "b" , "c")
tuple2 = (1, 2, 3)

tuple3 = tuple1 + tuple2
print(tuple3)              # ('a', 'b', 'c', 1, 2, 3)

------------------------------------------------------

fruits = ("apple", "banana", "mango")
newtuple = fruits * 2

print(newtuple)           # ('apple', 'banana', 'mango', 'apple', 'banana', 'mango')

number = (1, 2, 3)
newtuple1 = number * 2

print(newtuple1)         # (1, 2, 3, 1, 2, 3)
```

</details>

<details>
  <summary> - tuple methods</summary>

Python has two built-in methods that we can use on tuples.

| Method	   |                   Description                                                           |
|------------|-----------------------------------------------------------------------------------------|
| `count()`  | Returns the number of times a specified value occurs in a tuple                         |
| `index()`	 | Searches the tuple for a specified value and returns the position of where it was found |

```py

tuple1 = (1, 3, 4, 4, 5)

print(tuple1.count(4))    # 2
print(tuple1.index(5))    # 4
print(tuple1.index(4))    # 2
```


</details>

</details>
<!------------------------------------>


<details>
  <summary> 12. <b> Sets </b> </summary>

<br/>

A set is a collection which is unordered, unchangeable*, and unindexed.

Set items are unchangeable, but you can remove items and add new items.

Sets are written with curly brackets`{}`.

Set items are unordered, unchangeable, and do not allow duplicate values.

```py
myset = {"apple", "banana", "mango"}
print(myset)          # {'mango', 'apple', 'banana'}

# Note: set is unordered, meaning: the items will appear in a random order.

set2 = {1, 2, 3, 1, 4}
print(set2)           # {1, 4, 2, 3}

```

> Once a set is created, you cannot change its items, but you can remove items and add new items.

<details>
  <summary> - set intro </summary>

The values **False and 0** and **True and 1** are considered the same value in sets, and are treated as duplicates.
```py
set1 = {0, 1, 2, False, True}

print(set1)          # {0, 1, 2}
print(len(set1))     # 3

set1 = {"abc", "pqr", "xyz"}
set2 = {1, 3, 5, 7, 9}
set3 = {True, False, False}
set4 = ("abc", 21, True, "male"}

set5 = set(("a", "b", "c")) 
print(set5)           # {'a', 'b', 'c'}

print(type(set5))     #  <class 'set'>
```
</details>

<details>
  <summary> - access set items </summary>

```py
set1 = {10, 20, 30, 40, 50}

for i in set1:
  print(i)             # 10 20 30 40 50

print(10 in set1)      # True
print(5 not in set1)   # True
```

</details>

<details>
  <summary> - add and remove set items </summary>

Once a set is created, you cannot change its items, but you can add new items.

```py
set1 = {"apple", "banana", "mango"}

set1.add("orange")
print(set1)          # {'apple', 'banana', 'mango', 'orange'}

---------------------------------------------------------------

set1 = {"apple", "banana", "mango"}
set2 = {1, 2, 3}

set1.update(set2)

print(set1)         # {'apple', 'banana', 'mango', 1, 2, 3}

--------------------------------------------------------------
object in the update() method does not have to be a set, it can be
any iterable object (tuples, lists, dictionaries etc.)

set1 = {1, 2, 3}
list1 = ["a", "b"]

set1.update(list1)

print(set1)       # {1, 2, 3, 'a', 'b'}
```

To remove an item in a set, use the `remove()`, or the `discard()` method.

```py
set1 = {"apple", "banana", "mango"}

set1.remove("banana")
print(set1)

set1.remove("orange")  # Error

set1.discard("banana")
print(set1)

set1.discard("orange")  # No Error

```

- If the item to remove does not exist, `remove()` will raise an error. 

- If the item to remove does not exist, `discard()` will NOT raise an error.

You can also use the `pop()` method to remove an item, but this method will remove a random item, so you cannot be sure what item that gets removed. The return value of the `pop()` method is the removed item.

```py
set1 = {1, 2, 3, 4, 5}

x = set1.pop()
print(x)

print(set1)
```

**`clear()` and `del`**
- The `clear()` method empties the set.
- The `del` keyword will delete the set completely.
```py
set1 = {"apple", "banana", "mango"}
set1.clear()
print(set1)    # set()

del set1
print(set1)    # NameError : set1 even doesn't exists
```

</details>

<details>
  <summary> - loop </summary>

```py
set1 = {"apple", "banana", "mango"}

for i in set1:
  print(i)

```

</details>

<details>
  <summary> - Join Sets </summary>

There are several ways to join two or more sets in python.
- The `union()` and `update()` methods joins all items from both sets.
- The `intersection()` method keeps ONLY the common items between sets.
- The `difference()` method keeps the items from the first set that are not in the other set(s).
- The `symmetric_difference()` method keeps all items EXCEPT the duplicates.

#### UNION 
```py
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}

set3 = set1.union(set2)
print(set3)      # {'a', 'b', 'c', 1, 2, 3}

# You can use the | operator instead of the union() method, and you will get the same result.

set1 = {"a", "b", "c"}
set2 = {1, 2, 3}

set3 = set1 | set2
print(set3)         # {'a', 'b', 'c', 1, 2, 3}

-------------------------------------------------------------

set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = {"abc", "xyz"}

myset1 = set1.union(set2, set3)
myset2 = set1 | set2 | set3

print(myset1)     # {'a', 'b', 'c', 1, 2, 3, 'abc', 'xyz'}
print(myset2)     # {'a', 'b', 'c', 1, 2, 3, 'abc', 'xyz'}

-------------------------------------------------------------

#  update() method inserts the items in set2 into set1:

set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}

set1.update(set2)
print(set1)         # {'a', 'b', 'c', 1, 2, 3}

``` 

#### INTERSECTION 

```py
set1 = {1, 2, 3}
set2 = {3, 4, 5}

set3 = set1.intersection(set2)
print(set3)           #   {3}

----------------------------------------------

# NOTE : We can use the & operator instead of the intersection()

set3 = set1 & set2
print(set3)          #  {3}

-----------------------------------------------
set1 = {"a", "b", "c"}
set2 = {"d", "e", "a"}

set1.intersection_update(set2)
print(set1)         #   {a}
                    # but it will change the original set instead of returning a new set.
```

#### DIFFERENCE

```py
set1 = {1, 2, 3}
set2 = {3, 4, 5}

set3 = set1.difference(set2)
print(set3)      #  {1, 2}

set4 = set2.difference(set1)
print(set4)      #  {4, 5}

#----------------------------------------

# Note : - operator instead of the difference()
set3 = set1 - set2
print(set3)       #  {1, 2}

set4 = set2 - set1
print(set4)       #  {4, 5}

#-----------------------------------------
set1 = {"a", "b", "c"}
set2 = {"d", "e", "a"}

set1.difference_update(set2)

print(set1)     # {'b', 'c'}
                # but it will change the original set instead of returning a new set
```

#### Symmetric Differences

```py
set1 = {1, 2, 3}
set2 = {4, 5, 1}

set3 = set1.symmetric_difference(set2)

print(set3)    # {2, 3, 4, 5}
#---------------------------------------

# We can use the ^ operator instead of the symmetric_difference()

set3 = set1 ^ set2
print(set3)    # {2, 3, 4, 5}

#---------------------------------------

set1 = {1, 2, 3}
set2 = {4, 5, 1}

set1.symmetric_difference_update(set2)

print(set1)    # {2, 3, 4, 5}
```

</details>

<details>
  <summary> - frozenset </summary>

`frozenset` is an immutable version of a set.

Like sets, it contains unique, unordered, unchangeable elements. <br/>
Unlike sets, elements cannot be added or removed from a frozenset.

```py
x = frozenset({"a", "b", "c"})

print(x)             #  frozenset({'banana', 'apple', 'cherry'})
print(type(x))       #  <class 'frozenset'>
```

Being immutable means you cannot add or remove elements. However, frozensets support all non-mutating operations of sets.


</details>

<details>
  <summary> - set methods </summary>

Python has a set of built-in methods that you can use on sets.

| Method	                  | Shortcut	       |    Description                             |
|-----------------|------------------|------------------------------------------------------|
| `add()`	 	      | Adds an element to the set                 |
| `clear()`	      | Removes all the elements from the set      |
| `copy()`	 	    | Returns a copy of the set                  |
| `difference()`	| `-`	 |Returns a set containing the difference between two or more sets |
| `difference_update()` |	`-=` | Removes the items in this set that are also included in another, specified set |
| `discard()`	    | Remove the specified item                  |
| `intersection()`|	`&`	| Returns a set, that is the intersection of two other sets  |
| `intersection_update()` |	`&=` | Removes the items in this set that are not present in other, specified set(s)  |
| `isdisjoint()`	| Returns True if NO items of this set is present in another set                  |
| `issubset()`	  | `<=`	| Returns True if all items of this set is present in another set         |
|            	    | `<`	  | Returns True if all items of this set is present in another, larger set |
| `issuperset()`	| `>=`	| Returns True if all items of another set is present in this set         |
|  	              | `>`	  | Returns True if all items of another, smaller set is present in this set|
| `pop()`	 	      |       | Removes an element from the set                                         |
| `remove()`	 	  |       | Removes the specified element                                           |
| `symmetric_difference()` |	`^`	| Returns a set with the symmetric differences of two sets        |
| `symmetric_difference_update()` | `^=` | Inserts the symmetric differences from this set and another |
| `union()` 	| l	 | Return a set containing the union of sets             |
| `update()`  | l= |	Update the set with the union of this set and others |

</details>

</details>
<!------------------------------------>


<details>
  <summary> 13. <b> Dictionaries </b> </summary>

<br/>

Dictionaries are used to store data values in `key:value` pairs.

A dictionary is a collection which is ordered*, changeable and do not allow duplicates.

Dictionaries are written with curly brackets `{}`, and have `keys and values`.

```py
person = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi"
}
```

The values in dictionary items can be of any data type.

<details>
  <summary> - dictionary intro </summary>

```py
person = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi"
}

#---------------------------------------------------------------------------

print(person)              #  {'name' : 'Ram', 'age' : 21, 'city' : 'Delhi'}

print(person["name"])      #  Ram

#---------------------------------------------------------------------------

person["age"] = 22      
print(person["age"])       #  22

person["gender"] = "Male"
print(person["gender"])    #  Male

print(person)              #  {'name' : 'Ram', 'age' : 21, 'city' : 'Delhi', 'gender' : 'Male'}

#--------------------------------------------------------------------------

print(len(person))         #  4

#--------------------------------------------------------------------------

dict1 = dict(name = "Shiva", age = 24, country = "India")
print(dict1)               #  {'name':'Shiva', 'age':21, 'country':'India'}

#--------------------------------------------------------------------------

dict2 = {1: "Amit", 2:"Arun", 3:"Anushka", 3:"Anmol"}
print(dict2)               # {1: 'Amit', 2: 'Arun', 3: 'Anmol'}
                           # It doesn't throw error rather it will update the last entered value
```

Example : **Count Frequency**

```py
numbers = [1, 2, 2, 3, 3, 3, 3, 3]

frequency = {}

for i in numbers:
    if i in frequency:
        frequency[i] += 1
    else:
        frequency[i] = 1

print(frequency)
```

</details>


<details>
  <summary> - access dictionary items </summary>

```py
dict1 = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi"
}

print(dict1["name"])       # Ram

#--------------get()------------------

print(dict1.get("name"))   # Ram

#-------------keys()-------------------

# keys() method will return a list of all the keys in the dictionary.

print(dict1.keys())       # dict_keys(['name', 'age', 'city'])

#------------values()-----------------

# values() method will return a list of all the values in the dictionary.

print(dict1.values())       # dict_values(['Ram', 21, 'Delhi'])

#-----------items()----------------------

# items() method will return each item in a dictionary, as tuples in a list

print(dict1.items())       # dict_items([('name', 'Ram'), ('age', 21), ('city', 'Delhi')])

#-------------in----------------------------

# To determine if a specified key is present in a dictionary use the in

if "name" in dict1:
  print("Yes, 'name' is one of the keys in the dictionary")

```

</details>

<details>
  <summary> - change dictionary items </summary>

We can change the value of a specific item by referring to its key name.

```py
dict1 = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi"
}

dict1["name"] = "Shiva"      
print(dict1["name"])             #  Shiva

dict1.update({"age": 20})
print(dict1["age"])              # 20

#  update() method will update the dictionary with the items from a given argument.
#  If the item does not exist, the item will be added.

dict1.update({"gender": "male"})
print(dict1)                    # {'name':Shiva, 'age':20, 'city':'Delhi', 'gender':'male'}
```

</details>

<details>
  <summary> - removing dictionary items </summary>

`pop()` method removes the item with the specified key name:
```py
dict1 = {
    "name": "Shiva",
    "age": 20,
    "city": "Delhi",
    "gender": "Male"
}

#------------------pop()-----------------------
dict1.pop("gender")
print(dict1)           # {'name':Shiva, 'age':20, 'city':'Delhi'}

#------------------popitem()-----------------------

# popitem() method removes the last inserted item 

dict1.popitem()
print(dict1)           # {'name':Shiva, 'age':20}

#------------------del()--------------------------

# del removes the item with the specified key name
# if not specifies it will delete the dictionary as a whole

del dict1["age"]
print(dict1)          # {'name':Shiva}


del dict1
#print(dict1)          # NameError : Dictionary dict1 not even exists

#----------------clear()--------------------------

# clear() method empties the dictionary

dict1 = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi",
    "gender": "Male"
}

dict1.clear()
print(dict1)      # {}
```

</details>

<details>
  <summary> - loops on dictionary </summary>

```py
dict1 = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi",
    "gender": "Male"
}

#------------for loop-----------------------------
for i in dict1:
  print(i)              # Print all keys of dict1

for i in dict1:
  print(dict1[i])       # Print all values of respective keys of dict1

#------------------------------------------------
for i in dict1.keys():
  print(i)              # Print all keys of dict1

for i in dict1.values():
  print(i)              # Print all values of dict1

#--------------------------------------------------

for x, y in dict1.items():
  print(x, y)           # Print both keys and values of dict1
```

</details>

<details>
  <summary> - copy dictionary </summary>

We can't copy a dictionary simply by typing dict2 = dict1, bcuz dict2 will only be a reference to dict1, and changes made in dict1 will automatically also be made in dict2.


```py
dict1 = {
    "name": "Ram",
    "age": 21,
    "city": "Delhi",
    "gender": "Male"
}

dict2 = dict1.copy()
print(dict2)  # {'name': 'Ram', 'age': 21, 'city': 'Delhi', 'gender': 'Male'}

dict3 = dict(dict1)
print(dict3)  # {'name': 'Ram', 'age': 21, 'city': 'Delhi', 'gender': 'Male'}
```

</details>

<details>
  <summary> - nested dictionary  </summary>

A dictionary can contain dictionaries, this is called nested dictionaries.

```py
dict1 = {
  "dict1_1" : {
    "name" : "Ram",
    "age" : 21
  },
  "dict1_2" : {
    "name" : "Shyam", 
    "age" : 22
  },
  "dict1_3" : {
    "name" : "Mohan",
    "age" : 23
  }
}

print(dict1)
# {'dict1_1': {'name': 'Ram', 'age': 21}, 'dict1_2': {'name': 'Shyam', 'age': 22}, 'dict1_3': {'name': 'Mohan', 'age': 23}} 


print(dict1["dict1_1"]["name"]) # abc

for x, obj in dict1.items():
  print(x)

  for y in obj:
    print(y + ':', obj[y])
```

</details>

<details>
  <summary> - dictionary methods </summary>

| Method	      | Description                                                |
|---------------|------------------------------------------------------------|
| `clear()`	    | Removes all the elements from the dictionary               |
| `copy()`	    | Returns a copy of the dictionary                           |
| `fromkeys()`	| Returns a dictionary with the specified keys and value     |
| `get()`	      | Returns the value of the specified key                     |
| `items()`	    | Returns a list containing a tuple for each key value pair  |
| `keys()`	    | Returns a list containing the dictionary's keys            |
| `pop()`	      | Removes the element with the specified key                 |
| `popitem()`	  | Removes the last inserted key-value pair                   |
| `setdefault()`| Returns the value of the specified key. If the key does not exist: insert the key, with the specified value |
| `update()`	  | Updates the dictionary with the specified key-value pairs  |
| `values()`	  | Returns a list of all the values in the dictionary         |

</details>

</details>
<!------------------------------------>

<details>
  <summary> List, Tuple, Set, Dictionary </summary>

| Four collection data types in the Python                                                             |
|------------------------------------------------------------------------------------------------------|
| **`List`** is a collection which is ordered and changeable. <br/> Allows duplicate members.          |
| **`Tuple`** is a collection which is ordered and unchangeable. <br/> Allows duplicate members.       |
| **`Set`** is a collection which is unordered, unchangeable*, and unindexed. <br/> No duplicate members.|
| **`Dictionary`** is a collection which is ordered** and changeable. <br/> No duplicate members.    |

Que : **When would you use List vs Tuple vs Set vs Dictionary?** <br/>
Ans : 
- **_`List`_** : when we need an ordered, mutable collection and duplicates are allowed.
- **_`Tuple`_** : when we need an ordered collection that should not be modified.
- **_`Set`_** : when we need unique values and fast membership testing.
- **_`Dictionary`_** : when we need to associate keys with values or perform fast key-based lookups.

</details>

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

### **Shallow Copy**
> Shallow copying creates a new object but references the same nested objects, leading to shared changes.


### **Deep Copy**
> Deep copying recursively duplicates all objects, ensuring full independence from the original.


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
