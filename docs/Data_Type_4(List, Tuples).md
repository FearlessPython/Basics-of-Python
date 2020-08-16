
# List and Tuple

## List

**Lists** are like arrays in other programming languages. It can contain elements belonging to different data-types in a single list. Here the elements are indexed according to a definite sequence. Lists are *mutable* i.e., the elements of a list can be changed by other elements.

### Declaring a List


```python
a = [1, 2, 3, 4, 5, 'python', 3+2j, 8.9, False]
a

```




    [1, 2, 3, 4, 5, 'python', (3+2j), 8.9, False]



### Lists are mutable


```python
a = [1, 2, 3, 4, 5]
b = [1, 2, 3, 4, 6]
id(a)
```




    99466456




```python
id(b)
```




    99077456



`id()` displayes the memory location for a value in Python. Clearly we can see both the variables have different id location. So they are distinct. 

Now,


```python
a[4] = 6
```


```python
a, b
```




    ([1, 2, 3, 4, 6], [1, 2, 3, 4, 6])



We have now changed the value of the 4th index from 5 to 6 so now `a` and `b` array are equal. But,


```python
id(a), id(b)
```




    (99466456, 99077456)




```python
a == b
```




    True



Still we see that the memory location is different. This proves that we are able to change a list i.e., lists are *mutable*. You can try for *int* datatypes you will see that when you change the value its id location will also change.


```python
a = 10
b = 12
id(a), id(b)
```




    (2088920304, 2088920336)




```python
a = 12
id(a), id(b)
```




    (2088920336, 2088920336)



### Length of List

We can calculate the number of elements present in a list by using the inbuilt Python function `len()`.


```python
a = [1, 2, 3, 4, 5, 6, 'python']
len(a)
```




    7



### Indexing in List

Similar to string, list have two types of indexing, *Forward indexing* and *Reverse Indexing*.

#### Forward Indexing

Here the indexing starts with 0, the first element is given the index 0 and this indexing goes on upto `len(list) - 1` i.e., the last element of the list has the index `len(list) - 1`.


```python
a=[1, 2, 3, 4, 5, 6, 7, 8]
a[0], a[3], a[7]
```




    (1, 4, 8)



The first element has index 0 the 4th element i.e 4 has index 3 and the last element i.e., 8 has index 7

#### Reverse Indexing

Here the indexing starts from the end of the list. The last element is given the index -1 and the seond last gets the index -2 and so on the indexing runs from right to left and the first element gets the index -len(list).


```python
a[-1], a[-8], a[-4]
```




    (8, 1, 5)



The last element has the index -1 the first element has index -8 and so on 

#### Finding the index of the element :


We can find the index of an element by using the `index()` function. It returns the index value of the first occurence of the element. It returns `ValueError` if the element whose index we are going to find is not present in the list or the portion of the list we have given to search.


```python
a.index(5)
```




    4



Similarly, as in string we can also define the area of search in list too.


```python
a = [1, 2, 3, 1, 4, 5, 1]
a.index(1, 1)
```




    3



In the above example, we have started searching for the element 1 from the index 1, so we did not get the value of index of 1 as 0 rather we got 3 i.e., the first occurence of 1 from index 1.

We can similarly add the upper limit point to the search .


```python
a.index(1, 1, 4)
```




    3



Here the search will be from index 1 to index 4 only.

### `IndexError`

We get `IndexError` error when we enter any value which is greater than the indices preset in the list. 


```python
a[8]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-16-beec7994ef7f> in <module>
    ----> 1 a[8]
    

    IndexError: list index out of range


### Slicing in List

We can create sub-list from a list by using the slicing operation.


```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
a[2:6]
```




    [3, 4, 5, 6]



Here we have sliced the list starting from index 2 and ending with index 5 i.e., 1 index prior to the upper limit (6).

If we want to slice the list starting from the first element and ending before a certain index we can do the following:


```python
a[:6]
```




    [1, 2, 3, 4, 5, 6]



If we want to start the slicing from an index and end the slicing at the end of the list we can do it by the following:   


```python
a[4:]
```




    [5, 6, 7, 8, 9]



We can also slice a list by skipping the elements in a pattern. For example, let's make a new list from the old list with skipping all the elements alternatively.


```python
b = a[::2]
b
```




    [1, 3, 5, 7, 9]



See we were able to create a list `b` where alternatively all the elements are skipped. Secondly, we have intentionally kept the two places blank as mentioned in the Strings notebook That when we keep the first place blank python sets a default value of 0 and at the second place the value `len(list)`. We have written 2 in the third place as we want to skip the elements alternatively. If we were to skip two elements at a time we would write 3 in the place of 2.

#### Reverse Slicing

We can also reverse slice the list by placing the start index of the sicing at the first place and the ending index at the second place and we will have to put -1 at the third place. For Example,


```python
a[8:2:-1]
```




    [9, 8, 7, 6, 5, 4]



See we have placed the index from where the slicing will start and entered the index before which the slicing will stop. Note we have put 2 and the slicing has stopped at index 3. Similarly try for -2, -3 in place of -1 and see.

### Adding Element to a List

We can add element to a list by 3 different methods shown below:

#### `append()`

This function is used when we will have to add a single element at the end of the list. For example :


```python
a = [1, 2, 3, 4, 5]
b = 8
a.append(b)
print(a)
```

    [1, 2, 3, 4, 5, 8]
    

See the element 8 has been added at the end of the list.

#### `extend()`

If instead of adding a single element to the list we have to add multiple elements stored in another list we can use the `extend()` function.


```python
a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9]
a.extend(b)
a
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9]



