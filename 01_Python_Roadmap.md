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

class definitions cannot be empty, but if you for some reason have a class definition with no content, put in the pass statement to avoid getting an error.

```py
class Person:
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

c = '''India is my country,
We all are Indian,
All Indians are my brothers and sisters.'''
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
print(a.strip())            # "Hello World"
print(a.lstrip())           # "Hello World "
print(a.rstrip())           # "  Hello World"
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

str4 = "HelloXYZ\rWorld!"
print(str4)       # World!YZ

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

**Identifiers**

> ***Identifiers are user-defined names used to identify and reference program elements such as variables, functions, classes, modules, and objects.***

**Identifier vs Variable**
> An identifier is a general name used for variables, functions, classes, and other objects in Python, whereas a variable is a specific type of identifier used to store data. Therefore, every variable is an identifier, but not every identifier is a variable.

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
print(list1)              # [10, 2, 40, 50]
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
changes made in `list1` will automatically also be made in `list2`.

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

> **Tuple is immutable, so its elements cannot be changed. However, += with tuples creates a new tuple and reassigns the variable to it. It does not modify the original tuple.**

Let's prove it:
```py
tuple1 = ("apple", "banana", "mango")
print(tuple1)
print(id(tuple1))    # Different Id

tuple2 = ("orange",)
print(tuple2)
print(id(tuple2))

tuple1 += tuple2

print(tuple1)     
print(id(tuple1))   # Different Id Since it is newly created!

```

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

#---------------------------------------------------------------

set1 = {"apple", "banana", "mango"}
set2 = {1, 2, 3}

set1.update(set2)

print(set1)         # {'apple', 'banana', 'mango', 1, 2, 3}

#--------------------------------------------------------------
# object in the update() method does not have to be a set, it can be
# any iterable object (tuples, lists, dictionaries etc.)

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

```py
x = frozenset({"a", "b", "c"})
print(x)     # frozenset({'c', 'b', 'a'})

set1 = {"a", "b", "c"}
set2 = {1, 2, 3}

set3 = x.union(set2)
print(set3)  # frozenset({'a', 'c', 1, 2, 3, 'b'})
```

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


<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/9fe3deac-8b69-4d14-bdcd-72e7de8a4f93" />


**Shallow Copy**
> A Shallow Copy creates a new object but copies the references of nested objects instead of creating new copies of them.
> - As a result, both the original and copied objects share the same referenced data.
> - Any modification to shared objects is reflected in both copies.

**Deep Copy**
> A Deep Copy creates a completely independent copy of an object, including all referenced objects.
> - The copied object has its own memory allocation, so changes made to it do not affect the original object.


</details>
<!------------------------------------>


<details>
  <summary> 16. List/set/dict comprehensions </summary>

<br/>

</details>
<!------------------------------------>


## Level 3 - Functions


<details>
  <summary> 17. <b> Functions </b> </summary>

<br/>

A function is a block of code to avoid code repetition which only runs when it is called.

A function can return data as a result.

### Creating a Function

```py
def greeting():
  print("Hello")
```

The code inside the function must be indented. <br/>
Python uses indentation to define code blocks.

### Calling a Function

To call a function, write its name followed by parentheses`()`.

```py
def greeting():
  print("Hello")

greeting()        #  Hello

# We can call the same function multiple times.
greeting()        #  Hello
greeting()        #  Hello
greeting()        #  Hello
```

It's good practice to use descriptive names that explain what the function does.

Que : **Why functions**? <br/>
Ans : With functions, you write the code once and reuse it.

### Return Values

```py
def sumOfTwo(a, b):
  result = a + b;
  return result;

num1 = 10
num2 = 20

print(sumOfTwo(num1,num2)); # 30

num = sumOfTwo(num1,num2)
print(num)
```

If a function doesn't have a return statement, it returns `None` by default.

```py
def greeting():
  print("Hello")

print(greeting())  # None
```


Function definitions can't be empty. If you need to create a function placeholder without any code, use the `pass` statement.
```py
def greeting:
  pass
```
The pass statement is often used when developing, allowing you to define the structure first and implement details later.

</details>
<!------------------------------------>



<details>
  <summary> 18. <b> Arguments and parameters </b> </summary>

### Parameters vs Arguments

The terms parameter and argument can be used for the same thing: information that are passed into a function.

**From a function's perspective** <br/>
> A **parameter** is the variable listed inside the parentheses in the function definition.

> An **argument** is the actual value that is sent to the function when it is called.

```py
# function with one argument:

def greetings(name):       # name is a parameter
  print("Hello " + name)

greetings("Ram")           # "Ram" is an argument
grettings("Shiva")         # "Shiva" is an argument

```

> **Default Parameter Values**

We can assign default values to parameters. If the function is called without an argument, it uses the default value.

```py
def greetings(name="default"):       
  print("Hello " + name)

greetings();       # Hello default
greetings("Ram");  # Hello Ram
```


### Keyword Arguments
We can send arguments with the key = value syntax.

Using this the order of arguments doesn't matter.

```py
def petStatus(animal, name):
  print("I have a", animal)
  print("My", animal + "'s name is", name)

petStatus(animal = "dog", name = "Leo")
#------------------------------------------
petStatus(name = "Leo", animal = "dog")
# Both print the same
# I have a dog
# My dog's name is Leo
```
The phrase **Keyword Arguments** is often shortened to ***`kwargs`*** in python doc.

When you call a function with arguments without using keywords, they are called **positional arguments**.
<br/> Positional arguments must be in the correct order.
```py
def petStatus(animal, name):
  print("I have a", animal)
  print("My", animal + "'s name is", name)

petStatus("dog", "Leo")
#------------------------------
petStatus("Leo", "dog")
# Both have different output as positional arguments are used!
# I have a dog
# My dog's name is Leo
#------------------------------
# I have a Leo
# My dog's name is dog
```

### Mixing Positional Arguments and Keyword Arguments

We can mix positional arguments and keyword arguments in a function call. <br/>
However, positional arguments must come before keyword arguments.
```py
def person(name, age, gender):
  print("My name is", name, "I'm", age, "and", gender)

person("Ram", age = 21, gender = "Male")
person("Ram", gender = "Male",  age = 21)
person(name = "Ram", gender = "Male",  age = 21)
# person(name = "Ram", "Male",  age = 21) # Not Allowed!
# Same output
# My name is Ram I'm 21 and Male
```

### Passing Different Data Types
We can send any data type as an argument to a function (string, number, list, dictionary, etc.).
```py
def printList(fruits):
  for fruit in fruits:
    print(fruit)

fruits = ["apple", "banana", "mango"]
printList(fruits)

#-----------------------------------------

def printDict(person):
  print("Name:", person["name"])
  print("Age:", person["age"])

person = {"name": "Ram", "age": 21}
printDict(person)

#-----------------------------------------

def printStr(name):
  for ch in name:
    print(ch)

name = "Ram"
printStr(name)
```

### Return Values

Functions can return values using the `return` statement.

```py
def sumOfTwo(x, y):
  return x + y

result = sumOfTwo(5, 3)
print(result)    # 8
```

Functions can return any data type, including lists, tuples, dictionaries, and more.
```py
def my_func():
  return ["apple", "banana", "mango"]

fruits = my_func()
print(fruits)       #	['apple', 'banana', 'mango']
print(fruits[0])    #	apple
print(fruits[1])    # 	banana
print(fruits[2])    # 	mango

#--------------------------------------

def my_func2():
  return (10, 20)

nums = my_func2()
print(nums)       # (10, 20)
#-----------------
x, y = my_func2()
print("x:", x)    # 10
print("y:", y)    # 10

```

### Positional-Only Arguments

We can specify that a function can have ONLY positional arguments. <br/>
To specify positional-only arguments, add `, /` after the arguments.

```py
def greeting(name):
  print("Hello", name)

greeting("Ram")          #  Hello Ram
greeting(name="Ram")     #  Hello Ram

#-------------------------------------

def greeting(name, /):
  print("Hello", name)

greeting("Ram")          #  Hello Ram
greeting(name="Ram")     #  TypeError bcuz only positional argument allowed not keyword
```

### Keyword-Only Arguments

To specify that a function can have only keyword arguments, add `*,` before the arguments.

```py
def greeting(name):
  print("Hello", name)

greeting(name="Ram")     #  Hello Ram
greeting("Ram")          #  Hello Ram

#-------------------------------------

def greeting(*, name):
  print("Hello", name)

greeting(name="Ram")     #  Hello Ram
greeting("Ram")          #  TypeError bcuz only keyword argument allowed, not positional arg
```

### Combining Positional-Only and Keyword-Only

We can combine both argument types in the same function. <br/>
Arguments before `/` are positional-only, and arguments after `*` are keyword-only:

```py
def sumOfNum(a, b, /, *, c, d):
  return a + b + c + d

result = sumOfNum(5, 10, c=15, d=20)
print(result)      # 50

#---------------------------------------

result2 = sumOfNum(a=5, b=10, 15, 20)  # ValueError
# bcuz of 1st two args are keywords args which must be positional
# and alst two args are positional args which must be keywords

```

> **`/` must be ahead of `*` bcuz we can't have keywords arguments then positional arguments.**

```py
def sumOfNum(*, a, b, /, c, d):  # SyntaxError: / must be ahead of *
  return a + b + c + d

result = sumOfNum(a=5, b=10, 15, 20)
print(result)      
```

</details>
<!------------------------------------>



<details>
  <summary> 19. <code>*args</code> and <code> **kwargs </code> </summary>

<br/>

By default, a function must be called with the correct number of arguments. <br/>
However, sometimes you may not know how many arguments that will be passed into your function.

*args and **kwargs allow functions to accept a unknown number of arguments.

### Arbitrary Arguments - *args
If you do not know how many arguments will be passed into your function, add a `*` before the parameter name.

This way, the function will receive a tuple of arguments and can access the items accordingly.

Arbitrary Arguments are often shortened to `*args` in python doc.
```py
# Using *args to accept any number of arguments.

def youngestKid(*kids):
  print("The youngest child is " + kids[2])

youngestKid("Golu", "Molu", "Chhotu")                # Chhotu
youngestKid("Golu", "Molu", "Chhotu", "Kullu")       # Chhotu
```

### What is *args?

The `*args` parameter allows a function to accept any number of positional arguments. <br/>
Inside the function, `args` becomes a tuple containing all the passed arguments

```py
# Accessing individual arguments from *args

def my_function(*args):
  print("Type:", type(args))           # <class 'tuple'>
  print("First argument:", args[0])    # Rohan
  print("Second argument:", args[1])   # Mohan
  print("All arguments:", args)        # ('Rohan', 'Mohan', 'Sohan')

my_function("Rohan", "Mohan", "Sohan")

```

### Using *args with Regular Arguments

We can combine regular parameters with `*args`. <br/>
Regular parameters must come before `*args`.

```py
def greet(greeting, *names):
  for name in names:
    print(greeting, name)

greet("Hello", "Rohan")                     # Hello Rohan
greet("Hello", "Rohan", "Mohan")            # Hello Rohan
                                            # hello Mohan
greet("Hello", "Rohan", "Mohan", "Sohan")   # Hello Rohan
                                            # Hello Mohan
                                            # Hello Sohan

```

`*args` is useful when you want to create flexible functions.
```py
# A function that calculates the sum of any number of values

def sum_n_numbers(*numbers):
  total = 0
  for num in numbers:
    total += num
  return total

print(sum_n_numbers(1))               # 1
print(sum_n_numbers(1, 2))            # 3
print(sum_n_numbers(1, 2, 3))         # 6
print(sum_n_numbers(10, 20, 30, 40))  # 100
```

```py
# Finding the maximum value

def my_function(*numbers):
  print(numbers)
  if len(numbers) == 0:
    return None
  max_num = numbers[0]
  for num in numbers:
    if num > max_num:
      max_num = num
  return max_num

print(my_function(3, 7, 2, 5, 1))
```

### Arbitrary Keyword Arguments - `**kwargs`

If we do not know how many keyword arguments will be passed into your function, add two asterisks `**` before the parameter name.

This way, the function will receive a dictionary of arguments and can access the items accordingly

Arbitrary Keyword Arguments are often shortened to **kwargs in Python doc

```py
# Using **kwargs to accept any number of keyword arguments

def my_function(**kid):
  print("The first name is " + kid["first_name"]) # The first name is Rohit
  print("and last name is " + kid["last_name"])   # and last name is Kumar

my_function(first_name = "Rohit", last_name = "Kumar")
```

### What is **kwargs?

The `**kwargs` parameter allows a function to accept any number of keyword arguments. <br/>
Inside the function, `kwargs` becomes a dictionary containing all the keyword arguments.

```py
# Accessing values from **kwargs

def my_function(**myvar):
  print("Type:", type(myvar))      # <type ='dict'>
  print("Name:", myvar["name"])    # Ram
  print("Age:", myvar["age"])      # 21
  print("All data:", myvar)        # {'name': 'Ram', 'age': 21, 'city': 'Delhi'}

my_function(name = "Ram", age = 21, city = "Delhi")

```

### Using **kwargs with Regular Arguments

We can combine regular parameters with `**kwargs`. <br/>
Regular parameters must come before `**kwargs`.

```py
def my_function(username, **details):
  print("Username:", username)          # ram01
  print("Additional details:")          # Additional details:
  for key, value in details.items():
    print(" ", key + ":", value)        # name : Ram
                                        # age  : 21
                                        # city : Delhi
                                        # hobby: Coding
my_function("ram01", name='Ram', age=21, city="Delhi", hobby="coding")
```

### Combining *args and **kwargs

We can use both *args and **kwargs in the same function.

The order must be:
1. regular parameters
2. *args
3. **kwargs

```py
def my_function(title, *args, **kwargs):
  print("Title:", title)                  # Title: User Info
  print("Positional arguments:", args)    # Positional arguments: (Mohan, Rohan)
  print("Keyword arguments:", kwargs)     # Keyword arguments : {'age': 25, 'city': 'Mumbai'}

my_function("User Info", "Mohan", "Rohan", age = 25, city = "Mumbai")
```


### Unpacking Arguments

The `*` and `**` operators can also be used when calling functions to unpack (expand) a list or dictionary into separate arguments.

**Unpacking Lists with `*`** <br/>
If we have values stored in a list, we can use `*` to unpack them into individual arguments.

```py
# Using * to unpack a list into arguments

def my_function(a, b, c):
  return a + b + c

numbers = [1, 2, 3]
result = my_function(*numbers)
# Same as:
print(my_function(1, 2, 3))    # 6
print(result)                  # 6
```

**Unpacking Dictionaries with `**`** <br/>
If we have keyword arguments stored in a dictionary, you can use `**` to unpack them:

```py
# Using ** to unpack a dictionary into keyword arguments

def my_function(fname, lname):
  print("Hello", fname, lname)       # Hello Ram Kumar

person = {"fname": "Ram", "lname": "Kumar"}
my_function(**person)
# Same as:
my_function(fname="Ram", lname="Kumar")
```

> Use `*` and `**` in function definitions to collect arguments, and use them in function calls to unpack arguments.

</details>
<!------------------------------------>



<details>
  <summary> 20. Default arguments </summary>

> In python, functions can have default arguments, which are parameters with predefined values.

We can assign default values to parameters. If the function is called without an argument, it uses the default value.

```py
def greetings(name="default"):       
  print("Hello " + name)

greetings();       # Hello default
greetings("Ram");  # Hello Ram
```

</details>
<!------------------------------------>



<details>
  <summary> 21. <b> Scope: local, global, nonlocal </b> </summary>

<br/>


> A variable is only available from inside the region it is created. This is called **Scope**.

### Local Scope

A variable created inside a function belongs to the local scope of that function, and can only be used inside that function.

```py
# A variable created inside a function is available inside that function

def myfunc():
  x = 100
  print(x)

myfunc()   # 100
print(x)   # NameError

#----------------------------------------

def myfunc():
  x = 100
  def myinnerfunc():
    y = 200
    print(x)      # 100 
    print(y)      # 200
  myinnerfunc()   
  print(x)        # 100
  print(y)        # NameError

myfunc()
z = 300
print(z)         # 300
print(x)         # NameError
print(y)         # NameError
```

### Global Scope

> A variable created in the main body of the Python code is a global variable and belongs to the global scope.

Global variables are available from within any scope, global and local.

```py
x = 100
def myfunc():
  print(x)   # 100

myfunc()
print(x)    #  100

#----------------------

x = 100
def myfunc():
  x = 200
  print(x)   # 200

myfunc()
print(x)    #  100

#--------------------

def myfunc():
  global x
  x = 200
  print(x)   # 200

myfunc()
print(x)    #  200

#---------------------

x = 100
def myfunc():
  # global x = 300   Syntax Error in python
  global x
  x = 300
  print(x)   # 300

myfunc()
print(x)    #  300
```

### Nonlocal Keyword

> The `nonlocal` keyword is used to work with variables inside nested functions.

The `nonlocal` keyword makes the variable belong to the outer function.

```py
def myfunc1():
  x = 10
  print(x)         # 10
  def myfunc2():
    nonlocal x
    x = 20
  myfunc2()
  return x

print(myfunc1())    # 20
print(x)            # NameError

#-------------------------------

def myfunc1():
  x = 10
  print(x)          # 10
  def myfunc2():
    nonlocal x
    x = 20
    def myfunc3():
      nonlocal x
      x = 30
    myfunc3()
    print(x)        # 30
  myfunc2()
  return x

print(myfunc1())    # 30
#print(x)           # NameError
```

<details>
  <summary> Local, Enclosing, Global, Built-in </summary>


**Local** - Inside the current function <br/>
**Enclosing** - Inside enclosing functions (from inner to outer) <br/>
**Global** - At the top level of the module <br/>
**Built-in** - In Python's built-in namespace <br/>

```py
x = "global"

def outer():
  x = "enclosing"
  def inner():
    x = "local"
    print("Inner:", x)  # Inner: local
  inner()
  print("Outer:", x)    # Outer: enclosing

outer()                 # Inner: local
                        # Outer: enclosing

print("Global:", x)     # Global: global
```

</details>

</details>
<!------------------------------------>

<details>
  <summary>  <b> Python Decorators </b> </summary>

> Decorators let us add extra behavior to a function, without changing the function's code.

A decorator is a function that takes another function as input and returns a new function.


### Basic Decorator

Define the decorator first, then apply it with `@decorator_name` above the function

```py
def sub(a, b):
  return a-b

def divide(a, b):
  return a/b

print(sub(2,4))     # -2 
print(divide(2,4))  # 0.5

#---------------------------------

def sub(a, b):
  if b>a:
    a,b = b,a
  return a-b

def divide(a, b):
  if b>a:
    a,b = b,a
  return a/b

print(sub(2,4))     # 2
print(divide(2,4))  # 2.0

#-------------------------------

# Here by using decorators, we can reduce the common code
# between multiple functions

# decorator takes the function as parameter and return same function
# with modification

def decorator(func):
  def wrap(a,b):
    if a<b:
      a,b = b,a
    return func(a,b)
  return wrap

@decorator
def sub(a, b):
  return a-b

@decorator
def divide(a, b):
  return a/b

print(sub(2,4))     # 2
print(divide(2,4))  # 2.0

#-----------------------------

# How decorators works?
# sub = decorator(sub)
# divide = decorator(divide)

#-----------------------------

def log_dec(func):
  def wrap(a,b):
    print("Values ", a, " ",b)
    result = func(a,b)
    print("Result", result)
    return result
  return wrap

def decorator(func):
  def wrap(a,b):
    if a<b:
      a,b = b,a
    return func(a,b)
  return wrap

@log_dec
def add(a,b):
  return a+b

@log_dec
@decorator
def sub(a, b):
  return a-b


@log_dec
@decorator
def divide(a, b):
  return a/b

result1 = sub(2,4)
print(result1)          # 2

result2 = divide(5,20)
print(result2)          # 4.0

result3 = add(3,4)
print(result3)          # 7
```

Decorators are very useful while you work with frameworks.

### Arguments in the Decorated Function

Functions that require arguments can also be decorated, just make sure you pass the arguments to the wrapper function.

**`*args` and `**kwargs`** <br/>
Sometimes the decorator function has no control over the arguments passed from decorated function, to solve this problem, `add (*args, **kwargs)` to the wrapper function, this way the wrapper function can accept any number, and any type of arguments, and pass them to the decorated function.

```py

def log_dec(func):
  def wrap(*args, **kwargs):
    print("Values ", args)
    result = func(*args)
    print("Result", result)
    return result
  return wrap

def decorator(func):
  def wrap(a,b):
    if a<b:
      a,b = b,a
    return func(a,b)
  return wrap

@log_dec
def add(*args):
  sum = 0;
  for i in args:
    sum += i;
  return sum;

@log_dec
@decorator
def sub(a, b):
  return a-b


@log_dec
@decorator
def divide(a, b):
  return a/b

result1 = sub(2,4)
print(result1)          # 2

result2 = divide(5,20)
print(result2)          # 4.0

