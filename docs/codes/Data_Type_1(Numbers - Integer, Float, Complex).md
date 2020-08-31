---
mathjax: true
layout: repo-code
comments: true
title:
---

# Numbers - Integer, Float, Complex
 
Before learning about the integer, float, complex data-type, we will first learn something about variables.
 
## Variable
 
### What is a variable ?
 
A **variable** is that which stores values in a fixed memory location. The value may change dynamically. Whenever we accesse that variable, it returns the present value stored.

### Assignment of values to variables :

1. Assignment of values to a variable requires the `=` operator. The variable will be at the left side and the value will be at the right side. Reverse  will lead to an error (`SyntaxError`). Remember that in mathematics, `=` sign is used in equations where both sides of an equation are same. But in Python (and many other programming languages), it is an *assignment* operator. It just assigns a value to a variable name. *E.g:* In Mathematics,

$$
\begin{align*}
x &= 10 \\
x &= x + 1 
\end{align*}
$$

The last equation is not valid, because actually, $x \ne x + 1$. But, in Python,

$$
\begin{align*}
x &= 10 \\
x &= x + 1
\end{align*}
$$

Everything is valid here (and these are not equations). We are just assigning a value at each line. Python is an *interpreted* language, which means, Python executed code line by line. In the first line, `x` is assigned the value of integer `10`. In the next line, the new value of `x` is overwritten and assigned to 11 (See it as $x = 10+1$). (Whereas there are some language, like C++, which are *compiler* language, where whole block of code is executed, rather than line by line execution).

2. Single variable can take different values at different points of the program. The present value of variable will be the last assigned value. As seen in the above example, the old value of `x` (10) was overwritten by the new value (11), and the old value is lost.

3. We can't use any python reserved *keywords* as a variables, as it will lead to an error. And one more important thing, in case of assigning variable there is no problem in spacing. To see the reserved  Python *keywords*, type `help('keywords')` in python shell/interpreter and press enter. If you are in a text editor, type `print(help('keywords'))` and run the program to view all the keywords. This can also be done in shell/interpreter also.

4. Variable names can't start with any digit but digit can be anywhere in middle or last. Python is *case-sensitive*, which means **a** and **A** are not the same variable name. They are assigned different values as they have different memory places in python. In case of special characters (`!@#$%^&*_`), only underscore (`_`) can be used in a variable name.

Let us see few examples of defining variables.


```python
a = 4
```

The variable name **a** is assigned to the integer value 4. Now, to print the output of a defined variable, we simply need to write `print(a)`. `print()` is an inbuilt Python function.


```python
print(a)
```

    4
    


```python
print(id(a))
```

    2053989520
    

`id()` is again an inbuilt Python function which tells us the unique identity of any Python object (in this case, integer 4). Your computer identifies every object as a unique id, which is stored in your computer's memory. The unique id of any object will vary from computer to computer, and will vary each time you run a program (except for the integer values of -5 to 256). 


```python
a = 5
```


```python
print(a)
```

    5
    

See here the memory location changes after a is assigned to new value.


```python
print(id(a))
```

    2053989536
    


```python
print(id(10))
```

    2053989616
    


```python
print(id(10))
```

    2053989616
    

The unique id of 10 is same both the times. But it may change if we quit the program and start again fresh. But in the next trials also, both will be same.


```python
print(id(256))
```

    2053993552
    


```python
print(id(256))
```

    2053993552
    


```python
print(id(-5))
```

    2053989376
    


```python
print(id(-5))
```

    2053989376
    


```python
print(id(257))
```

    96624080
    


```python
print(id(257))
```

    96624128
    


```python
print(id(-6))
```

    96623568
    


```python
print(id(-6))
```

    96624016
    

Have you understood, that only integers -5 to 256 outputs same unique id during a program. Rest integers and data type (strings, list etc) changes their value dynamically each time even within executing a single program.

Can we assign `3` to `x`?


```python
3 = x
```


      File "<ipython-input-17-97d1cbcfdbdb>", line 1
        3 = x
             ^
    SyntaxError: can't assign to literal
    


