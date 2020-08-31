---
mathjax: true
layout: repo-code
title:
---

# Set

**Set** is an inbuilt python data-type, in which many elements can be stored. As in **Dictionary**, the ordering of elements in a *Set* do not matter. You can assign any variable to a *set* using curly braces `{}`, and separating the elements using comma `,`.


```python
a = {'value1', 'value2', 'value3'}
```

The *set* is now created and stored in the variable **a**. You can now print the *set* by using `print(a)`.


```python
print(a)
```

    {'value2', 'value1', 'value3'}
    

Did you see it? The ordering does not matter. They are unordered. Elements can be arranged randomly within a *set*.

Let's now check what python calls a *set* by using the `type()` function.


```python
print(type(a)) # prints the type of data of a
```

    <class 'set'>
    

As expected, python identifies a *Set* by `set`. So, `set` is a reserved keyword in Python, like `dict`, `int`, `str`, `float` etc.

We can print the length of a set using `len()` function.


```python
print(len(a))
```

    3
    

Nothing new here. It's all as expected.

Let's create an empty set using the curly braces `{}`.


```python
empty_set = {}
```

Let's check the type of `empty_set`.


```python
print(type(empty_set))
```

    <class 'dict'>
    

Woah! It was not an empty set. It is an empty dictionary. So, can we create empty set at all in Python?

The answer is **Yes**. But it's not as usual other empty data-types are created like *string*(`''`), *list*(`[]`), *dictionary*(`{}`) etc. It's a little bit tricky.

Not that much tricky as you are thinking. Just use `set()` without any arguments.


```python
empty_set = set()
print(type(empty_set))
```

    <class 'set'>
    

Yes! Now the things are going well.

Now, what are the accepted data-types in *Sets*? **A *Set* can only have *immutable* data-types**, like *strings*, *tuples*, *numbers* (*integers*, *floats*, *complex*) or *boolean*. **A *Set* cannot have *mutable* data-types** within it, like, *lists*, *dictionaries*, or other *sets*. So, a *Set* **cannot** be inserted within another *Set*. And a *set* can cantain *mixed* data-types as shown below.


```python
# A valid Set
set1 = {1, 2, 3, 4, 5} # All same data-types, i.e., integers
print(set1)
```

    {1, 2, 3, 4, 5}
    


```python
# Another valid Set
set2 = {1, 'Two', 3.0, 4+1j, ('I', 'like', 'Python')} # Mixed data-types, i.e., integer, string, float, complex, tuple.
print(set2)
```

    {1, 3.0, 'Two', (4+1j), ('I', 'like', 'Python')}
    


```python
# An invalid Set
set3 = {1, 2, ['Python', 'Ruby', 'JavaScript', 'C++'], {'Apples': 2, 'Banana': 6}}
print(set3)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-10-3b4153ab32db> in <module>
          1 # An invalid Set
    ----> 2 set3 = {1, 2, ['Python', 'Ruby', 'JavaScript', 'C++'], {'Apples': 2, 'Banana': 6}}
          3 print(set3)
    

    TypeError: unhashable type: 'list'


`TypeError` is raised, because **mutable** data-types were inserted in the *Set*.


```python
# Another invalid Set
set4 = {'Mathematics', set1, set2, 'Physics'} # set1 and set2 are being supplied within set4
print(set4)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-11-f8d4a944f9cf> in <module>
          1 # Another invalid Set
    ----> 2 set4 = {'Mathematics', set1, set2, 'Physics'} # set1 and set2 are being supplied within set4
          3 print(set4)
    

    TypeError: unhashable type: 'set'


As expected, a *Set* cannot be in another *Set*.

### Using variables in Set

Suppose we declare some variables below.


```python
Veg_foods = ('Pulses', 'Nuts', 'Grains', 'Vegetables') # Tuple
Fruits = ('Orange', 'Apple') # Tuple

# Set containing variables Veg_foods and Non_Veg_foods
My_diet = {Veg_foods, Fruits}
```

What should be the outcome if we print `My_diet`. Will it be printed with the variable names, or with the data that is stored in that variable names?


```python
print(My_diet)
```

    {('Pulses', 'Nuts', 'Grains', 'Vegetables'), ('Orange', 'Apple')}
    

You must have understood by now what we meant to say.

### Is Set mutable or immutable?

We said sometime ago that a *Set* cannot contain *mutable* data-types. A *Set* also cannot contain another *Set*. That means, *Set* must be *mutable*. And it's true. They are *mutable*.

But how to *add* or *remove* data in a *Set*. First let's see the methods to **Add** elements. Since ordering does not matter in *Sets*, so there is no question of *indexing*. So, `My_diet[0]` will not work.