result3 = add(3,4,7)
print(result3)          # 14
```


</details>

<!------------------------------------>

<details>
  <summary> Preserving Function Metadata </summary>

Functions in python has metadata that can be accessed using the `__name__` and `__doc__` attributes.

Normally, a function's name can be returned with the `__name__` attribute.
```py
def myfunction():
  return "Have a great day!"

print(myfunction.__name__)   # myfunction
```

But, when a function is decorated, the metadata of the original function is lost.
```py
def decorator(func):
  def wrap():
    return func().upper()
  return wrap

@decorator
def myfunction():
  return "Have a great day!"


print(myfunction.__name__)   # wrap
print(myfunction())          # HAVE A GREAT DAY!
```

To fix this, python has a built-in function called `functools.wraps` that can be used to preserve the original function's name and docstring.

```py
def decorator(func):
  def wrap():
    return func().upper()
  return wrap
  

@decorator
def myfunction():
  return "Hello"


print(myfunction.__name__)       # wrap
print(myfunction())              # HELLO

#------------------------------
import functools

def decorator(func):
  @functools.wraps(func)
  def wrap():
    return func().upper()
  return wrap


@decorator
def myfunction():
  return "Hello"

print(myfunction.__name__)       # myfunction
print(myfunction())              # HELLO
```


</details>


<!------------------------------------>



<details>
  <summary> 22. <b> Lambda </b> </summary>

### Lambda Functions

A lambda function is a small anonymous function.

A lambda function can take any number of arguments, but can only have one expression.

Syntax:
```
lambda arguments : expression
```

```py
# Add 10 to argument a, and return the result

def x(a):
  return a+10

print(x(5))   # 15

#-------------------------

x = lambda a : a + 10

print(x(5))   # 15
```


**Lambda functions can take any number of arguments**
```py
# Multiply argument a with argument b and return the result

def x(a,b):
  return a*b

print(x(5,6))        # 30

#--------------------------------

x = lambda a,b : a*b

print(x(5,6))        # 30


y = lambda a, b, c : a + b + c
print(y(5, 6, 7))    # 18 
```

### Why Use Lambda Functions?

The power of lambda is better shown when you use them as an anonymous function inside another function.

Suppose, we have a function definition that takes one argument, and that argument will be multiplied with an unknown number.

```py
def myfunc(n):
  return lambda a : a * n

# Use that function definition to make a function that doubles the number

mydoubler = myfunc(2)

print(mydoubler(10))    # 20
print(mydoubler(15))    # 30

# using same function definition to make a function that triples the number

mytripler = myfunc(3)

print(mytripler(10))   # 30
print(mytripler(15))   # 45
```

```py
# use the same function definition to make both functions, in the same program

def fun(n):
  return lambda a : a * n;

doubler = fun(2)
tripler = fun(3)
quadler = fun(4)

print(doubler(10))    # 20
print(tripler(10))    # 30
print(quadler(10))    # 40
```

> **Use lambda functions when an anonymous function is required for a short period of time**.


### Lambda with Built-in Functions

Lambda functions are commonly used with built-in functions like `map()`, `filter()`, and `sorted()`.

**Using Lambda with `map()`** <br/>
> The `map()` function applies a function to every item in an iterable.

```py
# Double all numbers in a list

numbers = [1, 2, 3, 4, 5]
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)
```


**Using Lambda with `filter()`** <br/>
> The `filter()` function creates a list of items for which a function returns `True`.

```py
# Filter out odd numbers from a list

numbers = [1, 2, 3, 4, 5]
odd_numbers = list(filter(lambda x: x % 2 != 0, numbers))
print(odd_numbers)     # [1, 3, 5]
```

**Using Lambda with `sorted()`** <br/>
> The `sorted()` function can use a lambda as a key for custom sorting.

```py
# Sort strings by length

words = ["on", "the", "right", "left"]
sorted_words = sorted(words, key=lambda x: len(x))
print(sorted_words)     # ['on', 'the', 'left', 'right']

#---------------------------------------------------------

# Sort a list of tuples by the second element

students = [("Mohan", 25), ("Rohan", 22), ("Sohan", 28)]
sorted_students = sorted(students, key=lambda x: x[1])
print(sorted_students)  # [('Rohan', 22), ('Mohan', 25), ('Sohan', 28)]
```


</details>
<!------------------------------------>



<details>
  <summary> 23. <code> map </code>, <code> filter </code>, <code> reduce </code> </summary>

<br/>

`map()` function applies a function to every item in an iterable.
```py
list1 = ['abc', 'pqr', 'stu', 'xyz']
uppered_list1 = []

for i in list1:
    x = i.upper()
    uppered_list1.append(x)

print(uppered_list1)

#---------------------------------------

list1 = ['abc', 'pqr', 'stu', 'xyz']

uppered_list1 = list(map(str.upper, list1))

print(uppered_list1)
```

`filter()`
```py
scores = [66, 90, 68, 59, 76, 60, 88, 74, 81, 65]

def is_A_student(score):
    return score > 75

over_75 = list(filter(is_A_student, scores))

print(over_75)   # [90, 76, 88, 81]
```

`reduce()`
```py
from functools import reduce

numbers = [3, 4, 6, 9, 34, 12]

def custom_sum(first, second):
    return first + second

result = reduce(custom_sum, numbers)
print(result)
```

| Function	  | Purpose	   |   Input	    | Output                          |                          |
|-------------|------------|--------------|---------------------------------|--------------------------|
| `map()`     |	Transform	 | Many values	| Iterator of transformed values  | "Change every item"      |
| `filter()`	| Select	   | Many values	| Iterator of selected values     | "Keep some items"        |
| `reduce()`	| Combine	   | Many values	| Single accumulated value        | "Turn many items into one" |

</details>
<!------------------------------------>



<details>
  <summary> 24. <b> Recursion </b> </summary>

<br/>

Recursion is a common mathematical and programming concept. <br/>
**Recursion means that a function calls itself**. <br/>
This has the benefit of meaning that you can loop through data to reach a result.

```py
# A simple recursive function that counts down from 5

def countdown(n):
  if n <= 0:
    print("Done!")
  else:
    print(n)
    countdown(n - 1)

countdown(5)     # 5 4 3 2 1 Done!
```

### Base Case and Recursive Case

Every recursive function must have two parts:

1. A **base case*** - A condition that stops the recursion
2. A **recursive case** - The function calling itself with a modified argument

Without a base case, the function would call itself forever, causing a stack overflow error.

The base case is crucial. Always make sure your recursive function has a condition that will eventually be met.

```py
# Identify base case and recursive case

def factorial(n):
  if n == 0 or n == 1:          # Base case
    return 1
  else:                 
    return n * factorial(n - 1) # Recursive case

print(factorial(5))             # 120
```

```py
# Find the 7th number in the Fibonacci sequence

def fibonacci(n):
  if n <= 1:
    return n
  else:
    return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(7))
```

```py
# Calculate the sum of all elements in a list

def sum_list(numbers):
  if len(numbers) == 0:
    return 0
  else:
    return numbers[0] + sum_list(numbers[1:])


# Find the maximum value in a list

def find_max(numbers):
  if len(numbers) == 1:
    return numbers[0]
  else:
    max_of_rest = find_max(numbers[1:])
    return numbers[0] if numbers[0] > max_of_rest else max_of_rest

my_list = [3, 7, 2, 9, 1]
print(find_max(my_list))   # 9
print(sum_list(my_list))   # 22
```

### Recursion Depth Limit

Python has a limit on how deep recursion can go. <br/>
The default limit is usually around 1000 recursive calls.

```py
# Check the recursion limit

import sys
print(sys.getrecursionlimit())

#-----------------------------------------------------------

# If you need deeper recursion, you can increase the limit,
# but be careful as this can cause crashes

import sys
sys.setrecursionlimit(2000)
print(sys.getrecursionlimit())
```

Increasing the recursion limit should be done with caution. For very deep recursion, consider using iteration instead.

</details>
<!------------------------------------>

<details>
  <summary> Python Generator </summary>

> **Generators are functions that can pause and resume their execution**.

When a generator function is called, it returns a generator object, which is an iterator.

Generators allow you to iterate over data without storing the entire dataset in memory.

Instead of using `return`, generators use the `yield` keyword.


```py
def topTen():
  return 5;

def topTenGen():
  yield 5;

value1 = topTen()
print(value1)             # 5

value2 = topTenGen()      # Generator Obj which is an iterator 
print(value2)
print(value2.__next__())  # 5
```

```py
# A simple generator function

def my_generator():
  yield 1
  yield 2
  yield 3

for value in my_generator():
  print(value)
```

```py
def squareUpto1toN(n):
  i=1
  while(i<=n):
    sq = i*i
    yield sq
    i+=1

values = squareUpto1toN(10);
print(values.__next__())        # 1
print(values.__next__())        # 4
print(values.__next__())        # 9
print(values.__next__())        # 16
print(values.__next__())        # 25
for i in values: 
  print(i)                      # 36 49 64 81 100

#---------or--------------------------------------
values2 = squareUpto1toN(5);
for i in values2:
  print(i)                      # 1 4 9 16 25
```

The code inside the function is not executed yet, it is only compiled. The function only executes when you iterate over the generator.


### The `yield` Keyword

The `yield` keyword is what makes a function a generator.

When `yield` is encountered, the function's state is saved, and the value is returned. <br/>
The next time the generator is called, it continues from where it left off.

```py
def count_up_to(n):
  count = 1
  while count <= n:
    yield count
    count += 1

for num in count_up_to(5):
  print(num)

# Unlike return, which terminates the function, yield pauses it and can be called multiple times.
```
> Generators are memory-efficient because they generate values on-the-fly instead of storing everything in memory.

We can manually iterate through a generator using the `next()` function:
```py
def simple_gen():
  yield "Rohan"
  yield "Mohan"
  yield "Sohan"

gen = simple_gen()
print(next(gen))         # Rohan
print(gen.__next__())    # Rohan
print(next(gen))         # Mohan
print(gen.__next__())    # Mohan
print(next(gen))         # Sohan
print(gen.__next__())    # Sohan

#---------------------------------------------------

print(next(gen))    # This will raise StopIteration

# When there are no more values to yield,
# the generator raises a StopIteration exception

```

### List Comprehension and Generator Expressions

Similar to list comprehensions, we can create generators using generator expressions with parentheses instead of square brackets.

```py
# List comprehension vs generator expression

# List comprehension - creates a list
list_comp = [x * x for x in range(5)]  
print(list_comp)                    # [0, 1, 4, 9, 16]
   
# Generator expression - creates a generator
gen_exp = (x * x for x in range(5))
print(gen_exp)                      # generator object 
print(list(gen_exp))                # [0, 1, 4, 9, 16]
```

```py
# Calculate sum of squares without creating a list
# Using a generator expression with sum

total = sum(x * x for x in range(10))
print(total)          # 285
```

### Generator Methods

Generators have special methods for advanced control.

`send()` method allows you to send a value to the generator:
```py
def echo_generator():
  while True:
    received = yield
    print("Received:", received)

gen = echo_generator()
next(gen) # Prime the generator
gen.send("Hello")     # Received: Hello
gen.send("World")     # Recieved: World
```

`close()` method stops the generator
```py
def my_gen():
  try:
    yield 1
    yield 2
    yield 3
  finally:
    print("Generator closed")

gen = my_gen()
print(next(gen))          # 1
print(gen.__next__())     # 2
gen.close()               # Generator closed

```

</details>
<!------------------------------------>

<details>
  <summary> Iterators </summary>

> **An iterator is an object that contains a countable number of values**.

An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.

Technically, in python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`.

Iterator will not give you all the value at a time. It gives us one value at a time.
```py
nums = [1, 3, 5, 7, 9]

print(nums[0])         # 1
print(nums[4])         # 9
print(nums[4])         # IndexOut of Bound error

for x in nums:
  print(x)             # 1 3 5 7 9

#----- Iterator-----------------------
itr = iter(nums)
print(itr)             # <iterator object>
print(itr._next_())    # 1
print(itr._next_())    # 3
# bcuz when we call it knows the last value means it preserve the state of last value.

print(next(itr))       # 7 
```

```py
class Top10:
  def __init__(self):
    self.num = 1
  def __iter__(self):
    return self
  def __next__(self):
    if(self.num <= 10):
      val = self.num
      self.num += 1

      return val
    else:
      raise StopIteration

values = Top10()

print(next(values))  # 1
for i in values:
  print i;           # 2 3 4 5 6 7 8 9 10

#---------------------
print(next(values))



print(next(value))
```

### Iterator vs Iterable

Lists, tuples, dictionaries, and sets are all iterable objects. <br/>
They are iterable containers which you can get an iterator from.

All these objects have a `iter()` method which is used to get an iterator.

```py
# Return an iterator from a tuple, and print each value

mytuple = ("apple", "banana", "mango")
myit = iter(mytuple)

print(next(myit))       # apple
print(next(myit))       # banana
print(next(myit))       # mango


# Even strings are iterable objects, and can return an iterator

mystr = "apple"
myit = iter(mystr)

print(next(myit))       # a
print(next(myit))       # p
print(next(myit))       # p
print(next(myit))       # l
print(next(myit))       # e

# Looping through a iterator

mytuple = ("apple", "banana", "mango")

for i in mytuple:
  print(i)              # apple  banana mango

```

### Create an Iterator

To create an object/class as an iterator we have to implement the methods `__iter__()` and `__next__()` to your object.

In python all classes have a function called `__init__()`, which allows us to do some initializing when the object is being created.

`__iter__()` method acts similar, you can do operations (initializing etc.), but must always return the iterator object itself.

`__next__()` method also allows you to do operations, and must return the next item in the sequence.


```py
# Create an iterator that returns numbers, starting with 1,
# and each sequence will increase by one (returning 1,2,3,4,5 etc.)

class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x

n1 = MyNumbers()
myiter = iter(n1)

print(next(myiter))  # 1
print(next(myiter))  # 2
print(next(myiter))  # 3
print(next(myiter))  # 4
print(next(myiter))  # 5
```

### StopIteration

To prevent the iteration from going on forever, we can use the StopIteration statement

In the `__next__()` method, we can add a terminating condition to raise an error if the iteration is done a specified number of times.

```py
# Stop after 20 iterations

class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    if self.a <= 20:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

for x in myiter:
  print(x)
```

</details>

<!------------------------------------>



## Level 4 - OOP

<details>
  <summary> Intro </summary>

Python is an **object-oriented programming language**, allows us to structure our code using **classes and objects** for better organization and reusability.

**OOP Advanatages**
1. Provides a clear structure to programs
2. Makes code easier to maintain, reuse, and debug
3. Helps keep our code **DRY (Don't Repeat Yourself)**
4. Allows us to build reusable applications with less code

**DRY** principle means you should avoid writing the same code more than once. Move repeated code into functions or classes and reuse it.

</details>
<!--------------------------------->

<details>
  <summary> 25. Class and object </summary>

<br/>

**Classes and objects** are the two core concepts in object-oriented programming.

> **Class : class is a Blueprint(template) for creating an object**.

> **Object : Object is an instance of a class with data members and member functions**.

| Class	   | Objects                      |
|----------|------------------------------|
| Fruit	   | Apple, Banana, Mango, orange |
| Car	     | Maruti, Volvo, Audi, Toyota  |


When we create an object from a class, it inherits all the variables and functions defined inside that class.

Almost everything in python is an object, with its properties and methods.

Each object is independent and has its own copy of the class properties.

```py
# Create a Class : To create a class, use the keyword class

class MyClass:
  x = 5

p1 = MyClass()
print(p1.x)        # 5

p1 = MyClass()
p2 = MyClass()
p3 = MyClass()
print(p1.x)        # 5 
print(p2.x)        # 5
print(p3.x)        # 5

#-----------------------------------------
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

# Create Object
p1 = Person("Ram", 21)
print(p1)                 # <class='Person'>
print(p1.name, p1.age)    #  Ram 21

# Delete Objects
del p1

print(p1)                 # NameError
```

</details>
<!------------------------------------>



<details>
  <summary> 26. Constructor </summary>

<br/>

Constructors are special methods used to initialize objects when they are created from a class. 

Object creation and initialization are handled through the `__new__()` and `__init__()` methods. 

Constructors help assign initial values to object attributes and prepare objects for use.

| When an object is created:                                          |
|---------------------------------------------------------------------|
| `__new__()` method creates and returns a new instance of the class. |
| `__init__()` method initializes the newly created object.           |
| **The object becomes ready for use.**                               |

### why `__init__()`?
```py
# Create a class without __init__()
class Person:
  pass

p1 = Person()
p1.name = "Ram"
p1.age = 21

print(p1.name)   # Ram
print(p1.age)    # 21

# Without the `__init__()` method, we would need to set properties manually for each object.
#-------------------------------------------

# Create a class named Person, use the __init__() method to assign values for name and age

class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("Ram", 21)

print(p1.name)     # Ram
print(p1.age)      # 21

# Using __init__() makes it easier to create objects with initial values
```

> Note : `__init__()` method is called automatically every time the class is being used to create a new object.

### Default Values in `__init__()`

We can also set default values for parameters in the __init__() method:
```py
class Person:
  def __init__(self, name, age=18):
    self.name = name
    self.age = age

p1 = Person("Rohan")
p2 = Person("Mohan", 25)

print(p1.name, p1.age)    # Rohan 18
print(p2.name, p2.age)    # Mohan 25
```

### `self` parameter

- `self` parameter is a reference to the current instance of the class.
- It is used to access properties and methods that belong to the class.

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def greetings(self):
    print("Hello, " + self.name)
    print("I'm " + str(self.age))

p1 = Person("Ram", 21)  
p1.greetings()            # Hello Ram
                          # I'm 21
```

> **Note: The `self` parameter must be the first parameter of any method in the class.**

```py
# self parameter links the method to the specific object

class Person:
  def __init__(self, name):
    self.name = name

  def printName(self):
    print(self.name)

p1 = Person("Rohan")
p2 = Person("Mohan")

p1.printName()     # Rohan
p2.printName()     # Mohan
```

**self Does Not Have to Be Named "self"** <br/>
- We can call it whatever you like, but it has to be the first parameter of any method in the class.
```py
class Person:
  def __init__(myobj, name, age):
    myobj.name = name
    myobj.age = age

  def getName(abc):
    print("Hello, I'm " + abc.name)

  def getAge(self):
    print("I'm ", self.name)

p1 = Person("Ram", 21)
p1.getName()              # Hello, I'm Ram
p1.getAge()               # I'm 21
```

> Note: **While we can use a different name, it is strongly recommended to use self as it is the convention in python and makes our code more readable to others.**

**Accessing Properties with self** <br/>
We can access any property of the class using `self`:
```py
class Car:
  def __init__(self, brand, model, year):
    self.brand = brand
    self.model = model
    self.year = year

  def display_info(self):
    print(f"{self.year} {self.brand} {self.model}")

car1 = Car("Toyota", "Corolla", 2020)
car1.display_info()
```

**Calling Methods with self** <br/>
We can also call other methods within the class using `self`;
```py
class Person:
  def __init__(self, name):
    self.name = name

  def greet(self):
    return "Hello, " + self.name

  def welcome(self):
    message = self.greet()
    print(message + "! Welcome to universe.")

p1 = Person("Veer")
p1.welcome()         # Hello, Veer! Welcome to universe.
```

</details>
<!------------------------------------>

<details>
  <summary> Class Properties vs Object Properties </summary>

Properties defined inside `__init__()` belong to each object (instance properties).

Properties defined outside methods belong to the class itself (class properties) and are shared by all objects;

```py
class Person:
  species = "Human"    # Class property

  def __init__(self, name, age):
    self.name = name   # Instance property
    self.age  = age    # Instance property

p1 = Person("Surya", 18)
p2 = Person("Aditya", 19)

print(p1.name)         # Surya
print(p2.age)          # 19
print(p1.species)      # Human
print(p2.species)      # Human
```

### Modifying Class Properties

When we modify a class property, it affects all objects;

```py
class Person:
  lastname = ""

  def __init__(self, name):
    self.name = name

p1 = Person("Shreya")
p2 = Person("Anjali")

Person.lastname = "Kumari"

print(p1.lastname)        # Kumari
print(p2.lastname)        # Kumari
```

### Add New Properties

We can add new properties to existing objects;

```py
class Person:
  def __init__(self, name):
    self.name = name

p1 = Person("Rocky")

# Adding properties to object

p1.age = 25
p1.city = "Chandigarh"

# Adding properties this way only adds them to that specific object,
# not to all objects of the class.

print(p1.name)      # Rocky
print(p1.age)       # 25
print(p1.city)      # Chandigarh
```

### Class Methods

Methods are functions that belong to a class. <br/>
They define the behavior of objects created from the class.

```py
class Person:
  def __init__(self, name):
    self.name = name

  # Create a method in a class
  def greet(self):
    print("Hello, " + self.name)

  # Note: All methods must have self as the first parameter.

p1 = Person("Arjun")
p1.greet()
```

>  All methods must have self as the first parameter.

**Methods with Parameters**
```py
class Calculator:
  def add(self, a, b):
    return a + b

  def multiply(self, a, b):
    return a * b

calc = Calculator()
print(calc.add(5, 3))        #  8
print(calc.multiply(4, 7))   #  11 
```

**Methods Modifying Properties** <br/>
Methods can modify the properties of an object;
```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def celebrate_birthday(self):
    self.age += 1
    print(f"Happy birthday! You're now {self.age}")

p1 = Person("Leo", 20)
p1.celebrate_birthday()  # Happy birthday! You're now 21
p1.celebrate_birthday()  # Happy birthday! You're now 22
```

**__str__() Method** <br/>
`__str__()` method is a special method that controls what is returned when the object is printed.
```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("Ram", 20)
print(p1)               #  <Person object>

#------------------------------------
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def __str__(self):
    return f"{self.name} {self.age}"    

p1 = Person("Ram", 20)

print(p1)         # Ram 21
```

</details>
<!------------------------------------>


<details>
  <summary> 27. Instance methods, class methods, static methods </summary>

<br/>

### 1. Instance Method

An instance method works with the data belonging to a particular object.

It takes self as its first parameter.

```py
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name, self.age)