`SyntaxError` is raised. You cannot assign `3` to `x`. `3` is `3` forever. `3` cannot become `x` or `4`. But the reverse is true.


```python
x = 3
print(x)
```

    3
    

### Reserved Python keywords can't be used as variable name

We already mentioned above how to view the Python reserved keywords.


```python
help('keywords')
```

    
    Here is a list of the Python keywords.  Enter any keyword to get more help.
    
    False               class               from                or
    None                continue            global              pass
    True                def                 if                  raise
    and                 del                 import              return
    as                  elif                in                  try
    assert              else                is                  while
    async               except              lambda              with
    await               finally             nonlocal            yield
    break               for                 not                 
    
    

Using reserved keywords as a variable name leads to a `SyntaxError` again.


```python
in = 42
```


      File "<ipython-input-20-393d143aec0c>", line 1
        in = 42
         ^
    SyntaxError: invalid syntax
    



```python
for = 64
```


      File "<ipython-input-21-d0d0539eac4a>", line 1
        for = 64
            ^
    SyntaxError: invalid syntax
    


### Using consistent writing style for better readability

You can include any spaces between variable name and equals (`=`) sign. You can also include any number of spaces between equals (`=`) and the value of the variable.


```python
y                    =    3
print(y)
```

    3
    

But it is recommended officially by [Python Software Foundation](https://www.python.org/psf/) to include only one whitespace between variable name, equals sign (`=`), and the variable value. So ideally, you should write `y = 3`. It is not wrong to include more spaces or less spaces, your code will still execute, but readability of your code is hampered. A code is read more than it is written. Other programmers who will look at your code will be not in ease if they look up your uneven written code. Well, there are lot more guidelines (called [PEP 8](https://www.python.org/dev/peps/pep-0008/)) for styling your code, written on the official Python website.

But never include whitespace before the variable name. It will lead to an error. You will learn later that sometimes you have to intentionally include spaces (2 spaces/4 spaces/Tab) before starting your code in a new line. But don't do it now.


```python
           x    =     3
    print(x)
```


      File "<ipython-input-23-45af53bd6a86>", line 2
        print(x)
        ^
    IndentationError: unexpected indent
    


### Line breaks in Python

Have you noticed one thing till now? How do Python known when you start a new line? In many other programming languages (*e.g*: JavaScript, C, Java), we have to enter a semi-colon (`;`) whenever we end a line. Not doing this will lead to a `SyntaxError` in those programming language. But why no `SyntaxError` in Python? Let's try something again, with and without semi-colon (`;`).


```python
Bones = 206
print(Bones)
```

    206
    

It worked. Why won't it work? All the way till now, we were doing this only, i.e., not using any semi-colon (`;`).

Will Python raise any error if we try now with a semi-colon (`;`)?


```python
Muscles = 640;
print(Muscles);
```

    640
    

Wohoo! It worked. Actually, Python is a little smart. It understands line-break as humans understand, just by hitting *Enter*. But other mentioned programming language cannot figure out line-break until and unless semi-colon (`;`) is given. So, giving a semi-colon (`;`) for line-break is optional in Python.

But you can do some shortcut things. Because Python will understand (`;`) as a line-break, then you don't need to provide an actual line-break at all.


```python
Teeth = 32; print(Teeth)
```

    32
    

Trying this without a semi-colon (`;`) will definitely lead to an error.


```python
Fingers = 10 print(Fingers)
```


      File "<ipython-input-27-4a57ab8de86c>", line 1
        Fingers = 10 print(Fingers)
                         ^
    SyntaxError: invalid syntax
    


You should have understood now what we meant.

### Valid and Invalid variable names

#### Valid variable names


```python
a1 = 5; a2 = 7 # There can be digit in the variable name, but not at the starting of the variable name
```


```python
print(a1)
```

    5
    


```python
print(a2)
```

    7
    


```python
Kaprekar_const = 6174 # We can use the special character _
print(Kaprekar_const)
```

    6174
    


```python
_num = 99 # We can use underscore _ also at the start of the variable name
print(_num)
```

    99
    

#### Invalid variable names


```python
Hardy-Ramanujan-number = 1729 # We cannot use other special characters ! @ # $ % ^ & * ( ) + = - /
print(Hardy-Ramanujan-number)
```


      File "<ipython-input-33-d1396092b870>", line 1
        Hardy-Ramanujan-number = 1729 # We cannot use other special characters ! @ # $ % ^ & * ( ) + = - /
                                                                                                          ^
    SyntaxError: can't assign to operator
    


Some more invalid variable names below.


```python
C@rs = 3
print(C@rs)
```


      File "<ipython-input-34-2ea4e3761f6b>", line 1
        C@rs = 3
                ^
    SyntaxError: can't assign to operator
    



```python
2num = 10    # There can be digit in the variable name, but not at the starting of the variable name
print(2num)
```


```python
MyPhone# = 2067093400 
print(MyPhone#) # Haha! Everything become comment after the special character #
```


      File "<ipython-input-35-9bff3c4ad731>", line 2
        print(MyPhone#) # Haha! Everything become comment after the special character #
                                                                                       ^
    SyntaxError: unexpected EOF while parsing
    


We learnt enough about the variable names. Now start with Python Data-Types.

## Python data-types

**In this part we are going to learn about the  python data types.**

Python has *primarily* these data types which are listed below:
1. Number (Integer, Float, Complex)
2. String
3. List
4. Tuple
5. Dictionary
6. Set

Apart from these, there are also other data-types like functions, classes, other objects etc.

 ## Numbers
 
 **Let's start with Python Numbers.**

Python has three types of Numbers. 

1. Integer $\longrightarrow$ -25, -10, -1, 0, 1, 255, 1024, ...
2. Float (Decimal Numbers) $\longrightarrow$ -25.56, -10.0, 0.99999999, 3.14159, 1000.0001
3. Complex Numbers $\longrightarrow$ $1 + 2i$, $6 - i$, $2i$, $13 + 5i$ (In Python, $j$ is used instead of $i$).

All the numbers are converted to the nearest binary numbers by the Python interpreter. Types of numbers differ only via assiging the correct values. Actually, Python deals with integer numbers, decimal numbers (floating point numbers) and complex numbers. No predeclaration of data type is required in Python. Whereas in other programming languages (like FORTRAN, C etc), you have to declare before defining a variable, that whether the variable is going to be assigned to an integer, or a float, or a complex number, or any other data-type. E.g., in C,
```
int a = 10, b = 20;
float f = 23.334;

```

Whereas in Python,
```
a = 10; b = 20; f = 23.334 
```


So, Python reduces our hard-work during declaring variables.

It should be kept in mind that in Python the data type of a variable is dynamically assigned. If a variable is assigned an integer value, and then undergone a float operation, then the data type of that variable is dynamically changed to a float.

### 1. Integer

**Integer** is the number without decimal point. In Python code we use `int()` to convert any variables to integer number (We should know that complex number can't directly be converted to integer we will discuss it in this part).

In case of conversion from decimal(float) to integer number python returns the nearest smaller integer number. 


```python
a = 2.718 # Here x is assigned with a float number
print(int(a))
```

    2
    

Using `abs()` we can get the absolute value of any number.


```python
b = -41
print(abs(b))
```

    41
    

Here we will learn to convert from decimal number to other number system. One thing to keep in mind is that here decimal stands for only the integer numbers with base-10 in number system.


```python
i = 17
print(type(i))   # checking the data-type using inbuilt Python type() function
```

    <class 'int'>
    

Python itself showed us that data-type of `i` is integer.


```python
print(bin(i))   # printing binary number of i using bin() function
```

    0b10001
    

The prefix `0b` represents that the result is a binary string. Hence Binary of 17 is 10001.

$$
\begin{align*}
(10001)_{2} &= (1 \times 2^{4}) + (0 \times 2^{3}) + (0 \times 2^{2}) + (0 \times 2^{1}) + (1 \times 2^{0}) \\
(10001)_{2} &= 16 + 0 + 0 + 0 + 1 \\
(10001)_{2} &= (17)_{10}
\end{align*}
$$


```python
print(i.bit_length())   # checking the bit length, i.e,. the number of binary digits (10001 --> 5 digits)
```

    5
    


```python
print(oct(i))    # converting to octal number using oct() function
```

    0o21
    

The prefix `0o` represents that the result is an octal string. Hence Octal of 17 is 21.

$$
\begin{align*}
(21)_{8} &= (2 \times 8^{1}) + (1 \times 8^{0}) \\
(21)_{8} &= 16 + 1 \\
(21)_{8} &= (17)_{10}
\end{align*}
$$


```python
print(hex(i))   # converting to Hexadecimal number using hex() function
```

    0x11
    

The prefix `0x` represents that the result is a Hexadecimal string. Hence the Hexadecimal of 17 is 11.

$$
\begin{align*}
(11)_{16} &= (1 \times 16^{1}) + (1 \times 16^{0}) \\
(11)_{16} &= 16 + 1\\
(11)_{16} &= (17)_{10}
\end{align*}
$$

### 2. Float

**Float** or Decimal numbers do have decimal point. They can be represented in two ways.

#### (i) Fractional form 


```python
x = 3.453 # i.e., 3543/1000
print(x)
```

    3.453
    


```python
print(type(x)) # checking the data-type by using type() function
```

    <class 'float'>
    

#### (ii) Exponential Form


```python
y = -8.025e112 # i.e., -8.025 * 10^(112)
print(y)
print(type(y))
```

    -8.025e+112
    <class 'float'>
    


```python
z = 2.5e-12
print(z)
print(type(z))
```

    2.5e-12
    <class 'float'>
    


```python
float.fromhex('0x1.ffffp10') # number taken from hexadecimal number 
```




    2047.984375




```python
float.fromhex('-0x1p-1074')
```




    -5e-324



Python built in function `float ()` is used to convert any other variable to float point number. 

The range of float numbers (positive and negative) is extended from **1.7976931348623157e+308** to **4.9406564584124654e-324**.


```python
print(1e308)
```

    1e+308
    


```python
print(1.7976931348623157e+308)
```

    1.7976931348623157e+308
    


```python
print(1e309) # exceed the upper boundary 
```

    inf
    


```python
print(4.9406564584124654e-324)
```

    5e-324
    


```python
print(0.5e-324) # exceed the lower boundary 
```

    0.0
    

#### Underflow and Overflow of decimal numbers

 In the previous example, it is found that, above a certain value of a decimal number, the number computationally becomes infinity. This is the overflow of a decimal number. It is also observed that a decimal number computationally becomes zero below certain value. That point is denoted as the underflow of decimal numbers. 
 
 Any decimal number can't be exactly converted to binary numbers by the interpreter. That's why we never get the exact value of a decimal number.


```python
print(0.1 + 0.2)
```

    0.30000000000000004
    

### 3. Complex

 In complex number usally there is a real part as well as an imaginary part. Here any real number with $j$ is called imaginary part.

Let's see an example.


```python
s = 2 + 3j
print(s)
```

    (2+3j)
    


```python
print(type(s)) # checking the data type
```

    <class 'complex'>
    

## We can use the following process to assign a complex number


```python
r1 = 3; r2 = 5
com = complex(r1, r2) # here r1 is used as real and r2 is used as imaginary part.
print(com)
```

    (3+5j)
    


```python
print(type(com)) # checking the data type
```

    <class 'complex'>
    


```python
print(com.conjugate()) # conjugate of the complex number
```

    (3-5j)
    

**We can use another method as follows.**


```python
k = 6.23 + 45.2j
print(complex.conjugate(k))
```

    (6.23-45.2j)
    


```python
t = complex(5, 9.5)
tc = t.conjugate()
print(tc)
```

    (5-9.5j)
    


```python
real_tc = tc.real # real part of the complex number assigned to tc
print(real_tc)
```

    5.0
    


```python
print(type(real_tc))
```

    <class 'float'>
    


```python
img_tc = tc.imag # imaginary part of the complex number assigned to tc
print(img_tc)
```

    -9.5
    

***For further details on Python data-types we can use the help() function as shown.***


```python
help(int)
help(float)
help(complex)
```

    Help on class int in module builtins:
    
    class int(object)
     |  int([x]) -> integer
     |  int(x, base=10) -> integer
     |  
     |  Convert a number or string to an integer, or return 0 if no arguments
     |  are given.  If x is a number, return x.__int__().  For floating point
     |  numbers, this truncates towards zero.
     |  
     |  If x is not a number or if base is given, then x must be a string,
     |  bytes, or bytearray instance representing an integer literal in the
     |  given base.  The literal can be preceded by '+' or '-' and be surrounded
     |  by whitespace.  The base defaults to 10.  Valid bases are 0 and 2-36.
     |  Base 0 means to interpret the base from the string as an integer literal.
     |  >>> int('0b100', base=0)
     |  4
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __and__(self, value, /)
     |      Return self&value.
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __ceil__(...)
     |      Ceiling of an Integral returns itself.
     |  
     |  __divmod__(self, value, /)
     |      Return divmod(self, value).
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __float__(self, /)
     |      float(self)
     |  
     |  __floor__(...)
     |      Flooring an Integral returns itself.
     |  
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(self, format_spec, /)
     |      Default object formatter.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __index__(self, /)
     |      Return self converted to an integer, if self is suitable for use as an index into a list.
     |  
     |  __int__(self, /)
     |      int(self)
     |  
     |  __invert__(self, /)
     |      ~self
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lshift__(self, value, /)
     |      Return self<<value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __neg__(self, /)
     |      -self
     |  
     |  __or__(self, value, /)
     |      Return self|value.
     |  
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
     |  
     |  __rand__(self, value, /)
     |      Return value&self.
     |  
     |  __rdivmod__(self, value, /)
     |      Return divmod(value, self).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rfloordiv__(self, value, /)
     |      Return value//self.
     |  
     |  __rlshift__(self, value, /)
     |      Return value<<self.
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __ror__(self, value, /)
     |      Return value|self.
     |  
     |  __round__(...)
     |      Rounding an Integral returns itself.
     |      Rounding with an ndigits argument also returns an integer.
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rrshift__(self, value, /)
     |      Return value>>self.
     |  
     |  __rshift__(self, value, /)
     |      Return self>>value.
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __rxor__(self, value, /)
     |      Return value^self.
     |  
     |  __sizeof__(self, /)
     |      Returns size in memory, in bytes.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  __trunc__(...)
     |      Truncating an Integral returns itself.
     |  
     |  __xor__(self, value, /)
     |      Return self^value.
     |  
     |  bit_length(self, /)
     |      Number of bits necessary to represent self in binary.
     |      
     |      >>> bin(37)
     |      '0b100101'
     |      >>> (37).bit_length()
     |      6
     |  
     |  conjugate(...)
     |      Returns self, the complex conjugate of any int.
     |  
     |  to_bytes(self, /, length, byteorder, *, signed=False)
     |      Return an array of bytes representing an integer.
     |      
     |      length
     |        Length of bytes object to use.  An OverflowError is raised if the
     |        integer is not representable with the given number of bytes.
     |      byteorder
     |        The byte order used to represent the integer.  If byteorder is 'big',
     |        the most significant byte is at the beginning of the byte array.  If
     |        byteorder is 'little', the most significant byte is at the end of the
     |        byte array.  To request the native byte order of the host system, use
     |        `sys.byteorder' as the byte order value.
     |      signed
     |        Determines whether two's complement is used to represent the integer.
     |        If signed is False and a negative integer is given, an OverflowError
     |        is raised.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  from_bytes(bytes, byteorder, *, signed=False) from builtins.type
     |      Return the integer represented by the given array of bytes.
     |      
     |      bytes
     |        Holds the array of bytes to convert.  The argument must either
     |        support the buffer protocol or be an iterable object producing bytes.
     |        Bytes and bytearray are examples of built-in objects that support the
     |        buffer protocol.
     |      byteorder
     |        The byte order used to represent the integer.  If byteorder is 'big',
     |        the most significant byte is at the beginning of the byte array.  If
     |        byteorder is 'little', the most significant byte is at the end of the
     |        byte array.  To request the native byte order of the host system, use
     |        `sys.byteorder' as the byte order value.
     |      signed
     |        Indicates whether two's complement is used to represent the integer.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  denominator
     |      the denominator of a rational number in lowest terms
     |  
     |  imag
     |      the imaginary part of a complex number
     |  
     |  numerator
     |      the numerator of a rational number in lowest terms
     |  
     |  real
     |      the real part of a complex number
    
    Help on class float in module builtins:
    
    class float(object)
     |  float(x=0, /)
     |  
     |  Convert a string or number to a floating point number, if possible.
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __divmod__(self, value, /)
     |      Return divmod(self, value).
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __float__(self, /)
     |      float(self)
     |  
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(self, format_spec, /)
     |      Formats the float according to format_spec.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __int__(self, /)
     |      int(self)
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __neg__(self, /)
     |      -self
     |  
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
     |  
     |  __rdivmod__(self, value, /)
     |      Return divmod(value, self).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rfloordiv__(self, value, /)
     |      Return value//self.
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __round__(self, ndigits=None, /)
     |      Return the Integral closest to x, rounding half toward even.
     |      
     |      When an argument is passed, work like built-in round(x, ndigits).
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  __trunc__(self, /)
     |      Return the Integral closest to x between 0 and x.
     |  
     |  as_integer_ratio(self, /)
     |      Return integer ratio.
     |      
     |      Return a pair of integers, whose ratio is exactly equal to the original float
     |      and with a positive denominator.
     |      
     |      Raise OverflowError on infinities and a ValueError on NaNs.
     |      
     |      >>> (10.0).as_integer_ratio()
     |      (10, 1)
     |      >>> (0.0).as_integer_ratio()
     |      (0, 1)
     |      >>> (-.25).as_integer_ratio()
     |      (-1, 4)
     |  
     |  conjugate(self, /)
     |      Return self, the complex conjugate of any float.
     |  
     |  hex(self, /)
     |      Return a hexadecimal representation of a floating-point number.
     |      
     |      >>> (-0.1).hex()
     |      '-0x1.999999999999ap-4'
     |      >>> 3.14159.hex()
     |      '0x1.921f9f01b866ep+1'
     |  
     |  is_integer(self, /)
     |      Return True if the float is an integer.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  __getformat__(typestr, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      This function returns whichever of 'unknown', 'IEEE, big-endian' or 'IEEE,
     |      little-endian' best describes the format of floating point numbers used by the
     |      C type named by typestr.
     |  
     |  __set_format__(typestr, fmt, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |        fmt
     |          Must be one of 'unknown', 'IEEE, big-endian' or 'IEEE, little-endian',
     |          and in addition can only be one of the latter two if it appears to
     |          match the underlying C reality.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      Override the automatic determination of C-level floating point type.
     |      This affects how floats are converted to and from binary strings.
     |  
     |  fromhex(string, /) from builtins.type
     |      Create a floating-point number from a hexadecimal string.
     |      
     |      >>> float.fromhex('0x1.ffffp10')
     |      2047.984375
     |      >>> float.fromhex('-0x1p-1074')
     |      -5e-324
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  imag
     |      the imaginary part of a complex number
     |  
     |  real
     |      the real part of a complex number
    
    Help on class complex in module builtins:
    
    class complex(object)
     |  complex(real=0, imag=0)
     |  
     |  Create a complex number from a real part and an optional imaginary part.
     |  
     |  This is equivalent to (real + imag*1j) where imag defaults to 0.
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __divmod__(self, value, /)
     |      Return divmod(self, value).
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __float__(self, /)
     |      float(self)
     |  
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(...)
     |      complex.__format__() -> str
     |      
     |      Convert to a string according to format_spec.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(...)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __int__(self, /)
     |      int(self)
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __neg__(self, /)
     |      -self
     |  
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
     |  
     |  __rdivmod__(self, value, /)
     |      Return divmod(value, self).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rfloordiv__(self, value, /)
     |      Return value//self.
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  conjugate(...)
     |      complex.conjugate() -> complex
     |      
     |      Return the complex conjugate of its argument. (3-4j).conjugate() == 3+4j.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  imag
     |      the imaginary part of a complex number
     |  
     |  real
     |      the real part of a complex number
    
    