```python
print(My_diet[0])
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-14-717052f73e2f> in <module>
    ----> 1 print(My_diet[0])
    

    TypeError: 'set' object is not subscriptable


`TypeError` is raised, because *indexing* does not work in *Sets*, as in *Dictionaries*.

#### Adding elements in a Set
There are two methods to add elements in a *Set*.
* `add()`   : A single element can be added in the *Set*.
* `update()`: Multiple elements can be added in the *Set*.


```python
# Defining a new Set
science = {'Chemistry', 'Physics', 'Mathematics'}
print(science)
```

    {'Physics', 'Chemistry', 'Mathematics'}
    


```python
# Adding sinle element
science.add('Botany')
print(science)
```

    {'Botany', 'Physics', 'Chemistry', 'Mathematics'}
    


```python
# Adding multiple elements
science.update({'Zoology', 'Microbiology'})
print(science)
```

    {'Botany', 'Physics', 'Mathematics', 'Zoology', 'Microbiology', 'Chemistry'}
    

```
# All the things below is equivalent to what written above.
science.update(['Zoology', 'Microbiology'])
science.update(('Zoology', 'Microbiology'))
```

Same element cannot be present in a *Set* multiple times. If an element which is already present in a *Set* is added again, it is overwritten, making a no net change.


```python
# Adding 'Zoology', 'Microbiology' again
science.update(['Zoology', 'Microbiology'])
print(science)
```

    {'Botany', 'Physics', 'Mathematics', 'Zoology', 'Microbiology', 'Chemistry'}
    

Inside the `update()` method, if you don't use extra `()`, or `[]`, or `{}`, then, the consequence is not good.


```python
science.update('Computer Science', 'Statistics')
print(science)
```

    {'Botany', 'Mathematics', 's', ' ', 'Physics', 'n', 't', 'r', 'i', 'm', 'C', 'p', 'o', 'u', 'e', 'Microbiology', 'Chemistry', 'a', 'c', 'S', 'Zoology'}
    

Each character of the element get separated from each other, and each one is added individually in the *Set*.

Note: An added element is not added again. So, only 1 's' will be added if multiple 's' are present.

We have added enough contents in the *Set*. Now, it is time to delete elements.

#### Deleting elements from a Set
There are several methods to delete elements from a *Set*.
* `discard()`: Include the value inside the parenthesis to remove it. It does not do anything if the value is not present in the *Set*.
* `remove()`: Include the value inside the parenthesis to remove it. It throws an error if the value is not present in the *Set*.
* `pop()`: Removes any one element randomly, since ordering does not matter in *Sets*.
* `clear()`: The whole *Set* is cleared and emptied.

Let's see each one with examples.


```python
# clearing the old science set, since it is messed up
science.clear()
print(science)
```

    set()
    

We used `clear()` method to empty our *Set*. It is also a way to define an empty *set* other than `science = set()`.


```python
# Adding subjects in the empty set
science.update({'Mathematics', 'Zoology', 'Physics', 'Geography', 'History', 'Chemistry', 'Computer Science', 'Biology'})
print(science)
```

    {'Mathematics', 'Biology', 'Chemistry', 'Computer Science', 'Geography', 'Physics', 'History', 'Zoology'}
    

Let's remove `'History'` from the *set* using `discard()`.


```python
science.discard('HISTORY')
print(science)
```

    {'Mathematics', 'Biology', 'Chemistry', 'Computer Science', 'Geography', 'Physics', 'History', 'Zoology'}
    

Oops! `'HISTORY'` is not present in the *set*, but `'History'` is present. We used `discard()`, that's why the *set* is unchanged and no errors were raised. Let's do that again correctly.


```python
science.discard('History')
print(science)
```

    {'Mathematics', 'Biology', 'Chemistry', 'Computer Science', 'Geography', 'Physics', 'Zoology'}
    

`'History'` is successfully removed.

Now we will use `remove()` method to remove `'Geography'`.


```python
science.remove('Geology')
print(science)
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-24-ea31414cecbd> in <module>
    ----> 1 science.remove('Geology')
          2 print(science)
    

    KeyError: 'Geology'


I supplied `'Geology'` as argument instead of `'Geography'`. `'Geology'` is not present in the *Set*, so `remove()` method raises `KeyError`. That's the difference between `discard()` and `remove()`.

We do this correctly again.


```python
science.remove('Geography')
print(science)
```

    {'Mathematics', 'Biology', 'Chemistry', 'Computer Science', 'Physics', 'Zoology'}
    

Successfully deleted `'Geography'` from science *set*.

Let's use `pop()` method, in which any random element will be deleted.