student1 = Student("Rahul", 20)
student2 = Student("Amit", 22)

student1.display()          # Rahul 20
student2.display()          # Amit 22
Student.display(student1)   # Rahul 20
```

Basically `student1.display()` is nothing but Python internally passes `student1` as `self`. <br/>
So, conceptually it is `Student.display(student1)`.


### 2. Class Method

A class method works with class-level data rather than a particular object's data.

We use the `@classmethod` decorator.

It takes `cls` as the first parameter.

```py
class Student:
    school = "ABC School"

    @classmethod
    def change_school(cls, new_school):
        cls.school = new_school

print(Student.school)                # ABC School
Student.change_school("XYZ School")
print(Student.school)                # XYZ School
```
`cls` refers to the class itself. So `cls.school` means `student.school`

**Use a class method when you want to work with class-level variables or class-level behavior.**

### Class Method as an Alternative Constructor

Suppose, maybe we receive employee information as a string. <br/>
So in that case, We can create a class method to construct the object. <br/>
This is called an **alternative constructor**.
```py
class Employee:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_string(cls, data):
        name, age = data.split(",")
        return cls(name, int(age))

emp = Employee.from_string("Rahul,25")
print(emp.name)      # Rahul
print(emp.age)       # 25
#--------------------------------------
emp2 = Employee("Tridev", 21)
print(emp2.name)    # Tridev
print(emp2.age)     # 21
```

### 3. Static Method

A static method doesn't receive `self` or `cls` automatically.

We use the `@staticmethod` decorator.

```py
class Calculator:

    @staticmethod
    def add(a, b):
        return a + b
        
    @staticmethod
    def is_even(number):
        return number % 2 == 0

print(Calculator.add(10, 20))    # 30
print(Calculator.is_even(10))    # True
```

We use a static method when the function is logically related to the class but doesn't need instance or class data.

### Summary of instance method, class method and static method

```py
class Employee:

    company = "ABC Ltd"

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):                    # Instance method
        print(self.name, self.salary)

    
    @classmethod
    def change_company(cls, new_company):  # Class method
        cls.company = new_company

    @staticmethod
    def is_valid_salary(salary):           # Static method
        return salary > 0

employee = Employee("Rahul", 50000)
employee.display()                        # instance method, require object   

Employee.change_company("XYZ Ltd")
print(Employee.company)                   # class method, doesn't require obj but class

print(Employee.is_valid_salary(50000))    # static method, doesn't require obj or class
```

| Feature                    | Instance Method           | Class Method             | Static Method     |
| -------------------------- | ------------------------- | ------------------------ | ----------------- |
| Decorator                  | None                      | `@classmethod`           | `@staticmethod`   |
| First parameter            | `self`                    | `cls`                    | None              |
| Access instance variables  | Yes                       | Not directly             | No                |
| Access class variables     | Yes                       | Yes                      | Not automatically |
| Can modify instance state  | Yes                       | Not directly             | No                |
| Can modify class state     | Yes                       | Yes                      | No                |
| Can be called using object | Yes                       | Yes                      | Yes               |
| Can be called using class  | Generally requires object | Yes                      | Yes               |
| Typical use                | Object behavior           | Class behavior / factory | Utility function  |



</details>
<!------------------------------------>



<details>
  <summary> 28. <b> Encapsulation </b> </summary>

<br/>

> Encapsulation is about protecting data inside a class.

It means keeping data (properties) and methods together in a class, while controlling how the data can be accessed from outside the class.

This prevents accidental changes to your data and hides the internal details of how your class works.


### Why Use Encapsulation?

Encapsulation provides several benefits:
- **Data Protection**: Prevents accidental modification of data
- **Validation**: We can validate data before setting it
- **Flexibility**: Internal implementation can change without affecting external code
- **Control**: We have full control over how data is accessed and modified

It is achieved through getter and setter methods.

```py
# Use of encapsulation to protect and validate data

class Student:
  def __init__(self, name):
    self.name = name
    self.__grade = 0

  def set_grade(self, grade):
    if 0 <= grade <= 100:
      self.__grade = grade
    else:
      print("Grade must be between 0 and 100")

  def get_grade(self):
    return self.__grade

  def get_status(self):
    if self.__grade >= 60:
      return "Passed"
    else:
      return "Failed"

student = Student("Vivek")
student.set_grade(85)
print(student.get_grade())
print(student.get_status())
```

### Private Properties

In python, we can make properties private by using a double underscore `__` prefix;

```py
# Create a private class property named __age

class Person:
  def __init__(self, name, age):
    self.name = name
    self.__age = age      # Private property

p1 = Person("Ram", 25)
print(p1.name)            # Ram
print(p1.__age)           # AttributeError
```

> Note: **Private properties cannot be accessed directly from outside the class.**

### Get Private Property Value

To access a private property, we can create a getter method;

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.__age = age        # Private property
    
  # Getter Method
  def get_age(self):
    return self.__age

p1 = Person("Ram", 25)
print(p1.name)              # Ram
# print(p1.__age)           # AttributeError
print(p1.get_age())         # 25
```

### Set Private Property Value

To modify a private property, you can create a setter method.

The setter method can also validate the value before setting it:

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.__age = age        # Private property
    
  # Getter Method
  def get_age(self):
    return self.__age

  # Setter Method
  def set_age(self, age):
    if age > 0:
      self.__age = age
    else:
      print("Age must be +ve")

p1 = Person("Ram", 25)
print(p1.name)              # Ram
# print(p1.__age)           # AttributeError
print(p1.get_age())         # 25


p1.__age = 20               # This create a new attribute
print(p1.__age)             # 20 as it is a new attribute
print(p1.get_age())         # 25
"""
p1
│
├── name          → "Ram"
├── _Person__age  → 25    ← original private variable
└── __age         → 20    ← NEW attribute
"""

p1.set_age(26)
print(p1.get_age())         # 26
```


### Protected Properties

Python also has a convention for protected properties using a single underscore `_` prefix;

```py
# Creating protected property

class Person:
  def __init__(self, name, salary):
    self.name = name
    self._salary = salary # Protected property

p1 = Person("Saurabh", 50000)
print(p1.name)            # Saurabh
print(p1._salary)         # 500000 | Can access, but shouldn't
```

> Note: A single underscore `_`is just a convention. It tells other programmers that the property is intended for internal use, but Python doesn't enforce this restriction.

### Private Methods

We can also make methods private using the double underscore `__` prefix;

```py
# Creating private method

class Calculator:
  def __init__(self):
    self.result = 0

  # Private method
  def __validate(self, num):
    if not isinstance(num, (int, float)):
      return False
    return True

  def add(self, num):
    if self.__validate(num):
      self.result += num
    else:
      print("Invalid number")

calc = Calculator()
calc.add(10)       
calc.add(5)         
print(calc.result)            #  15
# calc.__validate(5)          # This would cause an error

# The __validate method can only be used by other methods inside the class.
```

> Note: Just like private properties with double underscores, private methods cannot be called directly from outside the class. 


### Name Mangling

> **Name mangling** is how Python implements private properties and methods.

When We use double underscores `__`, Python automatically renames it internally by adding `_ClassName` in front. <br/>
e.g.  `__age` becomes `_Person__age`.

```py
class Person:
  def __init__(self, name, age):
    self.name = name
    self.__age = age

p1 = Person("Ram", 20)

# This is how Python mangles the name:
print(p1._Person__age)    # 20 Not recommended!
print(p1.getAge())        # AttributeError, So create getAge method inside class
```

> While you can access private properties using the mangled name, it's not recommended. It defeats the purpose of encapsulation.

</details>
<!------------------------------------>



<details>
  <summary> 29. <b> Inheritance </b> </summary>

Click here [Inheritance](https://github.com/pawansinghfromindia/OOP)


**Inheritance** allows us to define a class that inherits all the methods and properties from another class.
- **Parent class** is the class being inherited from, also called base class.
- **Child class** is the class that inherits from another class, also called derived class.

```py
# Parent Class
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

#Use the Person class to create an object, and then execute the printname method:

x = Person("Vaibhav", "Singh")
x.printname()       #  Vaibhav Singh

#-------------------------------------------------------

# Child Class
class Student(Person):
  pass

x = Student("Gaurav", "Kumar")
x.printname()      #  Gaurav Kumar
#------------------------------------------------------

class Student(Person):
  def __init__(self, fname, lname):
    #add properties etc.

# When you add the __init__() function, the child class
# will no longer inherit the parent's __init__() function.

#--------------------------------------------------------

# To keep the inheritance of the parent's __init__() function,
# add a call to the parent's __init__() function:

class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname):
    Person.__init__(self, fname, lname)

x = Student("Anant", "Singh")
x.printname()       #  Anant Singh

```

**Note: The child's `__init__()` function overrides the inheritance of the parent's `__init__()` function.**

### Use the `super()` Function

Python also has a `super()` function that will make the child class inherit all the methods and properties from its parent;
```py
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname):
    super().__init__(fname, lname)

x = Student("Bharat", "Ram")
x.printname()
```
By using the `super()` function, you do not have to use the name of the parent element, it will automatically inherit the methods and properties from its parent.

```py
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname, year):
    super().__init__(fname, lname)
    self.graduationyear = year

  def welcome(self):
    print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)

x = Student("Ram", "Kumar", 2026)
x.welcome()  # Welcome Ram Kumar to the class of 2026
```

If we add a method in the child class with the same name as a function in the parent class, the inheritance of the parent method will be overridden.

</details>
<!------------------------------------>



<details>
  <summary> 30. <b> Polymorphism </b> </summary>

<br/>

The word "polymorphism" means "many forms", and in programming it refers to methods/functions/operators with the same name that can be executed on many objects or classes.

### Function Polymorphism
Python function that can be used on different objects is the `len()` function.
```py
x = "Hello World!"
print(len(x))         # 12
#--------------------------
mytuple = ("apple", "banana", "mango")
print(len(mytuple))   # 3
#---------------------------
mylist = []
print(len(mylist))    # 0
#---------------------------
thisdict = {
  "name": "Ram",
  "age": 20,
  "city": "Mumbai"
}
print(len(thisdict))   # 3
#------------------------------
```

### Class Polymorphism

Polymorphism is often used in Class methods, where we can have multiple classes with the same method name.

e.g. 3 classes: Car, Boat, and Plane, and they all have a method called `move()`:

```py
# Different classes with same method

class Car:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print(self.brand, "Drive!")

class Boat:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print(self.brand, "Sail!")

class Plane:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print(self.brand, "Fly!")

car1 = Car("Ford", "Mustang")       # Create a Car object
boat1 = Boat("Ibiza", "Touring 20") # Create a Boat object
plane1 = Plane("Boeing", "747")     # Create a Plane object

for x in (car1, boat1, plane1):
  x.move()                          # Drive!  Sail!  Fly!

# Because of polymorphism we can execute the same method for all three classes.
```

### Inheritance Class Polymorphism

Que : What about classes with child classes with the same name? <br/>
Que : Can we use polymorphism there? <br/>
Ans : Yes. e.g. make a parent class called Vehicle, and make Car, Boat, Plane child classes of Vehicle, the child classes inherits the Vehicle methods, but can override them.

```py
class Vehicle:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Move!")

class Car(Vehicle):
  pass

class Boat(Vehicle):
  def move(self):
    print("Sail!")

class Plane(Vehicle):
  def move(self):
    print("Fly!")

car1 = Car("Ford", "Mustang")       # Create a Car object
boat1 = Boat("Ibiza", "Touring 20") # Create a Boat object
plane1 = Plane("Boeing", "747")     # Create a Plane object

for x in (car1, boat1, plane1):
  print(x.brand)
  print(x.model)
  x.move()
```

> Child classes inherits the properties and methods from the parent class.

</details>
<!------------------------------------>



<details>
  <summary> 31. <b> Abstraction </b> </summary>

<br/>

> Abstraction means **hiding the implementation details and showing only the essential features** of an object. This allows users to interact with an object without needing to know how it works internally.

- **Hides unnecessary implementation details**.
- **Exposes only the required functionality**.
- Improves code **security, maintainability, and reusability**.
- Achieved using **Abstract Classes and Abstract Methods** in Python.


**Abstract Class** <br/>

An abstract class is a class that cannot be instantiated directly. It serves as a blueprint for other classes.

Python provides the ABC (Abstract Base Class) module to create abstract classes.

```py
from abc import ABC, abstractmethod

# Abstract class
class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass

# Child class
class Dog(Animal):
    def sound(self):
        return "Bark"

# Child class
class Cat(Animal):
    def sound(self):
        return "Meow"

dog = Dog()
cat = Cat()

print(dog.sound())  # Bark
print(cat.sound())  # Meow
```
If a subclass does not implement all abstract methods, Python raises an error when you try to create an object of that subclass.

```
Think of a car:
- You use the steering wheel, accelerator, and brakes to drive.
- You don't need to know how the engine or transmission works internally.
- The controls are the interface, while the engine's implementation is hidden.
```
This is exactly what abstraction does in programming. <br/>
It provides a simple interface while hiding the underlying complexity.

</details>
<!------------------------------------>


<details>
  <summary> Inner Classes </summary>

### Python Inner Classes

An inner class is a class defined inside another class. <br/>
The inner class can access the properties and methods of the outer class.

Inner classes are useful for grouping classes that are only used in one place, making your code more organized.

```py
class Outer:
  def __init__(self):
    self.name = "Outer Class"

  class Inner:
    def __init__(self):
      self.name = "Inner Class"

    def display(self):
      print("This is the inner class")

otc = Outer()
print(otc.name)       # Outer Class

inc = otc.Inner()
print(inc.name)       # Inner Class
inc.display()         # This is the inner class
```

### Accessing Outer Class from Inner Class

Inner classes in python do not automatically have access to the outer class instance.

If we want the inner class to access the outer class, we need to pass the outer class instance as a parameter;
```py
class Outer:
  def __init__(self):
    self.name = "Ram1"

  class Inner:
    def __init__(self, outer):
      self.outer = outer
      self.name = "Ram2"

    def display(self):
      print(f"Outer class name: {self.outer.name}")
      print(f"Inner class name: {self.name}")

oc = Outer()
ic = oc.Inner(oc)

ic.display()
# Outer class name: Ram1
# Inner class name: Ram2
```

### Why Inner class?

Inner classes are useful for creating helper classes that are only used within the context of the outer class.

```py
class Car:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model
    self.engine = self.Engine()

  class Engine:
    def __init__(self):
      self.status = "Off"

    def start(self):
      self.status = "Running"
      print("Engine started")

    def stop(self):
      self.status = "Off"
      print("Engine stopped")

  def drive(self):
    if self.engine.status == "Running":
      print(f"Driving the {self.brand} {self.model}")
    else:
      print("Start the engine first!")

car = Car("Toyota", "Tata")
car.drive()
car.engine.start()
car.drive()
```

### Multiple Inner Classes
A class can have multiple inner classes;

```py
class Computer:
  def __init__(self):
    self.cpu = self.CPU()
    self.ram = self.RAM()

  class CPU:
    def process(self):
      print("Processing data...")

  class RAM:
    def store(self):
      print("Storing data...")

computer = Computer()
computer.cpu.process()
computer.ram.store()
```

</details>
<!------------------------------------>



<details>
  <summary> 32. Method overriding </summary>

<br/>

1. Dynamic/Runtime Polymorphism
2. Static/Compile time Polymorphism

| Overloading	          | Overriding                   |
|-----------------------|------------------------------|
| Same class usually	  | Parent-child relationship    |
| Same method name	    | Same method signature        |
| Different parameters  | Same parameters              |
| Compile-time	        | Runtime                      |
| Increases flexibility	| Enables runtime polymorphism |

```py
void print(int x)
void print(String x)
```

```py
class Parent {
    void show() {}
}

class Child extends Parent {
    void show() {}
}
```

### 1. Method Overloading

> Method overloading means having the same method name but different parameters.

In languages like Java/C++, you can directly define multiple methods with the same name:

```java
add(int a, int b)
add(int a, int b, int c)
```

**But Python does NOT support traditional method overloading** <br/>
If we define the same method twice, the latest definition replaces the previous one.

Instead, Python commonly achieves similar behavior using **default arguments or `*args`**.

Example 
```py
# using default arguments

class Calculator:

    def add(self, a, b, c=0):
        return a + b + c


calc = Calculator()

print(calc.add(10, 20))       # 30
print(calc.add(10, 20, 30))   # 60
# Here, the same add() method can work with either 2 or 3 arguments.

#------------------------------------------

# using *args

class Calculator:

    def add(self, *numbers):
        return sum(numbers)


calc = Calculator()

print(calc.add(10, 20))
print(calc.add(10, 20, 30))
print(calc.add(10, 20, 30, 40))
```

> **Python doesn't support traditional compile-time method overloading. We can achieve similar behavior using default arguments, `*args`, or conditional logic.**

### 2. Method Overriding

> Method overriding occurs when a child class provides its own implementation of a method that already exists in the parent class.

```py
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

animal = Animal()
dog = Dog()

animal.sound()   # Animal makes a sound
dog.sound()      # Dog barks
```

Sometimes we want the child to use the parent's implementation as well. <br/>
**Using `super()` with overriding**
```py
class Animal:
    def sound(self):
        print("Animal makes a sound")


class Dog(Animal):
    def sound(self):
        super().sound()
        print("Dog barks")


dog = Dog()
dog.sound()  # Animal makes a sound
             # Dog barks
```
> `super()` allows the child class to access the parent's method.


**Overloading = Same class, same name, different inputs**
```py
Calculator
    ↓
add(10, 20)
add(10, 20, 30)
```
**Overriding = Child changes parent's behavior**
```py
Animal
   ↓
sound()

Dog
   ↓
sound()  ← different implementation
```

</details>
<!------------------------------------>



<details>
  <summary> 33. <code> @property </code> </summary>

<br/>

> `@property` in python is a decorator that allows us to access a method like an attribute, without calling it with `()`.

It is mainly used for **encapsulation and controlled access to class attributes**.

```py
# without @property

class Student:
    def __init__(self, name):
        self._name = name  # private property

    def get_name(self):    # getter method
        return self._name


student = Student("Radha")

print(student.get_name())  # Radha

#------------------------------------------------

# With @property

class Student:
    def __init__(self, name, age):
        self._name = name   # private property
        self._age = age     # private property

    @property
    def name(self):
        return self._name
    
    @property
    def age(self):
        return self._age

student = Student("Radha", 10)

print(student.name)   # Radha
print(student.age)    # 10

student.get_name()   # Method call
student.name         # Looks like an attribute
```

`@property` decorator makes `name()` behave like a read-only attribute.


### @property with setter

| Python provides           |
|---------------------------|
| `@property` → getter      |
| `@name.setter` → setter   |
| `@name.deleter` → deleter |

```py
class Employee:
    def __init__(self, salary):
        self._salary = salary   # private property

    @property
    def salary(self):
        return self._salary

    @salary.setter
    def salary(self, value):
        if value < 0:
            raise ValueError("Salary can't be -ve")

        self._salary = value
    
    # Normal setter
    def setter(self, value):
       if value < 0:
           raise ValueError("Salary can't be -ve")
            
       self.salary = value


emp1 = Employee(50000)
print(emp1.salary)       # 50000

emp1.salary = 60000
print(emp1.salary)       # 60000

emp1.setter(70000)
print(emp1.salary)       # 70000
```

Basically `emp1.salary` ilooks like what it is but internally Python is calling the getter/setter methods.

</details>
<!------------------------------------>



<details>
  <summary> 34. Magic/dunder methods </summary>

<br/>
**Dunder means double underscore `__`.**

> **Dunder methods are special methods in python whose names start and end with double underscores**. <br/>
> They allow us to define how objects behave with built-in operations such as object creation, printing, comparison, addition, iteration, and length calculation.

e.g. :
```
__init__
__str__
__len__
__add__
__sub__
__next__
```
They are called **magic methods** or special methods because python automatically calls them in response to certain operations.

### `__init__()` — Constructor

It is called automatically when an object is created.

```py
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1= Student("Rahul", 20)
# When student obj is created Python automatically calls __init()_
```

### `__str__()` - String representation

```py
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("Rahul")
print(s1)            # <__main__.Student object at 0x14a1736f9070>

