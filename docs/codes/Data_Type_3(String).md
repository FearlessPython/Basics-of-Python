---
mathjax: true
layout: repo-code
comments: true
title: String
permalink: /String/
---

# String

Here we come to the next data type *String*. *String* is a collection of characters which can be alpha-numeric (`A-Z, a-z, 0-9`) as well as special characters (`!, @, $, &, *, ...`) stored within single quotes (`''`) or double quotes (`""`). Strings are **immutable** i.e., any character within the string cannot be altered by some other characters.

## Creation of string (some examples)

Anything stored within the single quotes (`''`) or double quotes (`""`) is represented as a string.


```python
a = "Python"
```


```python
type(a)
```




    str




```python
print(a)
```

    Python
    


```python
b = 'Fearless Python was created in 2020.'
```


```python
type(b)
```




    str




```python
print(b)
```

    Fearless Python was created in 2020.
    

## Length of String

We can calculate the length of a string or the number of characters in it by using Python's built-in function `len()`. 

(Note: We will describe about Python *functions* in the upcoming notebooks).


```python
a = "Python"
len(a)
```




    6



Here the variable `a` contains the string `"Python"` which consists of 6 characters. Similarly,


```python
b = "Fearless Python"
```


```python
len(b)
```




    15



## Indexing in string

In *strings* we have two types of indexing, **forward indexing** and **reverse indexing**. 

*Forward indexing* starts from the first character of the string assigning it an index value of `0` and then moving to the next by incrementing the index by `1`. 

On the other hand *Reverse indexing* starts from the right side i.e., from the last character of the string by assigning it a value `-1`, the immediate next left character gets the index `-2` and it goes on. One can choose any one of the indexing according to their requirement. 

### Forward Indexing


```python
a = "I love Python"
```


```python
a[0]
```




    'I'



See, the first character in the string `a` is `'I'` and it has been indexed as `0`.


```python
a[7]
```




    'P'



### Reverse Indexing


```python
a[-1]
```




    'n'



See, the last character in the string in variable a is `'n'` and it has been indexed as `-1` according to *negative indexing* convention.


```python
a[-10] == a[3]
```




    True




```python
a[-10], a[3]
```




    ('o', 'o')



Here, both the `a[-10]` and `a[3]` indicates the character `'o'` in the string `a`, so when we compared whether they are equal or not we got a boolean value `True`, which means they are equal. I hope you have gone through the notebook where [Boolean](Data_Type_2(Boolean).ipynb) data type was described. 

(Note: `==` is an operator. We will be discussing about operators in the upcoming notebooks. Now for your info, `==` is used to compare two values (may be string or int or float or any types of values) whether they are equal or not. Here we compared two sub-strings `a[-10]` and `a[3]`. Sub-string is just a string which is part of a larger string. Here, both `a[-10]` and `a[3]` is `'o'`, which is part of a string `a`).

### Finding Index of sub-string 

We can get the index of a sub-string or a charecter in a string by using Python's inbuilt `index()` function. It returns the *index of the **first occurence** of the character*.


```python
n = 'Python Physics'
n.index('P')
```




    0



In the previous example we got the first index where `'P'` has occured but we can define the search area to a part of the string to find other occurences as well.


```python
n.index('P', 1)
```




    7



Here we started searching from index `1` so we deliberately missed the `'P'` at index `0` and got the index of the other `'P'` as `7`. Similarly we can specify the end limit of out search by adding another number separated by comma (`,`).


```python
s = 'abbbaccccab'
```


```python
s.index('a', 1, 6)
```




    4



## Index Error

We get this error if we put an index which is greater than the indices present in the string. For Example:


```python
len(a)
```




    13




```python
a[15]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-21-53b5383173f3> in <module>
    ----> 1 a[15]
    

    IndexError: string index out of range


See in the above case we have length of string in variable `a = 15`. So here the indexing will be from `0` to `14`. But when we try to find the character at index `15` we got this `IndexError`.

## Strings are immutable

Strings are **not mutable** i.e., we cannot change any character within the string with some other one. For example,


```python
x = 'Fearless'
```


```python
x[3] = 'h'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-23-a98909048663> in <module>
    ----> 1 x[3] = 'h'
    

    TypeError: 'str' object does not support item assignment