```python
science.pop()
print(science)
```

    {'Biology', 'Chemistry', 'Computer Science', 'Physics', 'Zoology'}
    

Have you spotted which one is removed?

### Set operations

There is a whole field of mathematics about [Sets]((https://en.wikipedia.org/wiki/Set_(mathematics)). As in mathematics, *sets* are similar here. There are many *set* operations, like **union**, **intersection**, **difference** etc. We will discuss them here.

#### Set Union

Let us define two sets **A** and **B**, with which we will perform *set operations*.


```python
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}
```

Notice that **A** and **B** have two elements in common, 4 and 5. Union of **A** and **B** is written as $ A \cup B $ in mathematics. Which means that two sets will be merged, and all the elements will be unique. Same element cannot be present multiple times.

$$
\begin{align*}
A \cup B &= \{1, 2, 3, 4, 5, 6, 7, 8\}  \\
A \cup B &\ne \{1, 2, 3, 4, 4, 5, 5, 6, 7, 8\}
\end{align*}
$$

This is the mathematics. Let's do this in Python. In Python this operation is done by using `|` symbol. The same thing can be done using `union()` method.


```python
print(A | B)
```

    {1, 2, 3, 4, 5, 6, 7, 8}
    


```python
print(B | A)
```

    {1, 2, 3, 4, 5, 6, 7, 8}
    


```python
print(A.union(B)) # Doing A | B
```

    {1, 2, 3, 4, 5, 6, 7, 8}
    


```python
print(B.union(A)) # Doing B | A
```

    {1, 2, 3, 4, 5, 6, 7, 8}
    

All gave same results. That means set union is *commutative*. Which means

$$
\begin{equation*}
A \cup B = B \cup A
\end{equation*}
$$

#### Set Intersection

Intersection of **A** and **B** is written as $A \cap B$ in mathematics. Which means that the intersection of **A** and **B** will have only those elements which are common in both *sets*. In this case, 4 and 5 are common in both **A** and **B**.

$$
\begin{equation*}
A \cap B = \{4, 5\}
\end{equation*}
$$

This is the mathematics. Let's do this in Python. In Python, this operation is done using `&` symbol. The same thing can be done by using `intersection()` method.


```python
print(A & B)
```

    {4, 5}
    


```python
print(B & A)
```

    {4, 5}
    


```python
print(A.intersection(B)) # Doing A & B
```

    {4, 5}
    


```python
print(B.intersection(A)) # Doing B & A
```

    {4, 5}
    

All gave same results. That means set intersection is *commutative*. Which means

$$
\begin{equation*}
A \cap B = B \cap A
\end{equation*}
$$

#### Set Difference

Difference of set **A** from set **B**, which is $(A - B)$, is the set of elements that are only in **A**, but not in **B**. In this case,

$$
\begin{align*}
A &= \{1, 2, 3, 4, 5\} \\
B &= \{4, 5, 6, 7, 8\} \\
A - B &= \{1, 2, 3\}
\end{align*}
$$

In Python, this operation is done using `-` symbol. The same thing can be done using `difference()` method.


```python
print(A - B)
```

    {1, 2, 3}
    

Note that $A - B$ is not same as $B - A$. They give different results.


```python
print(B - A)
```

    {8, 6, 7}
    


```python
print(A.difference(B)) # A - B
```

    {1, 2, 3}
    


```python
print(B.difference(A)) # B - A
```

    {8, 6, 7}
    

That means *set difference* is **not** *commutative*.

$$
\begin{equation*}
A - B \ne B - A
\end{equation*}
$$

#### Set Symmetric Difference

Symmetric Difference of **A** and **B** is a set of elements in **A** and **B** but not in both (excluding the intersection). It can be represented by $(A \cup B) - (A \cap B)$.

$$
\begin{align*}
A &= \{1, 2, 3, 4, 5\} \\
B &= \{4, 5, 6, 7, 8\} \\
(A \cup B) - (A \cap B) &= \{1, 2, 3, 6, 7, 8\}
\end{align*}
$$

In Python, this operation is done using `^` symbol. The same thing can be done using `symmetric_difference()` method.


```python
print(A^B)
```

    {1, 2, 3, 6, 7, 8}
    


```python
print(B^A)
```

    {1, 2, 3, 6, 7, 8}
    


```python
print(A.symmetric_difference(B)) # A^B
```

    {1, 2, 3, 6, 7, 8}
    


```python
print(B.symmetric_difference(A)) # B^A
```

    {1, 2, 3, 6, 7, 8}
    

All gave same results. That means set symmetric difference is *commutative*. Which means

$$
\begin{equation*}
(A \cup B) - (A \cap B) = (B \cup A) - (B \cap A)
\end{equation*}
$$