#-----------------------------------

class Student:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f"Student: {self.name}"

s1 = Student("Rahul")
print(s1)            # Student: Rahul 
```
Without `__str__()`, Python gives a default object representation.

When Python sees `print(student)` it internally uses `student.__str__()`. <br/>
Similarly when it sees `a + b` internally it is `a.__add__(b)`. and so on for others function as well.

### Some important dunder(double underscore `__`) methods

| Dunder method    | Used for                          |
| ---------------- | --------------------------------- |
| `__init__()`     | Object initialization             |
| `__str__()`      | `print()` / readable string       |
| `__repr__()`     | Developer-oriented representation |
| `__len__()`      | `len()`                           |
| `__add__()`      | `+`                               |
| `__sub__()`      | `-`                               |
| `__mul__()`      | `*`                               |
| `__eq__()`       | `==`                              |
| `__lt__()`       | `<`                               |
| `__gt__()`       | `>`                               |
| `__getitem__()`  | `obj[index]`                      |
| `__setitem__()`  | `obj[index] = value`              |
| `__iter__()`     | Iteration                         |
| `__next__()`     | Next item during iteration        |
| `__contains__()` | `in`                              |
| `__call__()`     | Make object callable              |



### `__call__()`

Normally a function can be called using `()`. But we can make an object callable using `__call__()`

```py
def greet():
    print("Hello")

greet()     # Hello
```

```py
class Greeting:
    def __call__(self, name):
        print(f"Hello {name}")

g = Greeting()
g("Rahul")    #  Hello Rahul

# Here, greet("Rahul") actually invokes g._call_("Rahul")
```

### Dunder Takeaway

We can think of dunder methods as a bridge between Python's built-in syntax and our custom classes.

| Our code          |      Python calls   |
|-------------------|---------------------|
| `Employee(...)`   |     `__init__()`    |
| `print(employee)` |     `__str__()`     |   
| `len(employee)`   |    `__len__()`      |
| `a + b`           |     `__add__()`     |
| `a == b`          |     `__eq__()`      |
| `a < b`           |     `__lt__()`      |
| `obj[0]`          |     `__getitem__()` |
| `for x in obj`    |     `__iter__()`    |
| `x in obj`        |    `__contains__()` |
| `obj()`           |     `__call__()`    |

> **Dunder methods don't usually get called directly by us. Python invokes them automatically when we perform specific operations on objects.**

**Dunder methods → Operator Overloading → Polymorphism** <br/>
e.g : `__add__()` lets us define what `+` means for our own class.

</details>
<!------------------------------------>



## Level 5 - Intermediate/Advanced Python


<details>
  <summary> <code> try </code> <code> except </code> <code> else </code> <code> finally </code> </summary>

<br/>

The `try` block lets us try risky code (can cause errors).

The `except` block lets us handle the error.

The `else` block lets us execute code when there is no error means run only if successful.

The `finally` block lets us execute code, regardless of the result of the try and except blocks.

The `raise` block lets us create/throw an exception

```py
try:
  print("Hello")
except:
  print("Something went wrong")
else:
  print("Nothing went wrong")
finally:
  print("The 'try except' is finished")
```

```py
try:
    # code
except ValueError as e:
    print(f"Invalid value: {e}")
```

</details>
<!------------------------------------>

<details>
  <summary> 35. <b> Exception handling </b> </summary>

Exception handling is a mechanism used to handle runtime errors gracefully so that the program doesn't terminate unexpectedly.

```py
a = 10
b = 0
result = a / b          # ZeroDivisionError: division by zero
print(result)
```
Instead of letting the program crash, we can handle the exception.

### `try` and `except`

```py
try:
    a = 10
    b = 0
    result = a / b
except ZeroDivisionError:
    print("Cannot divide by zero")    # Cannot divide by zero
#--------------------------------------------------------
try
 ↓
Exception occurs?
 ↓
YES → except
 ↓
Continue program
```

**Handling Multiple Exceptions**

We can have multiple except blocks; <br/>
Different exceptions can be handled differently.

```py
try:
    number = int(input("Enter number: "))
    result = 10 / number

except ValueError:
    print("Please enter a valid number")

except ZeroDivisionError:
    print("Number cannot be zero")
```

Sometimes we want to capture the actual error message. 
```py
try:
    result = 10 / 0

except Exception as e:
    print("Error:", e)     # Error: division by zero
```

### `else`

`else` block executes only when no exception occurs.
```py
try:
    a = 10
    b = 2
    result = a / b

except ZeroDivisionError:
    print("Cannot divide by zero")

else:
    print("Result:", result)
#-------------------------------------
"""
try
 ↓
Exception?
 ├── YES → except
 │
 └── NO  → else
"""
```

### `finally`

`finally` block always executes, whether an exception occurs or not.
```py
try:
    result = 10 / 2

except ZeroDivisionError:
    print("Error")

finally:
    print("This will always execute")

#----------------------------------------
try:
    result = 10 / 0

except ZeroDivisionError:
    print("Error occurred")

finally:
    print("Cleanup completed")
```

`finally` is commonly used for cleanup operations, such as closing resources.
```py
try:
    file = open("data.txt")
    # process file

finally:
    file.close()
```

### `try-except-else-finally`

```py
try:
    number = int(input("Enter number: "))
    result = 100 / number

except ValueError:
    print("Invalid input")

except ZeroDivisionError:
    print("Cannot divide by zero")

else:
    print("Result:", result)

finally:
    print("Execution completed")

#----------------------------------------
"""
try
 ↓
Exception?
 ├── Yes → except
 │
 └── No  → else
              ↓
           finally
"""
```

### `raise` - Manually Raise an Exception

Python allows us to deliberately generate an exception using `raise`

```py
age = 15
if age < 18:
    raise ValueError("Age must be 18 or above")
```

### `assert`

`assert` is mainly used to check whether a condition is true, especially for debugging and development-time checks.

```py

age = 15
assert age >= 18, "Age must be 18 or above"   # Print this mentioned error

age = 19
assert age >= 18, "Age must be 18 or above"   # Nothing happens
#---------------------------------------------
def calculate_discount(price):
    assert price >= 0, "Price should never be negative"
    return price * 0.9
```

Generally we shouldn't use assert for validating user input or business rules

### Custom Exceptions

We can create your own exception classes.
```py
# Creating an exception class

class InsufficientBalanceError(Exception):
    pass

#---------------------------------------------
def withdraw(balance, amount):
    if amount > balance:
        raise InsufficientBalanceError("Insufficient balance")
    return balance - amount

#--------------------------------------------
try:
    withdraw(1000, 1500)

except InsufficientBalanceError as e:
    print(e)
```

### Common Exception in python

| Exception             | Example                       |
| --------------------- | ----------------------------- |
| `ValueError`          | Invalid value                 |
| `TypeError`           | Wrong data type               |
| `ZeroDivisionError`   | Division by zero              |
| `IndexError`          | Invalid list index            |
| `KeyError`            | Missing dictionary key        |
| `FileNotFoundError`   | File doesn't exist            |
| `AttributeError`      | Object doesn't have attribute |
| `NameError`           | Variable doesn't exist        |
| `ImportError`         | Import failure                |
| `ModuleNotFoundError` | Module not found              |

### Exception Hierarchy

Python exceptions are organized into a hierarchy.

```
BaseException
    │
    ├── SystemExit
    ├── KeyboardInterrupt
    │
    └── Exception
          │
          ├── ValueError
          ├── TypeError
          ├── IndexError
          ├── KeyError
          ├── FileNotFoundError
          └── ZeroDivisionError
```

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

> **A context manager is a mechanism for managing resources and ensuring proper setup and cleanup**. <br/>

It is commonly used with the `with` statement.

A class-based context manager implements `__enter__()` and `__exit__(). __enter__()` runs when entering the context, and `__exit__()` handles cleanup when leaving it, even if an exception occurs.
 
Python also provides `contextlib`, including the `@contextmanager` decorator, to create context managers more easily.

A context manager generally provides two special methods:
1. `_enter_()`
2. `__exit__()`
```py
class MyContext:

    def __enter__(self):
        print("Entering context")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Exiting context")


with MyContext():
    print("Inside context")

#------------------------------------------
"""
Entering context
Inside context
Exiting context

Concetually
with MyContext()
       ↓
   __enter__()
       ↓
  Execute block
       ↓
   __exit__()
"""
```

</details>
<!------------------------------------>


<details>
  <summary> 40. <code> yield </code> </summary>

<br/>

`yield` is used inside a function to create a generator. <br/>
Instead of returning all values at once, it produces one value at a time and pauses the function's execution.

```py
def numbers():
    yield 1
    yield 2
    yield 3

for num in numbers():
    print(num)
```

### `return` vs `yield`  

| `return`                  | `yield`                       |
| ------------------------- | ----------------------------- |
| Ends the function         | Pauses the function           |
| Returns a value once      | Produces values one at a time |
| Usually stores the result | Memory efficient              |
| Normal function           | Generator function            |


> **`yield` turns a normal function into a generator. It returns a value one at a time while preserving the function's state, making it useful for lazy evaluation and memory-efficient processing of large datasets.**

```py
def numbers():
    for i in range(1000000):
        yield i

# It doesn't create a list of 1 million numbers in memory at once
```

</details>
<!------------------------------------>



<details>
  <summary> 41. Closures </summary>

<br/>

> **A closure is a function that remembers and can access variables from its enclosing (outer) function even after the enclosing(outer) function has finished executing.**

It is typically created when an inner function references a variable from the outer function and the inner function is returned. <br/>
Closures are commonly used for maintaining state, implementing decorators, and creating encapsulated behavior.

```py
def outer():
    message = "Hello"
    def inner():
        print(message)

    return inner

func = outer()

func()          # Hello
#---------------------------------
"""
When we execute: func = outer(), outer() finishes execution.
Normally, we might expect message to disappear because outer() has finished.
But inner() remembers message.
So, func() can still access message
That's a closure.
"""
```
The three important ingredients are:
1. There is an outer function.
2. There is an inner function.
3. The inner function uses a variable from the outer function and is returned/exposed outside.
```
Outer Function
      ↓
Inner Function
      ↓
Inner function uses outer variable
      ↓
Return inner function
      ↓
Closure
```

### Closures and `__closure__`
```py
def outer():
    x = 10

    def inner():
        return x

    return inner

func = outer()

print(func())                            # 10
print(func.__closure__)                  # <int obj>
print(func.__closure__[0].cell_contents) # 10
```

### Closure with `nonlocal`

```py
def counter():

    count = 0

    def increment():
        nonlocal count
        count += 1
        return count

    return increment


counter1 = counter()

print(counter1())
print(counter1())
print(counter1())

"""
Why do we need nonlocal count is
Because without it: count += 1
would make Python treat count as a local variable inside increment().
nonlocal tells Python:"I want to modify the variable from the enclosing function.
"""
```

### Multiple Independent Closures
```py
def counter():

    count = 0

    def increment():
        nonlocal count
        count += 1
        return count

    return increment


counter1 = counter()
counter2 = counter()

print(counter1())
print(counter1())

print(counter2())
print(counter2())
#-------------------------------
"""
counter1 and counter2 have separate count values.
They don't interfere with each other.
"""
```

### Closures vs Global Variables
```py
# without closure
count = 0
def increment():
    global count
    count += 1

increment()
print(count)   # 1
# Now count is global.
#-----------------------

# with closure
def counter():
    count = 0
    def increment():
        nonlocal count
        count += 1
        return count

    return increment