We tried to change the charracter in the index position `3` of the string `'Fearless'` by `'h'` and we got a `TypeError`.

## Slicing in strings

We can create a sub-string from a string by using the *slicing* operation.


```python
a = 'Fearless Python'
b = a[0:8]
```


```python
b
```




    'Fearless'



See we were able to create a sub-string `'Fearless'` from the parent string `'Fearless Python'` by writing the indices. Notice that on the first place we gave `0` which is the index of `'F'` but on the next place we gave `8` which is the index of `' '`. During slicing in python the string is sliced to the index number prior to the end limit so although we have given `8` but it will slice till index `7` and when it reaches index `8` it will stop.

If we will have to slice from the first character only, instead of writing `0` at the first place we can also keep it blank, still Python will understand it as the defaut value = 0. For example:


```python
c = a[:8]
print(c)
```

    Fearless
    

Similarly if we want to slice a string from a position to the end of the string instead of writing the end limit of the string as the length of the string we can put it blank and Python will take the default value as the length of the string. It's shown in the example below.


```python
d = a[9:len(a)]
print(d)
```

    Python
    


```python
e = a[9:]
print(e)
```

    Python
    

We can even slice the string by skipping the characters in a pattern. Suppose we want to create a new string which will have the characters of the old string by skipiing one character in between. Lets see the code.


```python
f = a[::2]
print(f)
```

    Fals yhn
    

See we have kept the first position blank so Python takes a default `0` and the second place is also kept blank so that it takes `len(a)` as default. We have passes a third value i.e., `2` which signifies that we will skip each character one at a time so we get the result `'F'` is chosen but `'e'` is skipped and  we get `'a'` similarly it goes on. You can also try `1, 3, 4, ...` in place of `2` and see what output you get.

### Creating a reverse string

We can create the reverse of a string by the following command:



```python
g = a[: :-1]
print(g)
```

    nohtyP sselraeF
    

See we got the string in the reverse order starting from `'n'` and ending at `'F'`.


```python
h = a[::-2]
h
```




    'nhy slaF'



Here also we were able to reverse the string but here one letter is getting skipped at a time.

## String Concatenation

We can join two strings by using `+` and this method is called *string concatenation*.


```python
a = 'Python'
b = 'Fearless_'
print(a)
print(b)
```

    Python
    Fearless_
    


```python
c = b + a
c
```




    'Fearless_Python'



So we were successfully able to join two strings and store it in a new variable.


```python
x1 = '5'
x2 = '6'
z = x1 + x2
```


```python
z
```




    '56'



Here `'5'` and `'6'` were stored as string, not as numbers so when we used `+` they got concatenated as `'56'`

## Spliting string

We can split a string by using Python's inbuilt `split()` function.


```python
a = 'Python Physics Chemistry'
a.split()
```




    ['Python', 'Physics', 'Chemistry']



We were able to split a string into sub-strings separated by `' '`. Here the separator was `' '` we can even give other seperators like `.`, `,`, `@` etc.


```python
email='fearlesspython@gmail.com'
email.split('@')
```




    ['fearlesspython', 'gmail.com']



## Striping spaces from a string

We can remove all the blank spaces in front and at the end of a string by using inbuilt Python function `strip()`.


```python
a = '   Python    '
print(a)
```

       Python    
    


```python
a
```




    '   Python    '




```python
a = a.strip()
```


```python
a
```




    'Python'



## Some other inbuilt functions in string Data-Type 

We can convert all the characters of a string to *lowercase* by using `string.lower()` function. For Example:


```python
a = 'Python'
a.lower()
```




    'python'



We can convert all the characters of a string to *uppercase* by using `string.upper()` function. For Example:


```python
a.upper()
```




    'PYTHON'



We can make the *first letter of the string uppercase and all the rest characters into lowercase* using `string.capitalize()` function. For Example:


```python
a = "python is an interesTing language."
a.capitalize()
```




    'Python is an interesting language.'



We can make *all the first letters of the word uppercase and the rest letters lower case* using `string.title()` function. For Example:


```python
a.title()
```




    'Python Is An Interesting Language.'