The elements in list b are aso added at the end of the list `a`.


```python
a = [1, 2, 3, 4, 5]
f = 6
g = 7
h = 9.0
a.extend([f, g, h])
a
```




    [1, 2, 3, 4, 5, 6, 7, 9.0]



#### `insert()`

If we want to insert the values at a specified index then we use the insert function. If the specified index is greater than the indices present, then it will add the element at the last of the list.


```python
a = [1, 2, 3, 4, 5]
b = 7
a.insert(2, b)
a
```




    [1, 2, 7, 3, 4, 5]



See we have inserted element 7 at index 2.


```python
a.insert(4, [2, 4, 5])
```


```python
a
```




    [1, 2, 7, 3, [2, 4, 5], 4, 5]




```python
a = [1, 2, 3, 4, 5, 6]
a.insert(50, 8)
a
```




    [1, 2, 3, 4, 5, 6, 8]



### Deleting Elements from a List

We can delete elements from a list by 3 different methods shown below.

#### `pop()`

This will remove the element from the index specified. If no index is specified it will remove the last element by default. If the list is empty or the index is out of range then it will give an `IndexError`.


```python
a = [1, 2, 3, 4, 5, 6]
a.pop(3)
a
```




    [1, 2, 3, 5, 6]



It has removed the element that was present at index 3.


```python
a.pop()
a
```




    [1, 2, 3, 5]



We have not mentioned any index here so it just removed the last element from the list.

#### `remove()`

It will remove the first occurence of the element mentioned to remove. If the element is not present in the list it will show `ValueError`.


```python
a = [1, 2, 3, 4, 5, 6, 7]
a.remove(4)
```


```python
a
```




    [1, 2, 3, 5, 6, 7]



See the value 4 has been removed.


```python
a.remove(8)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-33-62fd461cfce9> in <module>
    ----> 1 a.remove(8)
    

    ValueError: list.remove(x): x not in list


See the value 8 was not present in the list so it returned a `ValueError`.

#### `del()`

This is used when we want to delete multiple elements from the list. It deletes all the elements from the first specified index to the index before the second specified index.


```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
del a[2:5]
a
```




    [1, 2, 6, 7, 8, 9]



Here the function has deleted all the elements from 2 to 4 i.e., an index before the upper limit given which was 5.


```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
del a[2:8:2]
a
```




    [1, 2, 4, 6, 8, 9, 0]



Similarly as in slicing by putting a third number we skiped an element alternatively we can also skip an element alternatively while deleting here too.

### Sorting a List

We can sort the list by using `sort()` function.


```python
a = [1 ,5, 3, 9, 2, 5, 3, 0]
a
```




    [1, 5, 3, 9, 2, 5, 3, 0]




```python
a.sort()
```


```python
a
```




    [0, 1, 2, 3, 3, 5, 5, 9]



The list gets sorted.

We can even sort the list in the reverse order by writing the following code.


```python
a.sort(reverse = True)
a
```




    [9, 5, 5, 3, 3, 2, 1, 0]



The list got sorted in the reverse order.

### Some other functions of List

We can calculate the sum of a list which is having all its elements as numbers by using `sum()` function.


```python
a = [1, 2, 3, 4, 5, 6, 7]
sum(a)
```




    28



We can find the minimum and the maximum element in the list by `min()` and `max()`.


```python
min(a)
```




    1




```python
max(a)
```




    7



We can calculate the number of occurances of an element in a list by using the `count()` function.


```python
a = [1, 2, 3, 4, 5, 6, 2, 3, 2, 4]
a.count(2)
```




    3



## Tuple

Like a list tuple is also an array of data but it is inmutable i.e., it cannot be changed.

### Declaring a tuple


```python
a = (1, 2, 3, 4, 'python', 9.0)
a
```




    (1, 2, 3, 4, 'python', 9.0)



### Tuple is immutable

This mean we cannot alter any existing value of a tuple neither we can add new value to it or delete any pre-existing value. On doing so we will get a `TypeError`.


```python
a[4] = 7
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-45-cb3ce5dc8467> in <module>
    ----> 1 a[4] = 7
    

    TypeError: 'tuple' object does not support item assignment


### Fetching values from tuple


```python
b = a[5]
b
```




    9.0



### Counting Values

We can count the number of occurences of an element in a tuple by using `count()` function.


```python
a = (1, 2, 2, 3, 4, 5, 2, 3)
a.count(2)
```




    3




```python
a.count(7)
```




    0



### Getting Index of an Element

We can get the index of an element in the tuple by using `index()` function. It returns the index of the first occurence of the element in the tuple. Like in list we can also define the portion of the searching for the element here also. It returns a `ValueError` if the element is not present in the tuple.


```python
a.index(2)
```




    1




```python
a.index(2, 4)
```




    6



So here we end with List and Tuples for more info on these you can type `help(list)` for list and `help(tuple)` for tuple in the interpreter.