func = counter()
print(func())  # 1
# The state is kept inside the closure rather than exposed globally.
```

### Closures and Decorators
```py
def decorator(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")

    return wrapper
#---------------------------------
"""
Here wrapper() remembers: func from the outer function.
That's a closure.
"""
#---------------------------------
@decorator
def greet():
    print("Hello")

greet()       # Before function
              # Hello
              # After function
```

### Closure vs Nested Function

```py
def outer():

    def inner():
        print("Hello")

    inner()
# This is a nested function. But it isn't necessarily a closure.
#----------------------------------------
def outer():
    message = "Hello"

    def inner():
        print(message)

    return inner
# Here inner() is a closure because it remembers message
```

> Every closure involves a nested function, but not every nested function is a closure


### Closure vs Class

We can sometimes use either a closure or a class to maintain state.

```py
# Closure
def counter():
    count = 0
    def increment():
        nonlocal count
        count += 1
        return count

    return increment
#----------------------------
# class
class Counter:
    def __init__(self):
        self.count = 0

    def increment(self):
        self.count += 1
        return self.count

# Both closure and class can maintain state.
```

`nested function` + `enclosing variable` + remember after outer function ends + `nonlocal` + `decorators`.

</details>
<!------------------------------------>



<details>
  <summary> 42. <code> is </code> vs <code> == </code> </summary>

<br/>

This distinction is very important bcuz two different objects can store same value but still not be same object.

### `==` Operator (Equality Operator)

- It is used when we want to check whether two objects contain same data (value), regardless of whether they are stored in same memory location. 
- Internally, it calls `__eq__()` method of class.
- For built-in types like lists, strings and numbers, this means checking if the contents are same.

```py
x = [1, 2, 3]
y = [1, 2, 3]
z = x
if x == y:
    print("x and y have the same values")
else:
    print("x and y do not have the same values")
#---------------------------------------------------
# x and y have the same values
# bcuz == only looks at value not memory address
```

### `is` Operator (Identity Operator)

- The `is` operator is used when you want to check whether two variables refer to exact same object in memory. 
- It does not care about values. Even if two objects look identical, is will return False unless both variables literally point to the same memory location.

```py
x = [1, 2, 3]
y = [1, 2, 3]
z = x

# Case 1: x and y
if x is y:
    print("x and y are the same object")
else:
    print("x and y are not the same object")

# Case 2: x and z
if x is z:
    print("x and z are the same object")
else:
    print("x and z are not the same object")
#-----------------------------------------------
# x and y are not the same object | bcuz both stored in different memory locations, so x is y -> False.
# x and z are the same object | bcuz both point to the same list in memory, so x is z -> True.
 
```

| `is` Operator (Identity)	| `==` Operator (Equality) |
|---------------------------|--------------------------|         
| Checks whether both variables point to the same object in memory | Checks whether two objects have the same values |
| Returns	`True` if same object, otherwise `False` | Return `True` if values are equal, otherwise `False` |
| `x is y -> False` (different objects)	| `x == y -> True` (values match) |

</details>
<!------------------------------------>



<details>
  <summary> 43. <code> @staticmethod </code> vs <code> @classmethod </code> </summary>

<br/>

| Feature	                  |        Class Method	            | Static Method                                |
|---------------------------|---------------------------------|----------------------------------------------|
| Decorator Used	| Defined using the `@classmethod` decorator. |	Defined using the `@staticmethod` decorator. |
| First Parameter	| Receives the class as the first parameter, conventionally named `cls`.	| Does not receive any automatic first parameter like `self` or `cls`. |
| Access to Class Data    |	Can access and modify class-level variables because it has access to `cls`.	| Cannot access or modify class-level variables unless explicitly passed.|
| Access to Instance Data |	Cannot directly access instance variables unless an object is passed manually.| Cannot access instance variables unless they are explicitly passed as arguments.|
| Purpose                 |	Commonly used to create factory methods or alternative constructors that return class objects.	| Typically used to define utility functions that logically belong to the class but do not depend on class or instance data.|
| Object Creation	        | Can create or modify class instances using `cls`.	| Does not create or modify class instances automatically.|

</details>
<!------------------------------------>



<details>
  <summary> 44. <b> Memory Management in Python </b> </summary>

<br/>

Memory management in Python is **the process of allocating, using, and releasing memory for objects automatically**.

Unlike C/C++, Python developers usually don't manually allocate and free memory using things like `malloc()` and `free()`.

Python manages memory automatically using:
- **Private heap**
- **Python Memory Manager**
- **Reference counting**
- **Garbage Collector**
- **Memory allocators**

```py
x = 10
name = "Ram"

"""
Python creates objects in a memory area called the Python private heap.
We don't directly manage this memory.
Python's memory manager handles it.

 Python Code
      ↓
Python Memory Manager
      ↓
Private Heap
      ↓
    Objects
 ┌──────────────┐
 │ Integer  10  │
 ├──────────────┤
 │ String       │
 │ "Ram"        │
 └──────────────┘
"""
```

```py
x = [10, 20, 30]

x ───────→ [10, 20, 30]
             ↑
          Object
# There is one reference to the list.

y = x

x ───────┐
         ↓
      [10, 20, 30]
         ↑
y ───────┘

# Now the object has two references.

del x
# Now One reference remains

del y
# Now the object has no references.
```

**`del` Does NOT Always Delete the Object**
```py
x = [1, 2, 3]
y = x

del x

print(y)  # [1, 2, 3]
```

### Python's Memory Allocator

Python has its own memory management system.

For commonly used Python objects, CPython uses specialized allocation mechanisms.

We don't normally need to know the internal implementation.


### Stack vs Heap

**Stack** is used for things such as function call frames and execution state.

**Heap**, Python objects themselves are generally allocated in the Python-managed heap.
```
   Python Process
               │
       ┌───────┴───────┐
       ↓               ↓
   Call Stack      Managed Heap
       │               │
   function          objects
    frames       [1,2,3], "Hello"
```

### Mutable Objects and Memory

```py
a = [1, 2, 3]
b = a
b.append(4)
print(a)    #  [1, 2, 3, 4]
print(b)    #  [1, 2, 3, 4]

# why?
# bcuz both variables reference the same list object.
"""
a ───────┐
         ↓
      [1,2,3,4]
         ↑
b ───────┘
"""
```
Here comes the concept of **Shallow Copy and Deep Copy**.

**Shallow Copy**
> A Shallow Copy creates a new object but copies the references of nested objects instead of creating new copies of them.
> - As a result, both the original and copied objects share the same referenced data.
> - Any modification to shared objects is reflected in both copies.

**Deep Copy**
> A Deep Copy creates a completely independent copy of an object, including all referenced objects.
> - The copied object has its own memory allocation, so changes made to it do not affect the original object.

### Memory Leak in Python

> **"Python doesn't have memory leaks because it has garbage collection.**

That's true but not completely.

Python can still have memory-related problems. <br/>
For example: <br/>
- Objects are unintentionally kept referenced.
- Large global collections keep growing.
- C/C++ extensions can leak memory.
- Caches aren't bounded.
- Resources aren't released properly.
- Long-lived objects retain references to unnecessary objects.


### Summary

```
             Python Program
                    │
                    ↓
          Python Memory Manager
                    │
                    ↓
             Private Heap
                    │
          ┌─────────┴─────────┐
          ↓                   ↓
   Reference Counting    Garbage Collector
          │                   │
          ↓                   ↓
   Reclaim when          Handle unreachable
   ref count = 0         cyclic objects
```

```
1. Python manages memory automatically.
2. Objects live in a managed heap.
3. Reference counting tracks references.
4. Garbage collector handles cyclic references.
5. del removes a reference, not necessarily the object.
6. Python can still have memory leaks.
7. Generators can reduce memory usage.
8. Context managers manage external resources.
```

</details>
<!------------------------------------>



<details>
  <summary> 45. Garbage collection </summary>

<br/>

> **Garbage collection is a form of automatic memory management used in programming languages like Java, Python, and JavaScript to reclaim memory occupied by objects that are no longer in use**.

This process relieves developers from manual memory allocation and deallocation, significantly reducing the risk of bugs such as memory leaks and dangling references.

**Python mainly uses reference counting, along with a cyclic garbage collector to handle reference cycles.**

```py
import gc

print(gc.isenabled())

#--------------------------------------
# We can manually request a collection:
import gc

collected = gc.collect()
print("Objects collected:", collected)
#---------------------------------------
# However, We generally don't need to manually call gc.collect()
# in normal python programs.
```

### `del` vs Garbage Collection 

| 	       `del`                     |  Garbage Collection             |
|------------------------------------|---------------------------------|
| Removes a name/reference	         | Finds reclaimable objects       | 
| Explicit operation	               | Mostly automatic                |
| Doesn't necessarily destroy object |	Reclaims eligible objects      |
| `del x`	                           | `gc` handles unreachable cycles |



</details>
<!------------------------------------>

## File Handling

<details>
  <summary> <b> File handling </b> </summary>

File handling is an important part of any web application. <br/>
Python has several functions for **creating, reading, updating, and deleting files**.

**File Open**

The key function for working with files in python is the `open()` function.

`open()` function takes two parameters; `filename`, and `mode`.

There are four different methods (modes) for opening a file:
| `"r"` | Read   | Default value. Opens a file for reading, error if the file does not exist |
|-------|--------|---------------------------------------------------------------------------|
| `"a"` | Append | Opens a file for appending, creates the file if it does not exist         |
| `"w"` | Write  | Opens a file for writing, creates the file if it does not exist           |
| `"x"` | Create | Creates the specified file, returns an error if the file exists           |

In addition we can specify if the file should be handled as binary or text mode
| `"t"` | Text   | Default value. Text mode   |
|-------|--------|----------------------------|
| `"b"` | Binary | Binary mode (e.g. images)  |

Syntax :
```py
# To open a file for reading it is enough to specify the name of the file:

f = open("demofile.txt")
#---------or----------------------
f = open("demofile.txt", "rt")

# Both are same bcuz
# "r" for read, and "t" for text are the default values, We don't need to specify them.
```

> Note: **Make sure the file exists, or else we will get an error**.

</details>
<!------------------------------------->

<details>
  <summary> Open and reading file  </summary>

Suppose we have a text file, located in the same folder as python.

demo.txt
```.txt
Hello! Welcome to demo text file
This file is for testing purposes.
Good Luck!
```
To open the file, use the built-in `open()` function.
The `open()` function returns a file object, which has a `read()` method for reading the content of the file:
```py
f = open("demo.txt")
print(f.read())
```

If the file is located in a different location, we will have to specify the file path.
```py
f = open("D:\\myfiles\demo.txt")
print(f.read())
```

### Using the `with` statement

We can also use the with statement when opening a file; <br/>
Then we do not have to worry about closing our files, the `with` statement takes care of that.
```py
with open("demo.txt") as f:
  print(f.read())
```

**Close file** <br/>
It is a good practice to always close the file when we are done with it.

If we are not using the `with` statement, we must write a `close` statement in order to close the file.

```py
f = open("demo.txt")
print(f.readline())
f.close()
```

> We should always close your files. In some cases, due to buffering, changes made to a file may not show until we close the file.

### Read Only Parts of the File

By default the `read()` method returns the whole text, but we can also specify how many characters we want to return.

```py
# Return the 5 first characters of the file

with open("demo.txt") as f:
  print(f.read(5))
```

### Read Lines

We can return one line by using the `readline()` method.

```py
# Reading one line of the file

with open("demo.txt") as f:
  print(f.readline())
#--------------------------------

# By calling readline() two times, we can read the two first lines

with open("demofile.txt") as f:
  print(f.readline())
  print(f.readline())
#--------------------------------

# By looping through the lines of the file, we can read the whole file, line by line

with open("demo.txt") as f:
  for x in f:
    print(x)
```


</details>
<!------------------------------------->

<details>
  <summary> Write/Create files </summary>

### Write to an Existing File

To write to an existing file, we must add a parameter to the `open()` function.

| `"a"` | Append | will append to the end of the file  |
|-------|--------|-------------------------------------|
| `"w"` | Write  | will overwrite any existing content |

```py
# Open the file "demo.txt" and append content to the file:

with open("demo.txt", "a") as f:
  f.write("Now the file has more content!")

# Open and read the file after the appending:
with open("demo.txt") as f:
  print(f.read())
```

### Overwrite Existing Content

To overwrite the existing content to the file, use the `w` parameter.

```py
# Open the file "demo.txt" and overwrite the content:

with open("demo.txt", "w") as f:
  f.write("Woops! I have deleted the content!")

# open and read the file after the overwriting:
with open("demo.txt") as f:
  print(f.read())
```
> Note: **The "w" method will overwrite the entire file**.

### Create a New File

To create a new file in python, use the `open()` method, with one of the following parameters.

| `"x"` | Create | will create a file, returns an error if the file exists  |
|-------|--------|----------------------------------------------------------|
| `"a"` | Append | will create a file if the specified file does not exists |
| `"w"` | Write  | will create a file if the specified file does not exists |

```py
# Create a new file called "myfile.txt":

f = open("myfile.txt", "x")
# a new empty file is created
```
> Note: If the file already exists, an error will be raised.


</details>
<!------------------------------------->

<details>
  <summary> delete files </summary>

### Delete a File

To delete a file, we must import the **OS module**, and run its `os.remove()` function.

```py
# Remove the file "demo.txt":

import os
os.remove("demo.txt")
```

To avoid getting an error, we might want to check if the file exists before we try to delete it.
```py
# Check if file exists, then delete it:

import os
if os.path.exists("demo.txt"):
  os.remove("demo.txt")
else:
  print("The file does not exist")
```

### Delete Folder

To delete an entire folder, use the `os.rmdir()` method.

```py
# Remove the folder "myfolder":

import os
os.rmdir("myfolder")
```
> Note: **We can only remove empty folders**.

</details>
<!------------------------------------->

## DSA

<details>
  <summary> <b> Data Structures and Algorithms </b> </summary>

<br/>

> **Data Structures** is about **_how data can be stored in different structures_**.

> **Algorithms** is about **_how to solve different problems, often by searching through and manipulating data structures_**.

Understanding **DSA** helps us **to find the best combination of Data Structures and Algorithms to create more efficient code**.


### Data Structures

Data Structures are a way of storing and organizing data in a computer.

Python has built-in support for several data structures, such as `lists`, `dictionaries`, and `sets`.

Other data structures can be implemented using Python classes and objects, such as `linked lists`, `stacks`, `queues`, `trees`, and `graphs`.

**Data Structures** :
- [x] Lists and Arrays
- [x] Stacks
- [x] Queues
- [x] Linked Lists
- [x] Hash Tables
- [x] Trees
  - [x] Binary Trees
  - [x] Binary Search Trees
  - [x] AVL Trees
- [x] Graphs


### Algorithms

Algorithms are a way of working with data in a computer and solving problems like sorting, searching, etc.


**Searching and Sorting Algorithms** :
- [x] Linear Search
- [x] Binary Search
- [x] Bubble Sort
- [x] Selection Sort
- [x] Insertion Sort
- [x] Quick Sort
- [x] Counting Sort
- [x] Radix Sort
- [x] Merge Sort


### Why DSA with Python?
- Python has a clean readable syntax
- DSA allows you to improve problem-solving skills
- DSA and Python helps you write more efficient code
- DSA gives you a better understanding of memory storage
- DSA helps you handle complex programming challenges
- Python is widely used in Data Science and Machine Learning


</details>
<!------------------------------------->

### Data Structures

<details>
  <summary> <b> Lists and Arrays </b> </summary>

### Arrays

**Python does not have built-in support for Arrays, but Python Lists can be used instead**.

We use LISTS as ARRAYS, however, to work with arrays in Python you will have to import a library, like the NumPy library.

```py
import numpy as np

arr = np.array([1, 2, 3, 4, 5])

print(arr)          # [1 2 3 4 5]
print(type(arr))    # <class 'numpy.ndarray'>

#################################################
import array as arr

numbers = arr.array('i', [1, 2, 3, 4])

print(type(numbers))    # <class 'array.array'>
print(numbers)          # array('i', [1, 2, 3, 4])

for x in numbers:
	print(x)

#-----------------------------

alphabets = arr.array('u', ['a', 'b', 'c', 'd'])
print(alphabets)        # array('u', 'abcd')
for y in alphabets: 
	print(y)
```


- An array is a special variable, which can hold more than one value at a time.

```py
name1 = "Ram"
name2 = "Bharat"
name3 = "Lakshman"
name4 = "Shatrudhan"

# What if we have not 4 names, but 100?
# The solution is array!
# An array can hold many values under a single name,
# and you can access the values by referring to an index number.
#--------------------------------------------------------------

names = ["Ram", "Bharat", "Lakshman", "Shatrudhan"]

# Access the Elements of an Array
print(names[0])       # 'Ram'
print(names[1])       # 'Bharat'
print(names[2])       # 'Lakshman'
print(names[3])       # 'Shatrudhan'

# Modify the value
names[0] = "Krishna"
print(names[0])       # 'Krishna'

# Length of an Array
length = len(names)
print(length)         # 4

#  > Note: Array's Index starts with 0

# Looping Array Elements

#--------Looping through indexes---------
for i in range(len(names)):
  print(names[i])

#--------Looping through iterator---------
for x in names:
  print(x)
```

Python has a set of built-in methods that we can use on lists/arrays.

| Method	    | Description                                                                 |
|-------------|-----------------------------------------------------------------------------|
| `append()`	| Adds an element at the end of the list                                      |
| `clear()`	  | Removes all the elements from the list                                      |
| `copy()`	  | Returns a copy of the list                                                  |
| `count()`	  | Returns the number of elements with the specified value                     |
| `extend()`	| Add the elements of a list (or any iterable), to the end of the current list|
| `index()`	  | Returns the index of the first element with the specified value             |
| `insert()`	| Adds an element at the specified position                                   |
| `pop()`	    | Removes the element at the specified position                               |
| `remove()`	| Removes the first item with the specified value                             |
| `reverse()`	| Reverses the order of the list                                              |
| `sort()`	  | Sorts the list                                                              |


### Lists

A list is a built-in data structure in Python, used to store multiple elements.

A list is an ordered, mutable collection that can store different data types.

**Creating a list**
```py
# Empty list
x = []
print(x)                   # []

# List of size n=10
l = [0]*10
print(l)                   # [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

# List with initial values
y = [1, 2, 3, 4, 5]
print(y)                  # [1, 2, 3, 4, 5]

# List with mixed types
z = [1, "Hello", 3.14, True]
print(z)                  # [1, 'Hello', 3.14, True]

a = [i*i for i in range(1,6)]
print(a)                  # [1, 4, 9, 16, 25]
```

### List methods and operations

```py
numbers = [10, 20, 30]

numbers.append(40)       # Add at end
print(numbers)           # [10, 20, 30, 40]

numbers.insert(1, 15)    # Add at index
print(numbers)           # [10, 15, 20, 30, 40]

numbers.remove(20)       # Remove value
print(numbers)           # [10, 15, 30, 40]

numbers.pop()            # Remove last element
print(numbers)           # [10, 15, 30]

numbers.pop(1)           # Remove element at index
print(numbers)           # [10, 30]

num = [10, 20, 30]
print(num[0])            # 10
print(num[-1])           # 30
print(num[1:3])          # [20, 30]
```

| Feature           | List         | Array                         |
| ----------------- | ------------ | ----------------------------- |
| Built-in          | Yes          | `array` module                |
| Data types        | Can be mixed | Usually same type             |
| Mutable           | Yes          | Yes                           |
| Dynamic size      | Yes          | Yes                           |
| Memory efficiency | Lower        | Better for typed data         |
| General-purpose   | Excellent    | Useful for typed numeric data |


### Summary

**List** is :
- [x] Ordered
- [x] Mutable
- [x] Dynamic
- [x] Can contain different types
- [x] Index access: O(1)
- [x] Append: O(1) amortized(avg)
- [x] Search: O(n)
- [x] Insert/delete at beginning: O(n)

</details>
<!------------------------------------->
<details>
  <summary> <b> Stacks </b> </summary>

<br/>

> **A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle**.

We can think of it like a stack of breads - we can only add or remove breads from the top.

**A stack is a data structure that can hold many elements, and the last element added is the first one to be removed**.

### Basic operations we can do on a stack are:

**Push** : Adds a new element on the stack. <br/>
**Pop** : Removes and returns the top element from the stack. <br/>
**Peek** : Returns the top (last) element on the stack. <br/>
**isEmpty** : Checks if the stack is empty. <br/>
**Size** : Finds the number of elements in the stack. <br/>

**Stacks can be implemented by using _arrays_ or _linked lists_**.

Stacks can be used **to implement undo mechanisms**, **to revert to previous states**, **to create algorithms for depth-first search in graphs**, or **for backtracking**.

**Stacks are often mentioned together with Queues, which is a similar data structure like stack but different.**

<details>
  <summary> <b> Stack Implementation using Array(List) </b> </summary>

<br/>

**Creating stack using list**
```py
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')

print("Stack : ", stack)    	    # ['A', 'B', 'C']

# Peek
print("Peek : ", stack[-1])     	# C

# Pop
print("Pop : ", stack.pop())	    # C

# Stack after Pop
print("Stack after Pop : ", stack)  # ['A', 'B']

# isEmpty
isEmpty = not bool(stack)      
print("isEmpty : ", isEmpty)        # False
print("isEmpty : ", len(stack)==0)  # False

# Size
print("Size : ",len(stack))         # 2
```
**Creating Stack using class**
```py
class Stack:
  def __init__(self):
    self.stack = []

  def push(self, element):
    self.stack.append(element)

  def pop(self):
    if self.isEmpty():
      return "Stack is empty"
    return self.stack.pop()

  def peek(self):
    if self.isEmpty():
      return "Stack is empty"
    return self.stack[-1]

  def isEmpty(self):
    return len(self.stack) == 0

  def size(self):
    return len(self.stack)

# Create a stack
myStack = Stack()

myStack.push('A')
myStack.push('B')
myStack.push('C')

print("Stack: ", myStack.stack)           # ['A', 'B', 'C']
print("Pop: ", myStack.pop())             # C
print("Stack after Pop: ", myStack.stack) # ['A', 'B']
print("Peek: ", myStack.peek())           # B
print("isEmpty: ", myStack.isEmpty())     # False
print("Size: ", myStack.size())           # 2
```

**Reasons to implement stacks using lists/arrays** :
- **Memory Efficient** : Array elements do not hold the next elements address like linked list nodes do.
- **Easier to implement and understand** : Using arrays to implement stacks require less code than using linked lists, and for this reason it is typically easier to understand as well.

**A reason for not using arrays to implement stacks** :
- **Fixed size**: An array occupies a fixed part of the memory. <br/>
  This means that it could take up more memory than needed, or if the array fills up, it cannot hold more elements.

</details>

<details>
  <summary> <b> Stack Implementation using Linkedlist </b> </summary>

<br/>

A linked list consists of nodes with some sort of data, and a pointer to the next node.

```
| data, next |------->| data, next |------->| data, next |-------> Null
```

**Benefit with using linked lists**
- A big benefit with using linked lists is that nodes are stored wherever there is free space in memory, the nodes do not have to be stored contiguously right after each other like elements are stored in arrays.
- Another nice thing with linked lists is that when adding or removing nodes, the rest of the nodes in the list do not have to be shifted.

**Creating a Stack using a Linked List**
```py
class Node:
  def __init__(self, value):
    self.value = value
    self.next = None
#-----------------------------
class Stack:
  def __init__(self):
    self.head = None
    self.size = 0

  def push(self, value):
    new_node = Node(value)
    if self.head:
      new_node.next = self.head
    self.head = new_node
    self.size += 1

  def pop(self):
    if self.isEmpty():
      return "Stack is empty"
    popped_node = self.head
    self.head = self.head.next
    self.size -= 1
    return popped_node.value

  def peek(self):
    if self.isEmpty():
      return "Stack is empty"
    return self.head.value

  def isEmpty(self):
    return self.size == 0

  def stackSize(self):
    return self.size

  def traverseAndPrint(self):
    currentNode = self.head
    while currentNode:
      print(currentNode.value, end=" -> ")
      currentNode = currentNode.next
    print()

myStack = Stack()
myStack.push('A')
myStack.push('B')
myStack.push('C')

print("LinkedList: ", end="")    		 # LinkedList: 
myStack.traverseAndPrint()       		 # C -> B -> A -> 
print("Peek: ", myStack.peek()) 		 # C
print("Pop: ", myStack.pop())    		 # C
print("LinkedList after Pop: ", end="")  # LinkedList after Pop: 
myStack.traverseAndPrint()               # B -> A ->
print("isEmpty: ", myStack.isEmpty())    # isEmpty: False
print("Size: ", myStack.stackSize())     # Size: 2
```

A reason for using linked lists to implement stacks:
- **Dynamic size** : The stack can grow and shrink dynamically, unlike with arrays.

Reasons for not using linked lists to implement stacks:
- **Extra memory** : Each stack element must contain the address to the next element (the next linked list node).
- **Readability** : The code might be harder to read and write for some because it is longer and more complex.

</details>

### Stack Applications
Stacks are used in many real-world scenarios :
1. Undo/Redo operations in text editors
2. Browser history (back/forward)
3. Function call stack in programming
4. Expression evaluation

</details>
<!------------------------------------->

<details>
  <summary> <b> Queues </b> </summary>

<br/>

> **A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle**.

We can think of a queue as people standing in line in a supermarket.

The first person to stand in line is also the first who can pay and leave the supermarket.

**Basic operations we can do on a queue are** :
**Enqueue** : Adds a new element to the queue.
**Dequeue** : Removes and returns the first (front) element from the queue.
**Peek** : Returns the first element in the queue.
**isEmpty** : Checks if the queue is empty.
**Size** : Finds the number of elements in the queue.

**Queues** can be implemented by using **arrays or linked lists**.

Queues can be used **to implement job scheduling for an office printer**, **order processing for e-tickets**, or **to create algorithms for breadth-first search in graphs**.

<details>
	<summary> Queue Implementation using Lists(Arrays) </summary>

Queue using list
```py
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')

print("Queue: ", queue)

# Peek i.e. frontElement
print("Peek: ", queue[0])              # Queue:  ['A', 'B', 'C']

# Dequeue
print("Dequeue: ", queue.pop(0))       # Peek:  A

print("Queue after Dequeue: ", queue)  # Dequeue:  A

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)            # isEmpty:  False

print("isEmpty: ", len(queue)==0)      # isEmpty:  False

# Size
print("Size: ", len(queue))            # Size: 2
```
Note: While using a list is simple, removing elements from the beginning (dequeue operation) requires shifting all remaining elements, making it less efficient for large queues.

**Stack using class**
```py
class Queue:
  def __init__(self):
    self.queue = []
    
  def enqueue(self, element):
    self.queue.append(element)

  def dequeue(self):
    if self.isEmpty():
      return "Queue is empty"
    return self.queue.pop(0)

  def peek(self):
    if self.isEmpty():
      return "Queue is empty"
    return self.queue[0]

  def isEmpty(self):
    return len(self.queue) == 0

  def size(self):
    return len(self.queue)

# Create a queue
myQueue = Queue()

myQueue.enqueue('A')
myQueue.enqueue('B')
myQueue.enqueue('C')
 
print("Queue: ", myQueue.queue)               # Queue:  ['A', 'B', 'C']
print("Peek: ", myQueue.peek())               # Peek:  A
print("Dequeue: ", myQueue.dequeue())         # Dequeue:  A
print("Queue after Dequeue: ", myQueue.queue) # Queue after Dequeue:  ['B', 'C']
print("isEmpty: ", myQueue.isEmpty())         # isEmpty:  False
print("Size: ", myQueue.size())               # Size:  2
```

</details>

<details>
	<summary> Queue Implementation using Linked Lists </summary>

A linked list consists of nodes with some sort of data, and a pointer to the next node.

```
| data, next |------->| data, next |------->| data, next |-------> Null
```

**Benefit with using linked lists**
- A big benefit with using linked lists is that nodes are stored wherever there is free space in memory, the nodes do not have to be stored contiguously right after each other like elements are stored in arrays. 

- Another nice thing with linked lists is that when adding or removing nodes, the rest of the nodes in the list do not have to be shifted.

```py
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

class Queue:
  def __init__(self):
    self.front = None
    self.rear = None
    self.length = 0

  def enqueue(self, element):
    new_node = Node(element)
    if self.rear is None:
      self.front = self.rear = new_node
      self.length += 1
      return
    self.rear.next = new_node
    self.rear = new_node
    self.length += 1

  def dequeue(self):
    if self.isEmpty():
      return "Queue is empty"
    temp = self.front
    self.front = temp.next
    self.length -= 1
    if self.front is None:
      self.rear = None
    return temp.data

  def peek(self):
    if self.isEmpty():
      return "Queue is empty"
    return self.front.data

  def isEmpty(self):
    return self.length == 0

  def size(self):
    return self.length

  def printQueue(self):
    temp = self.front
    while temp:
      print(temp.data, end=" -> ")
      temp = temp.next
    print()

# Create a queue
myQueue = Queue()

myQueue.enqueue('A')
myQueue.enqueue('B')
myQueue.enqueue('C')

