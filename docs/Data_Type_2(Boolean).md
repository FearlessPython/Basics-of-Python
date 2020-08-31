---
mathjax: true
layout: repo-code
title:
---

# Boolean

The boolean data-type is either `True` or `False`, which are both reserved keywords in Python. In Python, any variable can be assigned to a boolean using `True` and `False` keywords. After assigning any variable to a boolean, we can check its data-type using inbuilt Python `type()` function.


```python
B1 = True
type(B1)
```




    bool




```python
B2 = False
type(B2)
```




    bool



Note that you cannot use `true` or `false`. Python is a case-sensitive language. So using `true` instead of `True` will lead to an error (`NameError`).


```python
a = true # In keyword it is not true but it is True. Similar case for False
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-3-d816aeb5cbe5> in <module>
    ----> 1 a = true # In keyword it is not true but it is True. Similar case for False
    

    NameError: name 'true' is not defined


## Integer and float as booleans

Using Python's inbuilt `bool()` function one can convert any numbers to boolean data type. An integer, float or complex number set to *zero* returns `False`,  while the same if set to any other number, irrespective of positive or negative value, returns `True`. 


```python
bool(5)
```




    True




```python
bool(0)
```




    False




```python
bool(4 + 5j)
```




    True




```python
bool(-2.156)
```




    True




```python
bool(0.000000)
```




    False



## String as booleans
The thing which we did above with numbers, can similarly applied with strings. Strings are anything within the inverted commas(`""`). If there are some characters inside the string (including space), then the equivalent boolean value will be `True`. In the other hand, if there are no characters in the string (empty string), then the equivalent boolean value will be `False`.


```python
bool("You are on Fearless Python.")
```




    True




```python
bool("   ") # Spaces inserted in the inverted commas as a string
```




    True




```python
bool("These are special characters: !@#$%^&*-_+=/")
```




    True




```python
bool("") # Nothing is inside the inverted commas (empty string)
```




    False



This concept is famously called as **Truthy** and **Falsy**. This is also used widely in `if` `else` statements, which you will learn soon.

## Boolean operators in python include-  and , or , not
We also use `==` (equivalent) `!=` (not equivalent) operators.


```python
A = True
```


```python
a = False
```


```python
not A
```




    False




```python
not a
```




    True




```python
A == a
```




    False




```python
A != a
```




    True



### Few more examples are shown bellow.


```python
s = 1; t = 3
```


```python
s > t   # i.e., checking s is greater than t
```




    False




```python
s = 4; t = 4
s < t     # i.e. checking s is less than t
```




    False




```python
s == t
```




    True




```python
s <= t    # i.e. checking s is less than equalto t
```




    True



If any one of the operation is *true* , returns `True`.


```python
s >= t # i.e. checking s is greater than equal to t
```




    True



**For further details on Python data-types we can use the inbuilt `help()` function.**


```python
help(bool())
```

    Help on bool object:
    
    class bool(int)
     |  bool(x) -> bool
     |  
     |  Returns True when the argument x is true, False otherwise.
     |  The builtins True and False are the only two instances of the class bool.
     |  The class bool is a subclass of the class int, and cannot be subclassed.
     |  
     |  Method resolution order:
     |      bool
     |      int
     |      object
     |  
     |  Methods defined here:
     |  
     |  __and__(self, value, /)
     |      Return self&value.
     |  
     |  __or__(self, value, /)
     |      Return self|value.
     |  
     |  __rand__(self, value, /)
     |      Return value&self.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __ror__(self, value, /)
     |      Return value|self.
     |  
     |  __rxor__(self, value, /)
     |      Return value^self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __xor__(self, value, /)
     |      Return self^value.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from int:
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
     |  __sizeof__(self, /)
     |      Returns size in memory, in bytes.
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
     |  Class methods inherited from int:
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
     |  Data descriptors inherited from int:
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
    
    