We can *change the case of the all the characters from its original case to its opposite case* by using function `string.swapcase()` function. For Example: 


```python
a.swapcase()
```




    'PYTHON IS AN INTEREStING LANGUAGE.'




```python
b = 'aD'
b.swapcase()
```




    'Ad'



### Checking of type of string

`a = 'ad'` and `b = '567'` both are stored as string datatype but one is an alphabetic string and the other is a digit string. So how can we make a distinction between them. Don't worry. Python has a built-in function for this also. It has a function `isalpha()` to check whether its a alphabetic string or not and also has a `isdigit()` function to check whether the string is a digit string or not. For Example:


```python
a = 'Python'
b = '567'
a.isdigit()
```




    False




```python
a.isalpha()
```




    True




```python
b.isdigit()
```




    True




```python
b.isalpha()
```




    False



Similarly we can check wether a string is in *lowercase* or *uppercase* by using `islower()` and `isupper()` functions.

### Counting number of substring 

We can also count the number of occurence of the sub-string in the string by using `count()` function.


```python
a = 'aaababababa'
a.count('a')
```




    7



There are many more inbuilt functions in the str class of python for working on string datatypes. For more info type `help(str)` and you will get the list of all such functions and a small description.


```python
help(str)
```

    Help on class str in module builtins:
    
    class str(object)
     |  str(object='') -> str
     |  str(bytes_or_buffer[, encoding[, errors]]) -> str
     |  
     |  Create a new string object from the given object. If encoding or
     |  errors is specified, then the object must expose a data buffer
     |  that will be decoded using the given encoding and error handler.
     |  Otherwise, returns the result of object.__str__() (if defined)
     |  or repr(object).
     |  encoding defaults to sys.getdefaultencoding().
     |  errors defaults to 'strict'.
     |  
     |  Methods defined here:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __format__(self, format_spec, /)
     |      Return a formatted version of the string as described by format_spec.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(...)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
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
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __sizeof__(self, /)
     |      Return the size of the string in memory, in bytes.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  capitalize(self, /)
     |      Return a capitalized version of the string.
     |      
     |      More specifically, make the first character have upper case and the rest lower
     |      case.
     |  
     |  casefold(self, /)
     |      Return a version of the string suitable for caseless comparisons.
     |  
     |  center(self, width, fillchar=' ', /)
     |      Return a centered string of length width.
     |      
     |      Padding is done using the specified fill character (default is a space).
     |  
     |  count(...)
     |      S.count(sub[, start[, end]]) -> int
     |      
     |      Return the number of non-overlapping occurrences of substring sub in
     |      string S[start:end].  Optional arguments start and end are
     |      interpreted as in slice notation.
     |  
     |  encode(self, /, encoding='utf-8', errors='strict')
     |      Encode the string using the codec registered for encoding.
     |      
     |      encoding
     |        The encoding in which to encode the string.
     |      errors
     |        The error handling scheme to use for encoding errors.
     |        The default is 'strict' meaning that encoding errors raise a
     |        UnicodeEncodeError.  Other possible values are 'ignore', 'replace' and
     |        'xmlcharrefreplace' as well as any other name registered with
     |        codecs.register_error that can handle UnicodeEncodeErrors.
     |  
     |  endswith(...)
     |      S.endswith(suffix[, start[, end]]) -> bool
     |      
     |      Return True if S ends with the specified suffix, False otherwise.
     |      With optional start, test S beginning at that position.
     |      With optional end, stop comparing S at that position.
     |      suffix can also be a tuple of strings to try.
     |  
     |  expandtabs(self, /, tabsize=8)
     |      Return a copy where all tab characters are expanded using spaces.
     |      
     |      If tabsize is not given, a tab size of 8 characters is assumed.
     |  
     |  find(...)
     |      S.find(sub[, start[, end]]) -> int
     |      
     |      Return the lowest index in S where substring sub is found,
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  format(...)
     |      S.format(*args, **kwargs) -> str
     |      
     |      Return a formatted version of S, using substitutions from args and kwargs.
     |      The substitutions are identified by braces ('{' and '}').
     |  
     |  format_map(...)
     |      S.format_map(mapping) -> str
     |      
     |      Return a formatted version of S, using substitutions from mapping.
     |      The substitutions are identified by braces ('{' and '}').
     |  
     |  index(...)
     |      S.index(sub[, start[, end]]) -> int
     |      
     |      Return the lowest index in S where substring sub is found, 
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Raises ValueError when the substring is not found.
     |  
     |  isalnum(self, /)
     |      Return True if the string is an alpha-numeric string, False otherwise.
     |      
     |      A string is alpha-numeric if all characters in the string are alpha-numeric and
     |      there is at least one character in the string.
     |  
     |  isalpha(self, /)
     |      Return True if the string is an alphabetic string, False otherwise.
     |      
     |      A string is alphabetic if all characters in the string are alphabetic and there
     |      is at least one character in the string.
     |  
     |  isascii(self, /)
     |      Return True if all characters in the string are ASCII, False otherwise.
     |      
     |      ASCII characters have code points in the range U+0000-U+007F.
     |      Empty string is ASCII too.
     |  
     |  isdecimal(self, /)
     |      Return True if the string is a decimal string, False otherwise.
     |      
     |      A string is a decimal string if all characters in the string are decimal and
     |      there is at least one character in the string.
     |  
     |  isdigit(self, /)
     |      Return True if the string is a digit string, False otherwise.
     |      
     |      A string is a digit string if all characters in the string are digits and there
     |      is at least one character in the string.
     |  
     |  isidentifier(self, /)
     |      Return True if the string is a valid Python identifier, False otherwise.
     |      
     |      Use keyword.iskeyword() to test for reserved identifiers such as "def" and
     |      "class".
     |  
     |  islower(self, /)
     |      Return True if the string is a lowercase string, False otherwise.
     |      
     |      A string is lowercase if all cased characters in the string are lowercase and
     |      there is at least one cased character in the string.
     |  
     |  isnumeric(self, /)
     |      Return True if the string is a numeric string, False otherwise.
     |      
     |      A string is numeric if all characters in the string are numeric and there is at
     |      least one character in the string.
     |  
     |  isprintable(self, /)
     |      Return True if the string is printable, False otherwise.
     |      
     |      A string is printable if all of its characters are considered printable in
     |      repr() or if it is empty.
     |  
     |  isspace(self, /)
     |      Return True if the string is a whitespace string, False otherwise.
     |      
     |      A string is whitespace if all characters in the string are whitespace and there
     |      is at least one character in the string.
     |  
     |  istitle(self, /)
     |      Return True if the string is a title-cased string, False otherwise.
     |      
     |      In a title-cased string, upper- and title-case characters may only
     |      follow uncased characters and lowercase characters only cased ones.
     |  
     |  isupper(self, /)
     |      Return True if the string is an uppercase string, False otherwise.
     |      
     |      A string is uppercase if all cased characters in the string are uppercase and
     |      there is at least one cased character in the string.
     |  
     |  join(self, iterable, /)
     |      Concatenate any number of strings.
     |      
     |      The string whose method is called is inserted in between each given string.
     |      The result is returned as a new string.
     |      
     |      Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs'
     |  
     |  ljust(self, width, fillchar=' ', /)
     |      Return a left-justified string of length width.
     |      
     |      Padding is done using the specified fill character (default is a space).
     |  
     |  lower(self, /)
     |      Return a copy of the string converted to lowercase.
     |  
     |  lstrip(self, chars=None, /)
     |      Return a copy of the string with leading whitespace removed.
     |      
     |      If chars is given and not None, remove characters in chars instead.
     |  
     |  partition(self, sep, /)
     |      Partition the string into three parts using the given separator.
     |      
     |      This will search for the separator in the string.  If the separator is found,
     |      returns a 3-tuple containing the part before the separator, the separator
     |      itself, and the part after it.
     |      
     |      If the separator is not found, returns a 3-tuple containing the original string
     |      and two empty strings.
     |  
     |  replace(self, old, new, count=-1, /)
     |      Return a copy with all occurrences of substring old replaced by new.
     |      
     |        count
     |          Maximum number of occurrences to replace.
     |          -1 (the default value) means replace all occurrences.
     |      
     |      If the optional argument count is given, only the first count occurrences are
     |      replaced.
     |  
     |  rfind(...)
     |      S.rfind(sub[, start[, end]]) -> int
     |      
     |      Return the highest index in S where substring sub is found,
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  rindex(...)
     |      S.rindex(sub[, start[, end]]) -> int
     |      
     |      Return the highest index in S where substring sub is found,
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Raises ValueError when the substring is not found.
     |  
     |  rjust(self, width, fillchar=' ', /)
     |      Return a right-justified string of length width.
     |      
     |      Padding is done using the specified fill character (default is a space).
     |  
     |  rpartition(self, sep, /)
     |      Partition the string into three parts using the given separator.
     |      
     |      This will search for the separator in the string, starting at the end. If
     |      the separator is found, returns a 3-tuple containing the part before the
     |      separator, the separator itself, and the part after it.
     |      
     |      If the separator is not found, returns a 3-tuple containing two empty strings
     |      and the original string.
     |  
     |  rsplit(self, /, sep=None, maxsplit=-1)
     |      Return a list of the words in the string, using sep as the delimiter string.
     |      
     |        sep
     |          The delimiter according which to split the string.
     |          None (the default value) means split according to any whitespace,
     |          and discard empty strings from the result.
     |        maxsplit
     |          Maximum number of splits to do.
     |          -1 (the default value) means no limit.
     |      
     |      Splits are done starting at the end of the string and working to the front.
     |  
     |  rstrip(self, chars=None, /)
     |      Return a copy of the string with trailing whitespace removed.
     |      
     |      If chars is given and not None, remove characters in chars instead.
     |  
     |  split(self, /, sep=None, maxsplit=-1)
     |      Return a list of the words in the string, using sep as the delimiter string.
     |      
     |      sep
     |        The delimiter according which to split the string.
     |        None (the default value) means split according to any whitespace,
     |        and discard empty strings from the result.
     |      maxsplit
     |        Maximum number of splits to do.
     |        -1 (the default value) means no limit.
     |  
     |  splitlines(self, /, keepends=False)
     |      Return a list of the lines in the string, breaking at line boundaries.
     |      
     |      Line breaks are not included in the resulting list unless keepends is given and
     |      true.
     |  
     |  startswith(...)
     |      S.startswith(prefix[, start[, end]]) -> bool
     |      
     |      Return True if S starts with the specified prefix, False otherwise.
     |      With optional start, test S beginning at that position.
     |      With optional end, stop comparing S at that position.
     |      prefix can also be a tuple of strings to try.
     |  
     |  strip(self, chars=None, /)
     |      Return a copy of the string with leading and trailing whitespace remove.
     |      
     |      If chars is given and not None, remove characters in chars instead.
     |  
     |  swapcase(self, /)
     |      Convert uppercase characters to lowercase and lowercase characters to uppercase.
     |  
     |  title(self, /)
     |      Return a version of the string where each word is titlecased.
     |      
     |      More specifically, words start with uppercased characters and all remaining
     |      cased characters have lower case.
     |  
     |  translate(self, table, /)
     |      Replace each character in the string using the given translation table.
     |      
     |        table
     |          Translation table, which must be a mapping of Unicode ordinals to
     |          Unicode ordinals, strings, or None.
     |      
     |      The table must implement lookup/indexing via __getitem__, for instance a
     |      dictionary or list.  If this operation raises LookupError, the character is
     |      left untouched.  Characters mapped to None are deleted.
     |  
     |  upper(self, /)
     |      Return a copy of the string converted to uppercase.
     |  
     |  zfill(self, width, /)
     |      Pad a numeric string with zeros on the left, to fill a field of the given width.
     |      
     |      The string is never truncated.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  maketrans(x, y=None, z=None, /)
     |      Return a translation table usable for str.translate().
     |      
     |      If there is only one argument, it must be a dictionary mapping Unicode
     |      ordinals (integers) or characters to Unicode ordinals, strings or None.
     |      Character keys will be then converted to ordinals.
     |      If there are two arguments, they must be strings of equal length, and
     |      in the resulting dictionary, each character in x will be mapped to the
     |      character at the same position in y. If there is a third argument, it
     |      must be a string, whose characters will be mapped to None in the result.
    
    

With this we come to the end of our string data-type.