print("Queue: ", end="")
myQueue.printQueue()
print("Peek: ", myQueue.peek())
print("Dequeue: ", myQueue.dequeue())
print("Queue after Dequeue: ", end="")
myQueue.printQueue()
print("isEmpty: ", myQueue.isEmpty())
print("Size: ", myQueue.size())
```

**Reasons for using linked lists to implement queues** :
- **Dynamic size** : The queue can grow and shrink dynamically, unlike with arrays.
- **No shifting** : The front element of the queue can be removed (enqueue) without having to shift other elements in the memory.

**Reasons for not using linked lists to implement queues** :
- **Extra memory** : Each queue element must contain the address to the next element (the next linked list node).
- **Readability** : The code might be harder to read and write for some because it is longer and more complex.

</details>

### Queue Applications

Queues are used in many real-world scenarios :
1. Task scheduling in operating systems
2. Breadth-first search in graphs
3. Message queues in distributed systems


</details>
<!------------------------------------->

<details>
	<summary> <b> Linked Lists </b> </summary>

<br/>

> A **Linked List** is, as the word implies, a list where the nodes are linked together. 

> **Each node contains data and a pointer**.
 
> The way they are linked together is that each node points to where in the memory the next node is placed.

A linked list consists of **nodes(with some sort of data)**, and a **pointer(link)** to the next node.

```
| data, next |------->| data, next |------->| data, next |-------> Null
```

### Linked Lists vs Arrays

The easiest way to understand linked lists is perhaps by comparing linked lists with arrays.

Linked lists consist of nodes, and is a linear data structure we make ourselves, unlike arrays which is an existing data structure in the programming language that we can use.

Nodes in a linked list store links to other nodes, but array elements do not need to store links to other elements.


### Linked list properties, compared to arrays:

- Linked lists are not allocated to a fixed size in memory like arrays are, so linked lists do not require to move the whole list into a larger memory space when the fixed memory space fills up, like arrays must.

- Linked list nodes are not laid out one right after the other in memory (contiguously), so linked list nodes do not have to be shifted up or down in memory when nodes are inserted or deleted.

- Linked list nodes require more memory to store one or more links to other nodes. Array elements do not require that much memory, because array elements do not contain links to other elements.

- Linked list operations are usually harder to program and require more lines than similar array operations, because programming languages have better built in support for arrays.

- We must traverse a linked list to find a node at a specific position, but with arrays we can access an element directly by writing `arr[4]`.

<details>
	<summary> Types of Linked Lists </summary>

There are three basic forms of linked lists:
1. **Singly linked lists**

A singly linked list is the simplest kind of linked lists. It takes up less space in memory because each node has only one address to the next node, like in the image below.

<img width="625" height="102" alt="image" src="https://github.com/user-attachments/assets/d74049dd-a34c-4420-b9e0-7ca441323a3a" />


2. **Doubly linked lists**
A doubly linked list has nodes with addresses to both the previous and the next node, like in the image below, and therefore takes up more memory. But doubly linked lists are good if you want to be able to move both up and down in the list.

<img width="625" height="102" alt="image" src="https://github.com/user-attachments/assets/e6c20931-b57e-429a-94dc-dfff942be1d7" />


3. **Circular linked lists**

A circular linked list is like a singly or doubly linked list with the first node, the "head", and the last node, the "tail", connected.

In singly or doubly linked lists, we can find the start and end of a list by just checking if the links are null. But for circular linked lists, more complex code is needed to explicitly check for start and end nodes in certain applications.

Circular linked lists are good for lists we need to cycle through continuously.

Singly Circular Linked list

<img width="625" height="102" alt="image" src="https://github.com/user-attachments/assets/51a5ea9b-c193-4515-83e4-3a092aab224e" />

Doubly Circular Linked List

<img width="625" height="167" alt="image" src="https://github.com/user-attachments/assets/a6bdc203-3544-4d74-83aa-5a25da8a1fe5" />

</details>

<details>
	<summary> Operations on Linked List </summary>

Basic things we can do with linked lists are:

1. **Traversal**
2. **Remove a node**
3. **Insert a node**
4. **Sort**


### Traversal of a Linked List

Traversal of linked lists is typically done to search for a specific node, and read or modify the node's content, remove the node, or insert a node right before or after that node.

Traversal of a singly linked list
```py
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

def traverseAndPrint(head):
  currentNode = head
  while currentNode:
    print(currentNode.data, end=" -> ")
    currentNode = currentNode.next
  print("null")

node1 = Node(7)
node2 = Node(11)
node3 = Node(3)
node4 = Node(2)
node5 = Node(9)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

traverseAndPrint(node1)
```

Finding the lowest value in a singly linked list
```py
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

def findLowestValue(head):
  minValue = head.data
  currentNode = head.next
  while currentNode:
    if currentNode.data < minValue:
      minValue = currentNode.data
    currentNode = currentNode.next
  return minValue

node1 = Node(7)
node2 = Node(11)
node3 = Node(3)
node4 = Node(2)
node5 = Node(9)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

print("The lowest value in the linked list is:", findLowestValue(node1))
```

### Delete(Remove) a Node in a Linked List

If We want to delete a node in a linked list, it is important to connect the nodes on each side of the node before deleting it, so that the linked list is not broken.

So before deleting the node, we need to get the next pointer from the previous node, and connect the previous node to the new next node before deleting the node in between.

Also, it is a good idea to first connect next pointer to the node after the node we want to delete, before we delete it. This is to avoid a **'dangling' pointer**, a pointer that points to nothing, even if it is just for a brief moment.

Deleting a specific node in a singly linked list
```py
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

def traverseAndPrint(head):
  currentNode = head
  while currentNode:
    print(currentNode.data, end=" -> ")
    currentNode = currentNode.next
  print("null")

def deleteSpecificNode(head, nodeToDelete):
  if head == nodeToDelete:
    return head.next

  currentNode = head
  while currentNode.next and currentNode.next != nodeToDelete:
    currentNode = currentNode.next

  if currentNode.next is None:
    return head

  currentNode.next = currentNode.next.next

  return head

node1 = Node(7)
node2 = Node(11)
node3 = Node(3)
node4 = Node(2)
node5 = Node(9)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

print("Before deletion:")
traverseAndPrint(node1)

# Delete node4
node1 = deleteSpecificNode(node1, node4)

print("\nAfter deletion:")
traverseAndPrint(node1)
```

### Insert a Node in a Linked List

Inserting a node into a linked list is very similar to deleting a node, because in both cases we need to take care of the next pointers to make sure we do not break the linked list.

To insert a node in a linked list we first need to create the node, and then at the position where we insert it, we need to adjust the pointers so that the previous node points to the new node, and the new node points to the correct next node.
1. New node is created
2. Node 1 is linked to new node
3. New node is linked to next node

Inserting a node in a singly linked list 
```py
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

def traverseAndPrint(head):
  currentNode = head
  while currentNode:
    print(currentNode.data, end=" -> ")
    currentNode = currentNode.next
  print("null")

def insertNodeAtPosition(head, newNode, position):
  if position == 1:
    newNode.next = head
    return newNode

  currentNode = head
  for _ in range(position - 2):
    if currentNode.next is None:
      break
    currentNode = currentNode.next

  newNode.next = currentNode.next
  currentNode.next = newNode
  return head

node1 = Node(7)
node2 = Node(3)
node3 = Node(2)
node4 = Node(9)

node1.next = node2
node2.next = node3
node3.next = node4

print("Original list:")
traverseAndPrint(node1)

# Insert a new node with value 97 at position 2
newNode = Node(97)
node1 = insertNodeAtPosition(node1, newNode, 2)

print("\nAfter insertion:")
traverseAndPrint(node1)
```

</details>

</details>
<!------------------------------------->

<details>
	<summary> <b> Hash Tables </b> </summary>

<br/>

A Hash Table is a data structure designed to be fast to work with.

The reason Hash Tables are sometimes preferred instead of arrays or linked lists is because searching for, adding, and deleting data can be done really quickly, even for large amounts of data.

- In a Linked List, finding a person "Ram" takes time because we would have to go from one node to the next, checking each node, until the node with "Ram" is found.

- And finding "Ram" in an list/array could be fast if we knew the index, but when we only know the name "Ram", we need to compare each element and that takes time.

**With a Hash Table** however, finding "Ram" is done really fast because there is a way to go directly to where "Ram" is stored, **using something called a hash function.**


### Hash Tables

> **a data structure that represent a dynamic set of data**

Hash tables support `insert`, `delete` and `Search` operation. 

Hash table is best for searching as It takes Avg O(1) and Worst case O(N)

Hash tables sometimes use exhangeably with dictionary.

> **Dictionary** = generic way to map **keys to values**

> **Hash table** = implementation of a dictionary using hashing function

```py
dictionary = {
  'a': 1,
  'b': 9,
  'c': "Ram",
  'd': True,
}

# insert
dictionary['e'] = False

# delete
dictionary['a']

# search
print(dictionary['c'])
```
Let's see Keys values mapping implementation, to do this we have a concept similar to Hash tables i.e. **direct-access tables**. <br/>
With direct access tables we have a universe of keys. Some of keys are in use and they point to data. <br/>
With direct access tables insert, delete and search all are done in constant time. <br/>
In other words, **direct-access table is an array and if we need to represent every key in the universe, u is unbounded and impracticle to store in memory.**

With hash tables, space requirement is O(K) where k is the number of keys.  <br/>
To achieve this we introduce a hash function that maps keys to a location in table that holds data(value). <br/>
bcuz our universe of keys is no longer unbounded.
It is possible that hashing two different keys may result in the same value called **Collision**.

One method to accomodate collision is called **Chaining**.

To support chaining, we have to introduce linked list. And our table location become a bucket of values.

**hash function** 

**Goals** <br/>
To keep search as close as possible to O(1) we need a hash function that **maximizes randomness** and **produce the least amount of collisions**.

Some examples of hash functions:
- division
- multiplication
- universal hashing
- dynamic perfect hashing
- static perfect hashing

**Hashing by division**
```
h(k) = k % m
where m = size of the table

Let's say we have a hash table of size 13
then h(k) = k % 13
if k = 50
then h(50) = 50 % 13
           = 11
```

### Building A Hash Table from Scratch

To get the idea of what a Hash Table is, let's try to build one from scratch, to store unique first names inside it.

We will build the Hash Table in 5 steps:
1. Create an empty list (it can also be a dictionary or a set).
2. Create a hash function.
3. Inserting an element using a hash function.
4. Looking up an element using a hash function.
5. Handling collisions.

**Step 1: Create an Empty List**
```py
my_list = [None, None, None, None, None, None, None, None, None, None]
```
Each of these elements is called a **bucket** in a Hash Table.

**Step 2: Create a Hash Function**
```py
# Create a Hash Function that sums the Unicode numbers
# of each character and return a number between 0 and 9

def hash_function(value):
  sum_of_chars = 0
  for char in value:
    sum_of_chars += ord(char)

  return sum_of_chars % 10

print("'Ram' has hash code:", hash_function('Ram'))
# R -> 82 a -> 97 m -> 109
# 82+97+109 == 288 % 10 ==> 8
```
The number returned by the hash function is called the **hash code**.

According to our hash function, "Ram" should be stored at index 8.

**Step 3: Inserting an Element**
```py
# Create a function that add items to our hash table.

def add(name):
  index = hash_function(name)
  my_list[index] = name

add('Ram')
print(my_list)

# Now, my_list = [None, None, None, None, None, None, None, None, 'Ram', None]

add('Shyam')
add('Mohan')
add('Rohan')
add('Sohan')
print(my_list)
```

**Step 4: Looking up a name**
```py
def contains(name):
  index = hash_function(name)
  return my_list[index] == name

print("'Ram' is in the Hash Table:", contains('Ram'))
```

**Step 5: Handling collisions**
```py
my_list = [
  [],
  [],
  [],
  [],
  [],
  [],
  [],
  [],
  [],
  []
]

def hash_function(value):
  sum_of_chars = 0
  for char in value:
    sum_of_chars += ord(char)

  return sum_of_chars % 10

def add(name):
  index = hash_function(name)
  my_list[index].append(name)

def contains(name):
  index = hash_function(name)
  print(my_list[index])
  return name in my_list[index]

add('Ram')
add('Shyam')
add('Mohan')
add('Rohan')
add('Sohan')

print(my_list)

print(contains("Shyam"))
print(contains("Rohan"))
print(contains("Ram"))
```
Searching for "Shyam" now takes a little bit longer time, because we also find "Sohan" in the same bucket, but still much faster than searching the entire Hash Table.

### Uses of Hash Tables

Hash Tables are great for:
- Checking if something is in a collection (like finding a book in a library).
- Storing unique items and quickly finding them (like storing phone numbers).
- Connecting values to keys (like linking names to phone numbers).

The most important reason why Hash Tables are great for these things is that Hash Tables are very fast compared Arrays and Linked Lists, especially for large sets. <br/>
Arrays and Linked Lists have time complexity O(n) for search and delete, while Hash Tables have just O(1) on average.


### Hash Tables Summarized

- Hash Table elements are stored in storage containers called buckets.

- A hash function takes the key of an element to generate a hash code.

- The hash code says what bucket the element belongs to, so now we can go directly to that Hash Table element: to modify it, or to delete it, or just to check if it exists.

- A collision happens when two Hash Table elements have the same hash code, because that means they belong to the same bucket.

- Collision can be solved by Chaining by using lists to allow more than one element in the same bucket.


</details>
<!------------------------------------->

<details>
	<summary> <b> Trees </b> </summary>

<br/>

> **A tree is a hierarchical data structure consisting of nodes connected by edges.**

> **Each node contains a value and references to its child nodes.**

The Tree data structure is similar to Linked Lists in that each node contains data and can be linked to other nodes.

We know data structures like **Arrays, Linked Lists, Stacks, and Queues**. These are all linear structures, which means that each element follows directly after another in a sequence. 

Trees however, are different. In a Tree, a single element can have multiple 'next' elements, allowing the data structure to branch out in various directions.

<img width="400" height="200" alt="image" src="https://github.com/user-attachments/assets/1027c053-e117-4bcd-83c3-8a7239206ac4" />


### Tree data structure can be useful in many cases:

**Hierarchical Data** : File systems, organizational models, etc. <br/>
**Databases** : Used for quick data retrieval. <br/>
**Routing Tables** : Used for routing data in network algorithms. <br/>
**Sorting/Searching** : Used for sorting data and searching for data. <br/>
**Priority Queues** : Priority queue data structures are commonly implemented using trees, such as binary heaps. 

### Types of Trees

1. **Binary Trees**   
- Each node has up to two children, the left child node and the right child node.
- This structure is the foundation for more complex tree types like Binay Search Trees and AVL Trees.

2. **Binary Search Trees (BSTs)** 
- A type of Binary Tree where for each node, the left child node has a lower value, and the right child node has a higher value.

3. **AVL Trees**  
- A type of Binary Search Tree that **self-balances** so that for every node, the difference in height between the left and right subtrees is at most one. This balance is maintained through rotations when nodes are inserted or deleted.

### Trees vs Arrays and Linked Lists

**Benefits of Trees over Arrays and Linked Lists**

**Arrays** are fast when you want to access an element directly, like element number 700 in an array of 1000 elements for example. But inserting and deleting elements require other elements to shift in memory to make place for the new element, or to take the deleted elements place, and that is time consuming.

**Linked Lists** are **fast when inserting or deleting nodes**, no memory shifting needed, but to access an element inside the list, the list must be traversed, and that takes time.

**Trees**, such as Binary Trees, Binary Search Trees and AVL Trees, are great compared to Arrays and Linked Lists because they are BOTH **fast at accessing a node, AND fast when it comes to deleting or inserting a node**, with no shifts in memory needed.

</details>
<!------------------------------------->

<details>
	<summary> <b> Binary Trees </b> </summary>

<br/>

> **A Binary Tree is a type of tree data structure where each node can have a maximum of two child nodes, a left child node and a right child node.**

This restriction, that a node can have a maximum of two child nodes, gives us many benefits:

- Algorithms like traversing, searching, insertion and deletion become easier to understand, to implement, and run faster.
  
- Keeping data sorted in a Binary Search Tree (BST) makes searching very efficient.

- Balancing trees is easier to do with a limited number of child nodes, using an AVL Binary Tree for example.
Binary Trees can be represented as arrays, making the tree more memory efficient.

<img width="400" height="250" alt="image" src="https://github.com/user-attachments/assets/d4b565dc-9085-47ec-88e5-d2fea06213e5" />


### Binary Tree Implementation

```py
# Create a Binary Tree

class TreeNode:
  def __init__(self, data):
    self.data = data
    self.left = None
    self.right = None

root = TreeNode('R')
nodeA = TreeNode('A')
nodeB = TreeNode('B')
nodeC = TreeNode('C')
nodeD = TreeNode('D')
nodeE = TreeNode('E')
nodeF = TreeNode('F')
nodeG = TreeNode('G')

root.left = nodeA
root.right = nodeB

nodeA.left = nodeC
nodeA.right = nodeD

nodeB.left = nodeE
nodeB.right = nodeF

nodeF.left = nodeG

# Test
print("root.right.left.data:", root.right.left.data)
```

### Types of Binary Trees

1. **Balanced Binary Tree**
- A **balanced Binary Tree** has at most 1 in difference between its left and right subtree heights, for each node in the tree.

<img width="297" height="285" alt="image" src="https://github.com/user-attachments/assets/75e223bf-5400-4095-b25e-7c58d3a6cfac" />

<br/>

2. **Complete Binary Tree**
- A **complete Binary Tree** has all levels full of nodes, except the last level, which is can also be full, or filled from left to right. 
- The properties of a complete Binary Tree means it is also balanced.

<img width="327" height="292" alt="image" src="https://github.com/user-attachments/assets/9618c658-a9e8-4ffe-953f-7aabd09617ca" />

<br/>

3. **Full Binary Tree**
- A **full Binary Tree** is a kind of tree where each node has either 0 or 2 child nodes.

<img width="288" height="283" alt="image" src="https://github.com/user-attachments/assets/85efa85c-5663-4975-a04d-21732349d7b5" />

<br/>

4. **Perfect Binary Tree**
- A **perfect Binary Tree** has all leaf nodes on the same level, which means that all levels are full of nodes, and all internal nodes have two child nodes.
- The properties of a perfect Binary Tree means it is also full, balanced, and complete.

<img width="290" height="221" alt="image" src="https://github.com/user-attachments/assets/c2207e29-af0c-446b-b462-1eebf9e20c77" />


### Binary Tree Traversal

Going through a Tree by visiting every node, one node at a time, is called traversal.

There are two main categories of Tree traversal methods:

**1. Breadth First Search (BFS)** is when the nodes on the same level are visited before going to the next level in the tree. This means that the tree is explored in a more sideways direction.

**2. Depth First Search (DFS)** is when the traversal moves down the tree all the way to the leaf nodes, exploring the tree branch by branch in a downwards direction.


There are three different types of DFS traversals:
1. **pre-order**
2. **in-order**
3. **post-order**

**Pre-order Traversal** is done by visiting the root node first, then recursively do a pre-order traversal of the left subtree, followed by a recursive pre-order traversal of the right subtree.

```py
def preOrderTraversal(node):
  if node is None:
    return
  print(node.data, end=", ")
  preOrderTraversal(node.left)
  preOrderTraversal(node.right)
```

**In-order Traversal** does a recursive In-order Traversal of the left subtree, visits the root node, and finally, does a recursive In-order Traversal of the right subtree. 

```py
def inOrderTraversal(node):
  if node is None:
    return
  inOrderTraversal(node.left)
  print(node.data, end=", ")
  inOrderTraversal(node.right)
```

**Post-order Traversal** works by recursively doing a Post-order Traversal of the left subtree and the right subtree, followed by a visit to the root node. 

```py
def postOrderTraversal(node):
  if node is None:
    return
  postOrderTraversal(node.left)
  postOrderTraversal(node.right)
  print(node.data, end=", ")
```


</details>
<!------------------------------------->

<details>
	<summary> <b> Binary Search Trees </b> </summary>

<br/>

> **A Binary Search Tree is a Binary Tree where every node's left child has a lower value, and every node's right child has a higher value.**

The advantage with Binary Search Trees is that operations like **search, delete, and insert are fast** and done without having to shift values in memory.


A Binary Search Tree (BST) is a type of Binary Tree data structure, where the following properties must be true for any node "X" in the tree:
- The X node's left child and all of its descendants (children, children's children, and so on) have lower values than X's value.
- The right child, and all its descendants have higher values than X's value.
- Left and right subtrees must also be Binary Search Trees.

<img width="290" height="195" alt="image" src="https://github.com/user-attachments/assets/5f6cccb8-f1e4-41dd-985f-32e554d06f1d" />

The **_size of a tree_** is the number of nodes in it **(n)**.

A **_subtree_** starts with one of the nodes in the tree as a local root, and consists of that node and all its descendants.

The **_descendants_** of a node are all the child nodes of that node, and all their child nodes, and so on. Just start with a node, and the descendants will be all nodes that are connected below that node.

The **_node's height_** is the maximum number of edges between that node and a leaf node.

**Traversal of a Binary Search Tree**
```py
class TreeNode:
  def __init__(self, data):
    self.data = data
    self.left = None
    self.right = None

def inOrderTraversal(node):
  if node is None:
    return
  inOrderTraversal(node.left)
  print(node.data, end=", ")
  inOrderTraversal(node.right)

root = TreeNode(13)
node7 = TreeNode(7)
node15 = TreeNode(15)
node3 = TreeNode(3)
node8 = TreeNode(8)
node14 = TreeNode(14)
node19 = TreeNode(19)
node18 = TreeNode(18)

root.left = node7
root.right = node15

node7.left = node3
node7.right = node8

node15.left = node14
node15.right = node19

node19.left = node18

# Traverse
inOrderTraversal(root)

#-----------------------------------
# The in-order traversal produces a list of numbers in an increasing (ascending) order,
# which means that this Binary Tree is a Binary Search Tree.
```

**Search for a Value in a BST**
```
How it works:

1. Start at the root node.
2. If this is the value we are looking for, return.
3. If the value we are looking for is higher, continue searching in the right subtree.
4. If the value we are looking for is lower, continue searching in the left subtree.
5. If the subtree we want to search does not exist, depending on the programming language, return None, or NULL, or something similar, to indicate that the value is not inside the BST.
```
```py
def search(node, target):
  if node is None:
    return None
  elif node.data == target:
    return node
  elif target < node.data:
    return search(node.left, target)
  else:
    return search(node.right, target)

# Search for a value
result = search(root, 13)
if result:
  print(f"Found the node with value: {result.data}")
else:
  print("Value not found in the BST.")
```
**The time complexity for searching a BST for a value is O(h), where h is the height of the tree.**

**Insert a Node in a BST**
```
How it works:

1. Start at the root node.
2. Compare each node:
   - Is the value lower? Go left.
   - Is the value higher? Go right.
3. Continue to compare nodes with the new value until there is no right or left to compare with.
That is where the new node is inserted.
```
```py
def insert(node, data):
  if node is None:
    return TreeNode(data)
  else:
    if data < node.data:
      node.left = insert(node.left, data)
    elif data > node.data:
      node.right = insert(node.right, data)
  return node

# Inserting new value into the BST
insert(root, 10)
```

**Delete a Node in a BST**
```
How it works:

1. If the node is a leaf node, remove it by removing the link to it.
2. If the node only has one child node, connect the parent node of the node you want to remove to that child node.
3. If the node has both right and left child nodes: Find the node's in-order successor, change values with that node, then delete it.
```

```py
def delete(node, data):
  if not node:
    return None

  if data < node.data:
    node.left = delete(node.left, data)
  elif data > node.data:
    node.right = delete(node.right, data)
  else:
    # Node with only one child or no child
    if not node.left:
      temp = node.right
      node = None
      return temp
    elif not node.right:
      temp = node.left
      node = None
      return temp

    # Node with two children, get the in-order successor
    node.data = minValueNode(node.right).data
    node.right = delete(node.right, node.data)

  return node

# Delete node 15
delete(root,15)
```

Searching a BST is just as fast as Binary Search on an array, with the same time complexity `O(log n)`.

And deleting and inserting new values can be done without shifting elements in memory, just like with Linked Lists.

</details>
<!------------------------------------->

<details>
	<summary> <b> AVL Trees </b> </summary>

<br/>

The AVL Tree is a type of Binary Search Tree named after two Soviet inventors Georgy **Adelson-Velsky** and **Evgenii Landis** who invented the AVL Tree in 1962.


> **AVL trees are self-balancing**, which means that the **tree height is kept to a minimum** so that a very fast runtime is guaranteed for searching, inserting and deleting nodes, with **time complexity O(logn)**.

The only difference between a regular Binary Search Tree and an AVL Tree is that **AVL Trees do rotation operations in addition, to keep the tree balance**.

A Binary Search Tree is in balance when the difference in height between left and right subtrees is less than 2.

By keeping balance, the AVL Tree ensures a minimum tree height, which means that search, insert, and delete operations can be done really fast.

<img width="600" height="526" alt="image" src="https://github.com/user-attachments/assets/cc17b30b-0586-4314-a6e5-f15f33ab5938" />

The two trees above are both Binary Search Trees, they have the same nodes, and the same in-order traversal (alphabetical), but the height is very different because the AVL Tree has balanced itself.

</details>
<!------------------------------------->

<details>
	<summary> <b> Graph </b> </summary>
<br/>
	
> **A Graph is a non-linear data structure that consists of _vertices(nodes)_ and _edges_**.

- **A vertex, also called a node, is a point or an object in the Graph**.
- **An edge is used to connect two vertices with each other**.

<img width="400" height="240" alt="image" src="https://github.com/user-attachments/assets/cdd13592-12c0-4179-83cb-deb0ad6576db" />

Graphs are non-linear because the data structure allows us to have different paths to get from one vertex to another, unlike with linear data structures like Arrays or Linked Lists.

Graphs are used to represent and solve problems where the data consists of objects and relationships between them, such as:
- **Social Networks** : Each person is a vertex, and relationships (like friendships) are the edges. Algorithms can suggest potential friends.
- **Maps and Navigation** : Locations, like a town or bus stops, are stored as vertices, and roads are stored as edges. Algorithms can find the shortest route between two locations when stored as a Graph.
- **Internet** : Can be represented as a Graph, with web pages as vertices and hyperlinks as edges.
- **Biology**: Graphs can model systems like neural networks or the spread of diseases.

### Graph Representations

A Graph representation tells us how a Graph is stored in memory.

Different Graph representations can:
- take up more or less space.
- be faster or slower to search or manipulate.
- be better suited depending on what type of Graph we have (weighted, directed, etc.), and what we want to do with the Graph.
- be easier to understand and implement than others.

</details>
<!------------------------------------->

### Searching 

<details>
	<summary> <b> Linear Search </b> </summary>

<br/>

> **Linear search(sequential search) is the simplest search algorithm. It _checks each element one by one_**.

```
How it works:

1. Go through the array value by value from the start.
2. Compare each value to check if it is equal to the value we are looking for.
3. If the value is found, return the index of that value.
4. If the end of the array is reached and the value is not found, return -1 to indicate that the value was not found.
```

### Implementation of Linear Search

```py
def linearSearch(arr, targetVal):
  for i in range(len(arr)):
    if arr[i] == targetVal:
      return i
  return -1

mylist = [3, 7, 2, 9, 5, 1, 8, 4, 6]
x = 4

result = linearSearch(mylist, x)

if result != -1:
  print(x, "Found at index", result)
else:
  print(x, "Not found")

#----------------------------------------
mylist = [3, 7, 2, 9, 5, 1, 8, 4, 6]

x = 4
if x in mylist:
  print(x, "Found!")
else:
  print(x, "Not found!")
```

**Linear Search Time Complexity** is **_O(n)_**

<img width="433" height="302" alt="image" src="https://github.com/user-attachments/assets/ea037d10-18ab-4bfd-b324-b3071ad779a4" />


Note : **If the array is already sorted, it is better to use the much faster Binary Search algorithm.**


</details>
<!------------------------------------->

<details>
	<summary> <b> Binary Search </b> </summary>

<br/>

> **The Binary Search algorithm searches through a _sorted array_ and returns the index of the value it searches for.**

Binary Search is much faster than Linear Search, but requires a sorted array to work.

```
How it works:

1. Check the value in the center of the array.

2. If the target value is lower, search the left half of the array.
If the target value is higher, search the right half.

3. Continue step 1 and 2 for the new reduced part of the array
until the target value is found or until the search area is empty.

4. If the value is found, return the target value index.
If the target value is not found, return -1.

---------------------------------------------------------------

Step 1: We start with an array.
[ 2, 3, 7, 7, 11, 15, 25]

Step 2: The value in the middle of the array at index 3, is it equal to 11?
[ 2, 3, 7, 7, 11, 15, 25]

Step 3: 7 is less than 11, so we must search for 11 to the right of index 3.
The values to the right of index 3 are [ 11, 15, 25].
The next value to check is the middle value 15, at index 5.
[ 2, 3, 7, 7, 11, 15, 25]

Step 4: 15 is higher than 11, so we must search to the left of index 5.
We have already checked index 0-3,
so index 4 is only value left to check.
[ 2, 3, 7, 7, 11, 15, 25]
```

**Implementation of Binary Search**
```py
def binarySearch(arr, targetVal):
  left = 0
  right = len(arr) - 1

  while left <= right:
    mid = (left + right) // 2

    if arr[mid] == targetVal:
      return mid

    if arr[mid] < targetVal:
      left = mid + 1
    else:
      right = mid - 1

  return -1

mylist = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
x = 11

result = binarySearch(mylist, x)

if result != -1:
  print(x, "Found at index", result)
else:
  print(x, "Not found")
```

**Binary Search Time Complexity** is **_O(logN)_**

<img width="451" height="381" alt="image" src="https://github.com/user-attachments/assets/07e23744-8601-4f16-8d3d-a29e13e25a55" />

When writing time complexity using Big O notation we could also just have written O(logN), but O(log2 N) reminds us that the array search area is halved for every new comparison, which is the basic concept of Binary Search, so we will just keep the base 2 indication in this case.

</details>
<!------------------------------------->

### Sorting

<details>
	<summary> <b> Bubble Sort </b> </summary>

<br/>

> Bubble Sort is an algorithm that sorts an array from the lowest value to the highest value.

```
How it works:

1. Go through the array, one value at a time.
2. For each value, compare the value with the next value.
3. If the value is higher than the next one, swap the values so that the highest value comes last.
4. Go through the array as many times as there are values in the array.
Repeat until no more swaps are needed and you will get a sorted array
-----------------------------------------------------------------------
Step 1: We start with an unsorted array.
[7, 12, 9, 11, 3]

Step 2: We look at the two first values. Does the lowest value come first? Yes, so we don't need to swap them.
[7, 12, 9, 11, 3]

Step 3: Take one step forward and look at values 12 and 9. Does the lowest value come first? No.
[7, 12, 9, 11, 3]

Step 4: So we need to swap them so that 9 comes first.
[7, 9, 12, 11, 3]

Step 5: Taking one step forward, looking at 12 and 11.
[7, 9, 12, 11, 3]

Step 6: We must swap so that 11 comes before 12.
[7, 9, 11, 12, 3]

Step 7: Looking at 12 and 3, do we need to swap them? Yes.
[7, 9, 11, 12, 3]

Step 8: Swapping 12 and 3 so that 3 comes first.
[7, 9, 11, 3, 12]
```

**Implementation of Bubble Sort**
```py
mylist = [64, 34, 25, 12, 22, 11, 90, 5]

n = len(mylist)
for i in range(n-1):
  for j in range(n-i-1):
    if mylist[j] > mylist[j+1]:
      mylist[j], mylist[j+1] = mylist[j+1], mylist[j]

print(mylist)
```

The Bubble Sort algorithm can be improved a little bit more. <br/>
If array is almost sorted already, with the lowest numbers at the start.
```py
mylist = [7, 3, 9, 12, 11]

n = len(mylist)
for i in range(n-1):
  swapped = False
  for j in range(n-i-1):
    if mylist[j] > mylist[j+1]:
      mylist[j], mylist[j+1] = mylist[j+1], mylist[j]
      swapped = True
  if not swapped:
    break

print(mylist)
```

**The time complexity for Bubble Sort is: O(n2)**

There are sorting algorithms that are faster than this, like Quicksort.

<img width="440" height="358" alt="image" src="https://github.com/user-attachments/assets/e4065b7f-6d1f-4a32-b41d-445483c61c7a" />


</details>
<!------------------------------------->
<details>
	<summary> <b> Selection Sort </b> </summary>

<br/>

> **The Selection Sort algorithm finds the lowest value in an array and moves it to the front of the array.**

looks through the array again and again, moving the next lowest values to the front, until the array is sorted.

```
How it works:

1. Go through the array to find the lowest value.
2. Move the lowest value to the front of the unsorted part of the array.
3. Go through the array again as many times as there are values in the array.
---------------------------------------------------------------------------
Step 1: We start with an unsorted array.
[ 7, 12, 9, 11, 3]

Step 2: Go through the array, one value at a time.
Which value is the lowest? 3, right?
[ 7, 12, 9, 11, 3]

Step 3: Move the lowest value 3 to the front of the array.
[ 3, 7, 12, 9, 11]

Step 4: Look through the rest of the values, starting with 7. 7 is the lowest value,
and already at the front of the array, so we don't need to move it.
[ 3, 7, 12, 9, 11]

Step 5: Look through the rest of the array: 12, 9 and 11. 9 is the lowest value.
[ 3, 7, 12, 9, 11]

Step 6: Move 9 to the front.
[ 3, 7, 9, 12, 11]

Step 7: Looking at 12 and 11, 11 is the lowest.
[ 3, 7, 9, 12, 11]

Step 8: Move it to the front.
[ 3, 7, 9, 11, 12]
```

**Implementation of Selection Sort**
```py
mylist = [64, 34, 25, 5, 22, 11, 90, 12]

n = len(mylist)
for i in range(n-1):
  min_index = i
  for j in range(i+1, n):
     if mylist[j] < mylist[min_index]:
       min_index = j
  min_value = mylist.pop(min_index)
  mylist.insert(i, min_value)

print(mylist)
```

Improved Selection Sort
```py
mylist = [64, 34, 25, 12, 22, 11, 90, 5]

n = len(mylist)
for i in range(n):
  min_index = i
  for j in range(i+1, n):
     if mylist[j] < mylist[min_index]:
       min_index = j
  mylist[i], mylist[min_index] = mylist[min_index], mylist[i]

print(mylist)
```

The time complexity for the Selection Sort is O(N^2).

```
On average, about n/2 elements are compared to find the lowest value in each loop.

And Selection Sort must run the loop to find the lowest value approximately n times.

We get time complexity:  O(N/2*N) = N^2/2 = N^2
```

<img width="451" height="372" alt="image" src="https://github.com/user-attachments/assets/3400ac39-a827-4907-920b-3ce3f0a64312" />


</details>
<!------------------------------------->

<details>
	<summary> <b> Insertion Sort </b> </summary>


<br/>

> The Insertion Sort uses one part of the array to hold the sorted values, and the other part of the array to hold values that are not sorted yet.

Takes one value at a time from the unsorted part of the array and puts it into the right place in the sorted part of the array, until the array is sorted.

```
How it works:

1. Take the first value from the unsorted part of the array.
2. Move the value into the correct place in the sorted part of the array.
3. Go through the unsorted part of the array again as many times as there are values.
---------------------------------------------------------------------------
Step 1: We start with an unsorted array.
[ 7, 12, 9, 11, 3]

Step 2: We can consider the first value as the initial sorted part of the array.
If it is just one value, it must be sorted, right?
[ 7, 12, 9, 11, 3]

Step 3: The next value 12 should now be moved into the correct position
in the sorted part of the array.
But 12 is higher than 7, so it is already in the correct position.
[ 7, 12, 9, 11, 3]

Step 4: Consider the next value 9.
[ 7, 12, 9, 11, 3]

Step 5: The value 9 must now be moved into the correct position
inside the sorted part of the array, so we move 9 in between 7 and 12.
[ 7, 9, 12, 11, 3]

Step 6: The next value is 11.
[ 7, 9, 12, > 11, 3]

Step 7: We move it in between 9 and 12 in the sorted part of the array.
[ 7, 9, 11, 12, 3]

Step 8: The last value to insert into the correct position is 3.
[ 7, 9, 11, 12, 3]

Step 9: We insert 3 in front of all other values because it is the lowest value.
[ 3,7, 9, 11, 12]
```

**Implementation of Insertion Sort**
```py
mylist = [64, 34, 25, 12, 22, 11, 90, 5]

n = len(mylist)
for i in range(1,n):
  insert_index = i
  current_value = mylist.pop(i)
  for j in range(i-1, -1, -1):
    if mylist[j] > current_value:
      insert_index = j
  mylist.insert(insert_index, current_value)

print(mylist)
```

Improvised version of insertion sort
```py
mylist = [64, 34, 25, 12, 22, 11, 90, 5]

n = len(mylist)
for i in range(1,n):
  insert_index = i
  current_value = mylist[i]
  for j in range(i-1, -1, -1):
     if mylist[j] > current_value:
       mylist[j+1] = mylist[j]
       insert_index = j
     else:
       break
  mylist[insert_index] = current_value

print(mylist)
```

**The time complexity for Insertion Sort is O(N^2)**
```
On average, each value must be compared to about N/2 other values
 to find the correct place to insert it.

Insertion Sort must run the loop to insert a value in its correct place approximately N times.

We get time complexity for Insertion Sort O(N/2*N) = O(N^2)
```

<img width="450" height="372" alt="image" src="https://github.com/user-attachments/assets/2f30cd96-b97c-419d-9ce0-59732cb8fb3b" />

For Insertion Sort, there is a big difference between best, average and worst case scenarios.

</details>
<!------------------------------------->

<details>
	<summary> <b> Quick Sort </b> </summary>

<br/>

> As the name suggests, **Quicksort is one of the fastest sorting algorithms.**

Quicksort algorithm takes an array of values, chooses one of the values as the 'pivot' element, and moves the other values so that lower values are on the left of the pivot element, and higher values are on the right of it.

Here, the last element of the array is chosen to be the pivot element, but we could also have chosen the first element of the array, or any element in the array really.

Then, the Quicksort algorithm does the same operation recursively on the sub-arrays to the left and right side of the pivot element. This continues until the array is sorted.

```
Recursion is when a function calls itself.

After the Quicksort algorithm has put the pivot element in between a sub-array with lower values on the left side, and a sub-array with higher values on the right side, the algorithm calls itself twice, so that Quicksort runs again for the sub-array on the left side, and for the sub-array on the right side. The Quicksort algorithm continues to call itself until the sub-arrays are too small to be sorted.
```

```
How it works:

1. Choose a value in the array to be the pivot element.
2. Order the rest of the array so that lower values than the pivot element are on the left,
 and higher values are on the right.
3. Swap the pivot element with the first element of the higher values so that the
 pivot element lands in between the lower and higher values.
4. Do the same operations (recursively) for the sub-arrays on the left and right side
of the pivot element.

-----------------------------------------------------------------------------------------

Step 1: We start with an unsorted array.
[ 11, 9, 12, 7, 3]

Step 2: We choose the last value 3 as the pivot element.
[ 11, 9, 12, 7, 3]

Step 3: The rest of the values in the array are all greater than 3,
and must be on the right side of 3. Swap 3 with 11.
[ 3, 9, 12, 7, 11]

Step 4: Value 3 is now in the correct position. We need to sort the
values to the right of 3. We choose the last value 11 as the new pivot element.
[ 3, 9, 12, 7, 11]

Step 5: The value 7 must be to the left of pivot value 11, and
 12 must be to the right of it. Move 7 and 12.
[ 3, 9, 7, 12, 11]

Step 6: Swap 11 with 12 so that lower values 9 and 7 are
on the left side of 11, and 12 is on the right side.
[ 3, 9, 7, 11, 12]

Step 7: 11 and 12 are in the correct positions.
We choose 7 as the pivot element in sub-array [ 9, 7], to the left of 11.
[ 3, 9, 7, 11, 12]

Step 8: We must swap 9 with 7.
[ 3, 7, 9, 11, 12]
```

**Implementation of Quicksort**
```py
def partition(array, low, high):
  pivot = array[high]
  i = low - 1

  for j in range(low, high):
     if array[j] <= pivot:
       i += 1
       array[i], array[j] = array[j], array[i]

  array[i+1], array[high] = array[high], array[i+1]
  return i+1

def quicksort(array, low=0, high=None):
  if high is None:
    high = len(array) - 1

  if low < high:
    pivot_index = partition(array, low, high)
    quicksort(array, low, pivot_index-1)
    quicksort(array, pivot_index+1, high)

mylist = [64, 34, 25, 5, 22, 11, 90, 12]
quicksort(mylist)
print(mylist)
```

**Time Complexity of Quick Sort**

The worst case scenario for Quicksort is O(N^2).

But on average, the time complexity for Quicksort is actually just O(N log N) which is a lot better than for the previous sorting algorithms.


<img width="452" height="368" alt="image" src="https://github.com/user-attachments/assets/d4e4446e-8608-449c-b6b9-95b6ad5da6ba" />

The recursion part of the Quicksort algorithm is actually a reason why the average sorting scenario is so fast, because for good picks of the pivot element, the array will be split in half somewhat evenly each time the algorithm calls itself. So the number of recursive calls do not double, even if the number of values n double.

</details>
<!------------------------------------->

<details>
	<summary> <b> Merge Sort </b> </summary>

<br/>

> Merge Sort algorithm is a **divide-and-conquer algorithm that sorts an array by first breaking it down into smaller arrays, and then building the array back together the correct way so that it is sorted.**

**Divide** : The algorithm starts with breaking up the array into smaller and smaller pieces until one such sub-array only consists of one element.

**Conquer** : The algorithm merges the small pieces of the array back together by putting the lowest values first, resulting in a sorted array.

The breaking down and building up of the array to sort the array is done recursively.

<img width="496" height="565" alt="image" src="https://github.com/user-attachments/assets/25678c44-d1a0-4ef6-85e6-a9c2be1e0904" />


```
How it works:

1. Divide the unsorted array into two sub-arrays, half the size of the original.
2. Continue to divide the sub-arrays as long as the current piece of the array has
 more than one element.
3. Merge two sub-arrays together by always putting the lowest value first.
4. Keep merging until there are no sub-arrays left.

#-----------------------------------------------------

Step 1: We start with an unsorted array, and we know that it splits in half until the sub-arrays
only consist of one element. 
he Merge Sort function calls itself two times, once for each half of the array.
That means that the first sub-array will split into the smallest pieces first.
[ 12, 8, 9, 3, 11, 5, 4]
[ 12, 8, 9] [ 3, 11, 5, 4]
[ 12] [ 8, 9] [ 3, 11, 5, 4]
[ 12] [ 8] [ 9] [ 3, 11, 5, 4]

Step 2: The splitting of the first sub-array is finished, and now it is time to merge.
8 and 9 are the first two elements to be merged.
8 is the lowest value, so that comes before 9 in the first merged sub-array.
[ 12] [ 8, 9] [ 3, 11, 5, 4]

Step 4: Now the second big sub-array is split recursively.
[ 8, 9, 12] [ 3, 11, 5, 4]
[ 8, 9, 12] [ 3, 11] [ 5, 4]
[ 8, 9, 12] [ 3] [ 11] [ 5, 4]

Step 5: 3 and 11 are merged back together in the same order
 as they are shown because 3 is lower than 11.
[ 8, 9, 12] [ 3, 11] [ 5, 4]

Step 6: Sub-array with values 5 and 4 is split, then merged so that 4 comes before 5.
[ 8, 9, 12] [ 3, 11] [ 5] [ 4]
[ 8, 9, 12] [ 3, 11] [ 4, 5]

Step 7: The two sub-arrays on the right are merged. Comparisons are done to create elements
in the new merged array:
3 is lower than 4
4 is lower than 11
5 is lower than 11
11 is the last remaining value
[ 8, 9, 12] [ 3, 4, 5, 11]

Step 8: The two last remaining sub-arrays are merged.
Let's look at how the comparisons are done in more detail to create the
 new merged and finished sorted array:

3 is lower than 8:
Before [ 8, 9, 12] [ 3, 4, 5, 11]
After: [ 3, 8, 9, 12] [ 4, 5, 11]

Step 9: 4 is lower than 8:
Before [ 3, 8, 9, 12] [ 4, 5, 11]
After: [ 3, 4, 8, 9, 12] [ 5, 11]

Step 10: 5 is lower than 8:
Before [ 3, 4, 8, 9, 12] [ 5, 11]
After: [ 3, 4, 5, 8, 9, 12] [ 11]

Step 11: 8 and 9 are lower than 11:
Before [ 3, 4, 5, 8, 9, 12] [ 11]
After: [ 3, 4, 5, 8, 9, 12] [ 11]

Step 12: 11 is lower than 12:
Before [ 3, 4, 5, 8, 9, 12] [ 11]
After: [ 3, 4, 5, 8, 9, 11, 12]
```

**Implementation of Merge Sort**
```py
def mergeSort(arr):
  if len(arr) <= 1:
    return arr

  mid = len(arr) // 2
  leftHalf = arr[:mid]
  rightHalf = arr[mid:]

  sortedLeft = mergeSort(leftHalf)
  sortedRight = mergeSort(rightHalf)

  return merge(sortedLeft, sortedRight)

def merge(left, right):
  result = []
  i = j = 0

  while i < len(left) and j < len(right):
    if left[i] < right[j]:
      result.append(left[i])
      i += 1
    else:
      result.append(right[j])
      j += 1

  result.extend(left[i:])
  result.extend(right[j:])

  return result

mylist = [3, 7, 6, -10, 15, 23.5, 55, -13]
mysortedlist = mergeSort(mylist)
print("Sorted array:", mysortedlist)
```

**Merge Sort without Recursion**
```py
def merge(left, right):
  result = []
  i = j = 0

  while i < len(left) and j < len(right):
    if left[i] < right[j]:
      result.append(left[i])
      i += 1
    else:
      result.append(right[j])
      j += 1

  result.extend(left[i:])
  result.extend(right[j:])

  return result

def mergeSort(arr):
  step = 1 # Starting with sub-arrays of length 1
  length = len(arr)

  while step < length:
    for i in range(0, length, 2 * step):
      left = arr[i:i + step]
      right = arr[i + step:i + 2 * step]

      merged = merge(left, right)

      # Place the merged array back into the original array
      for j, val in enumerate(merged):
        arr[i + j] = val

    step *= 2 # Double the sub-array length for the next iteration

  return arr

mylist = [3, 7, 6, -10, 15, 23.5, 55, -13]
mysortedlist = mergeSort(mylist)
print(mysortedlist)
```

**The time complexity for Merge Sort is : O(N logN)**

<img width="442" height="367" alt="image" src="https://github.com/user-attachments/assets/7465c0da-672a-4224-b013-18ae5af9b421" />


</details>
<!------------------------------------->

<details>
	<summary> <b> Counting Sort </b> </summary>

<br/>

> The Counting Sort algorithm **sorts an array by counting the number of times each value occurs**.

Counting Sort does not compare values like the previous sorting algorithms we have looked at, and only works on non negative integers.

Furthermore, Counting Sort is fast when the range of possible values k is smaller than the number of values n.

```
How it works:

1. Create a new array for counting how many there are of the different values.
2. Go through the array that needs to be sorted.
3. For each value, count it by increasing the counting array at the corresponding index.
4. After counting the values, go through the counting array to create the sorted array.
5. For each count in the counting array, create the correct number of elements, with values that correspond to the counting array index.
```

**Conditions for Counting Sort** <br/>
The reasons why Counting Sort is said to only work for a limited range of non-negative integer values
1. **Integer values** : Counting Sort relies on counting occurrences of distinct values, so they must be integers
2. **Non negative values**
3. **Limited range of values**

```
Step 1: We start with an unsorted array.
myArray = [ 2, 3, 0, 2, 3, 2]

Step 2: We create another array for counting how many there are of each value.
The array has 4 elements, to hold values 0 through 3.
myArray = [ 2, 3, 0, 2, 3, 2]
countArray = [ 0, 0, 0, 0]

Step 3: Now let's start counting.
The first element is 2, so we must increment the counting array element at index 2.
myArray = [ 2, 3, 0, 2, 3, 2]
countArray = [ 0, 0, 1, 0]

Step 4: After counting a value, we can remove it, and count the next value, which is 3.
myArray = [ 3, 0, 2, 3, 2]
countArray = [ 0, 0, 1, 1]

Step 5: The next value we count is 0, so we increment index 0 in the counting array.
myArray = [ 0, 2, 3, 2]
countArray = [ 1, 0, 1, 1]

Step 6: We continue like this until all values are counted.
myArray = [ ]
countArray = [ 1, 0, 3, 2]

Step 7: Now we will recreate the elements from the initial array, and
we will do it so that the elements are ordered lowest to highest.
The first element in the counting array tells us that we have 1 element with value 0.
So we push 1 element with value 0 into the array, and we decrease the element at index 0
 in the counting array with 1.
myArray = [ 0]
countArray = [ 0, 0, 3, 2]

Step 8: From the counting array we see that we do not need to create any elements with value 1.
myArray = [ 0]
countArray = [ 0, 0, 3, 2]

Step 9: We push 3 elements with value 2 into the end of the array.
 And as we create these elements we also decrease the counting array at index 2.
myArray = [ 0, 2, 2, 2]
countArray = [ 0, 0, 0, 2]

Step 10: At last we must add 2 elements with value 3 at the end of the array.
myArray = [0, 2, 2, 2, 3, 3]
countArray = [ 0, 0, 0, 0]
```

**Implementation of Count Sort**
```py
def countingSort(arr):
  max_val = max(arr)
  count = [0] * (max_val + 1)

  while len(arr) > 0:
    num = arr.pop(0)
    count[num] += 1

  for i in range(len(count)):
    while count[i] > 0:
      arr.append(i)
      count[i] -= 1

  return arr

mylist = [4, 2, 2, 6, 3, 3, 1, 6, 5, 2, 3]
mysortedlist = countingSort(mylist)
print(mysortedlist)
```

**The time complexity for Counting Sort is O(N+K)**

</details>
<!------------------------------------->

<details>
	<summary> <b> Redix Sort </b> </summary>

<br/>

> Radix Sort is a linear sorting algorithm (for fixed length digit counts) that **sorts elements by processing them digit by digit.**


The radix (or base) is the number of unique digits in a number system. In the decimal system we normally use, there are 10 different digits from 0 till 9.

Radix Sort uses the radix so that decimal values are put into 10 different buckets (or containers) corresponding to the digit that is in focus, then put back into the array before moving on to the next digit.

Radix Sort is a non comparative algorithm that only works with non negative integers.

```
How it works:

1. Start with the least significant digit (rightmost digit).
2. Sort the values based on the digit in focus by first putting the values in the correct bucket
    based on the digit in focus, and then put them back into array in the correct order.
3. Move to the next digit, and sort again, like in the step above, until there are no digits left.
```

To perform radix sort on the array `[170, 45, 75, 90, 802, 24, 2, 66]`, we follow these steps:

Step 1: Find the largest element, which is 802. It has three digits, so we will iterate three times.

Step 2: Sort the elements based on the unit place digits (X=0).

<img width="807" height="262" alt="image" src="https://github.com/user-attachments/assets/e5f47c03-f2b2-4a2d-b67c-ffafbde0bd55" />

Step 3: Sort the elements based on the tens place digits.

<img width="792" height="271" alt="image" src="https://github.com/user-attachments/assets/b4c8c770-2de9-4c9e-88e5-10ac15758e38" />

Step 4: Sort the elements based on the hundreds place digits

<img width="797" height="276" alt="image" src="https://github.com/user-attachments/assets/9c4c4030-824b-48a7-af23-e58d0a9a25c4" />

Step 5: The array is now sorted in ascending order.

<img width="787" height="190" alt="image" src="https://github.com/user-attachments/assets/fb00e6fa-1100-4fa4-87d0-0a5050b8c0a6" />


**Implementation of Radix Sort**
```py
mylist = [170, 45, 75, 90, 802, 24, 2, 66]
print("Original array:", mylist)
radixArray = [[], [], [], [], [], [], [], [], [], []]
maxVal = max(mylist)
exp = 1

while maxVal // exp > 0:

  while len(mylist) > 0:
    val = mylist.pop()
    radixIndex = (val // exp) % 10
    radixArray[radixIndex].append(val)

  for bucket in radixArray:
    while len(bucket) > 0:
      val = bucket.pop()
      mylist.append(val)

  exp *= 10

print(mylist)
```

**The time complexity for Radix Sort is O(n.k)** <br/>
This means that Radix Sort depends both on the values that need to be sorted n, and the number of digits in the highest value k

<img width="487" height="377" alt="image" src="https://github.com/user-attachments/assets/53eb9402-86a5-4a54-bdb6-4e71ebad3042" />


</details>
<!------------------------------------->




## Level 6 - Interview Questions

<details>
  <summary> 46. Time & space complexity </summary>

<br/>

> Time Complexity and Space Complexity are **_measures used to analyze the efficiency of an algorithm_**.

### Time Complexity

> Time complexity describes **how the running time of an algorithm grows as the input size (n) increases**.

| Complexity | Name         | Example                     |
| ---------- | ------------ | --------------------------- |
| O(1)       | Constant     | Accessing an array element  |
| O(log n)   | Logarithmic  | Binary Search               |
| O(n)       | Linear       | Traversing an array         |
| O(n log n) | Linearithmic | Merge Sort, Heap Sort       |
| O(n²)      | Quadratic    | Nested loops                |
| O(2ⁿ)      | Exponential  | Recursive Fibonacci (naive) |
| O(n!)      | Factorial    | Generating all permutations |

### Space Complexity

> Space complexity describes **how much extra memory an algorithm uses as the input size grows**.

Creates an array of size n.
```py
arr = [0] * n        # Space Complexity = O(n)

#----------------------------------------------
# Uses only a few variables regardless of input size.

sum = 0
for i in range(n):
    sum += i         # Space Complexity = O(1)
```

Nested Loop traversing
```py
for i in range(n):
    for j in range(n):
        print(i, j)

#------------------------------------------
"""
- Outer loop runs n times.
- Inner loop runs n times for each outer iteration.
- Total operations = n × n = n²

 Time Complexity: O(n²)
 Space Complexity: O(1)
"""
```
Finding max element in an array
```py
def find_max(arr):
    max_val = arr[0]
    for num in arr:
        if num > max_val:
            max_val = num
    return max_val
#------------------------------
"""
Traverses the array once → Time Complexity = O(n)
Uses one extra variable → Space Complexity = O(1)
"""
```


[BigOCheatsheet](https://www.bigocheatsheet.com/)

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

Bcuz we **don't need to declare a variable's data type explicitly, and the type is determined at runtime**.

```py
x = 10
print(type(x))     # int

x = "Hello"
print(type(x))     # str

# same variable x can refer to objects of different types during execution
# object has the type not the variable name.
```

> **Python is dynamically typed because variable types are determined at runtime rather than being explicitly declared. A variable is simply a reference to an object, and the object determines its type. Therefore, the same variable can reference objects of different types during execution.**

**Dynamically typed** does not mean Python has no types. Python is actually strongly and dynamically typed.

</details>
<!------------------------------------>


<details>
  <summary> 57. How does Python manage memory? </summary>

Python manages memory automatically using a private heap managed by the Python Memory Manager. In CPython, it primarily uses reference counting to track objects and a Garbage Collector to handle cyclic references. When objects are no longer reachable, their memory can be reclaimed.

</details>
<!------------------------------------>


<details>
  <summary> 58. What is the GIL? </summary>

> **GIL (Global Interpreter Lock)** is a lock in CPython that allows only one thread at a time to execute Python bytecode within a process. <br/>
> Because of this, Python threads don't provide true parallel execution for CPU-bound tasks.

- Applies mainly to CPython.
- Limits CPU-bound multithreading.
- I/O-bound tasks can still benefit from threads.
- For CPU-bound work, multiprocessing can provide true parallelism.

</details>
<!------------------------------------>


<details>
  <summary> 59. Why are lists mutable but tuples immutable? </summary>

> **List → Mutable → Can change**

> **Tuple → Immutable → Cannot change**

```py
lst = [1, 2]
lst[0] = 10      # Allowed

tup = (1, 2)
tup[0] = 10      # TypeError
```

**Lists are designed to allow modification of their elements**, while **_tuples are designed to be fixed after creation_**. This makes tuples safer for constant data and allows them to be hashable (if all their elements are hashable), so they can be used as dictionary keys or set elements.

</details>
<!------------------------------------>


<details>
  <summary> 60. How does dictionary lookup work? </summary>

Python dictionaries use a hash table. When we access `dict[key]`, Python calculates the key's hash using `hash()`, uses it to locate the appropriate position, and then compares keys to find the matching entry.

```py
student = {"name": "Ram", "age": 20}

print(student["name"])   # O(1) average
print(student["age"])    # O(1) average
```

Time complexity:
- Average: O(1)
- Worst case: O(n) due to hash collisions.


</details>
<!------------------------------------>


<details>
  <summary> 61. What happens when you write <code> a = b </code> ? </summary>

```py
b = [1, 2, 3]
a = b

a.append(4)
print(b)   # [1, 2, 3, 4]
print(a)   # [1, 2, 3, 4]
#----------------------------
# Bascially a and b are pointing to same object,
# that means one object, two references
```

</details>
<!------------------------------------>


<details>
  <summary> 62. Difference between iterator and iterable </summary>

> Iterable is an object that can be looped over and provides an iterator using `iter()`.

> Iterator is an object that produces values one at a time using `next()`.

```py
numbers = [1, 2, 3]      # Iterable

itr = iter(numbers)      # Iterator

print(next(itr))         # 1
print(next(itr))         # 2

#----------------------------------------------
# Examples of iterables: list, tuple, string, dict, set.
# Iterable → iter() → Iterator → next() → values

#-----------------------------------------------
number2 = [5, 6, 7]
it = number2.__iter__()
print(it.__next__())
print(it.__next__())
```

</details>
<!------------------------------------>


<details>
  <summary> 63. Generator vs list </summary>

> **A list stores all elements in memory at once**, while **_a generator produces elements one at a time using `yield`_**. Generators are therefore more memory-efficient for large datasets.


| List                | Generator                  |
| ------------------- | -------------------------- |
| Stores all values   | Produces values one by one |
| Higher memory usage | Lower memory usage         |
| Can access by index | No direct indexing         |
| Reusable            | Usually single-use         |
| Eager evaluation    | Lazy evaluation            |

List:
```py
def get_numbers():
    return [1, 2, 3, 4, 5]

numbers = get_numbers()

for num in numbers:
    print(num)
#-----------------------------------------------------
# The entire list is created in memory before the loop starts.
```
Generator:
```py
def get_numbers():
    for i in range(1, 6):
        yield i

numbers = get_numbers()

for num in numbers:
    print(num)
#---------------------------------------------------------
# Here, numbers are generated one at a time as the loop requests them
```

```py
# List
numbers = [x for x in range(1000000)]

#-----------Means-----------------------
numbers = []
for x in range(5):
    numbers.append(x)
#----------------------------------------

# Generator
numbers = (x for x in range(1000000))

#-----------Means-----------------------
def generate():
    for x in range(1, 10):
        yield x

numbers = generate()
print(next(numbers))
```


</details>
<!------------------------------------>


<details>
  <summary> 64. Decorator internals </summary>

> A decorator is a function that takes another function, adds/modifies behavior, and returns a new function.

```py
def decorator(func):
    def wrapper():
        print("Before")
        func()
        print("After")
    return wrapper

@decorator
def greet():
    print("Hello")
#-------------------------------------
# Python internally convert above like below
def greet():
    print("Hello")

greet = decorator(greet)
#--------------------------------------------
# Because wrapper() forms a closure - it remembers func from the outer decorator() function.
```


</details>
<!------------------------------------>


<details>
  <summary> 65. <b> MRO(Method Resolution Order) and multiple inheritance </b> </summary>

**Multiple inheritance** means a class inherits from more than one parent class.

**MRO (Method Resolution Order)** defines the order in which Python searches parent classes for methods and attributes.

Python uses the **C3 linearization algorithm** to determine MRO.
```py
class A:
    def show(self):
        print("A")

class B(A):
    def show(self):
        print("B")

class C(A):
    def show(self):
        print("C")

class D(B, C):
    pass

print(D.mro())  # [<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>]

d = D()   
d.show()  # B
a = A() 
a.show()  # A
```

</details>
<!------------------------------------>


<details>
  <summary> 66. <code> __new__ </code> vs <code> __init__ </code>  </summary>

> **`__new__` creates and returns a new object, while `__init__` initializes that already-created object.**

```py
class Person:

    def __new__(cls):
        print("__new__")
        return super().__new__(cls)

    def __init__(self):
        print("__init__")

p = Person()     # __new__
                 # __init__
#----------------------------------
# When we create an object, __new__()
# and __init__() called automatically
```

Summary :
- **`__new__` > Creates object**
- **`__init__` > Initializes object**
- **`__new__` is a static method-like special method that receives `cls`.**
- **`__init__` receives `self`.**
- **`__new__` is commonly relevant when implementing immutable types or singleton patterns.**


</details>
<!------------------------------------>


<details>
  <summary> 67. Python garbage collection </summary>

<br/>

> **Python automatically manages memory using reference counting and a cyclic garbage collector.** 

> Reference counting removes objects whose reference count reaches zero, while the garbage collector detects and cleans up unreachable reference cycles.

```
Reference Counting → Primary mechanism in CPython.
Cyclic GC → Handles circular references.
gc module → Allows inspecting/managing garbage collection.
gc.collect() → Manually triggers garbage collection.
```
In short : `Unused object → Reference count/GC detects it → Memory is reclaimed`

</details>
<!------------------------------------>


<details>
  <summary> 68. Threading vs multiprocessing </summary>

<br/>

> **Threading uses multiple threads within the same process**, while **_multiprocessing uses separate processes with separate memory spaces_**.

**I/O-bound → Threading** <br/>
**CPU-bound → Multiprocessing**

| Threading                    | Multiprocessing                         |
| ---------------------------- | --------------------------------------- |
| Same process                 | Separate processes                      |
| Shared memory                | Separate memory                         |
| Lightweight                  | More resource-intensive                 |
| Good for **I/O-bound** tasks | Good for **CPU-bound** tasks            |
| Limited by GIL in CPython    | Can bypass GIL using multiple processes |

**GIL - Global Interpreter Lock**


</details>
<!------------------------------------>



<details>
  <summary> 69. Async programming </summary>

> **Async programming allows a program to perform other tasks while waiting for an I/O operation to complete, instead of blocking execution.** 

Python mainly uses `async`, `await`, and the `asyncio` library.

```py
import asyncio

async def task():
    await asyncio.sleep(2)
    print("Done")

asyncio.run(task())
```

`async` → defines asynchronous function
`await` → waits without blocking the event loop
`asyncio` → provides the async framework

Async programming is best for I/O-bound tasks such as API calls, network requests, and database operations.

</details>
<!------------------------------------>

<details>
  <summary> 70. Writing clean, production-quality Python </summary>


**Production-quality Python should be readable, maintainable, testable, efficient, and reliable**.

Key practices:
- Follow PEP 8 and use meaningful names.
- Write small, reusable functions.
- Handle exceptions properly; don't use bare `except`.
- Use type hints where useful.
- Add logging instead of relying on `print()`.
- Write unit/integration tests.
- Avoid duplicated code (DRY).
- Use context managers for resource management.
- Manage dependencies using virtual environments and pinned/controlled versions.
- Use tools like Ruff/Black, mypy, pytest where appropriate.
- Keep configuration and secrets outside the code.

**Clean code focuses on readability and maintainability; production-quality code additionally focuses on reliability, testing, logging, security, performance, and deployment readiness.**

</details>


## The end !

| Complete Python in 70 Question for Interview |
|----------------------------------------------|
