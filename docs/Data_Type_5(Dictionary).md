---
mathjax: true
layout: repo-code
title:
---

# Dictionary

**Dictionary** is a built-in python data-type, in which data can be stored in *key-value* pairs. A dictionary can be defined very easily. You can assign any variable to a dictionary by a particular syntax, using curly braces and colons.


```python
a = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}
```

The dictionary is now created and stored in the variable **a**. You can now print the dictionary by using `print(a)`.


```python
print(a)
```

    {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}
    

Let's now check what python calls a dictionary by using the `type()` function.


```python
print(type(a)) # prints the type of data of a
```

    <class 'dict'>
    

Python identifies a *dictionary* as `dict`. So `dict` is a reserved keyword in Python like `int`, `str`, `list` etc. 

Now, think about the *length* of the dictionary **a**. What is its length? 6? 

No. In dictionary, the data is saved in pairs. There are 3 pairs in **a**. So the *length* will be 3, not 6. Let's check and verify that using the in-built python function `len()`.


```python
print(len(a))
```

    3
    

You can even define an empty dictionary, like an empty *string* `''`, empty *list* `[]` etc. Let us define an empty dictionary and check its *length*.


```python
empty_dict = {}
print(len(empty_dict))
```

    0
    

Well, everything went as expected. Let's talk about the *key-value* pairs. 

In a *key-value* pair, a **key** and a **value** is separated by a colon `:`. The one before `:` is the **key** and the one after `:` is the corresponding **value**. 
Different *key-value* pairs are separated by a comma `,`. 

Now, what are the accepted data-types of *keys* and *values*. Well, a key can be anything which is **immutable**, i.e., *string*, *number (int, float, complex)*, *tuple* or *boolean*. Values can be of any data-type, *string*, *number*, *list*, *tuple*, *boolean*, *dictionary* etc. 
(Yes, *dictionaries* can be present within a *dictionary*, like *lists* can be present within a *list*).


```python
# A valid dictionary
fruits = {'Orange': 2, 'Mango': 16, 'Banana': 12, 'Apples': 5}
print(fruits)
```

    {'Orange': 2, 'Mango': 16, 'Banana': 12, 'Apples': 5}
    


```python
# An invalid dictionary
foods = {['Fruits', 'Grains', 'Nuts', 'Vegetables']: 'I like them', ['Meat', 'Fish', 'Dairy']: 'I do not like them'}
# This dictionary has two pairs. In each pairs, keys are lists, which is not allowed.
print(foods)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-7-0273117ad009> in <module>
          1 # An invalid dictionary
    ----> 2 foods = {['Fruits', 'Grains', 'Nuts', 'Vegetables']: 'I like them', ['Meat', 'Fish', 'Dairy']: 'I do not like them'}
          3 # This dictionary has two pairs. In each pairs, keys are lists, which is not allowed.
          4 print(foods)
    

    TypeError: unhashable type: 'list'


Sometimes errors are helpful too. This is a `TypeError`, which means `list` is not accepted data-type as *keys* in the dictionary.

### Using Variables in dictionary

Suppose we declare some variables below.


```python
Veg_foods = ['Fruits', 'Nuts', 'Grains', 'Vegetables'] # List
Non_Veg_foods = ['Meat', 'Fish'] # List

# Dictionary containing variables Veg_foods and Non_Veg_foods
My_diet = {True : Veg_foods, False: Non_Veg_foods}
```

What should be the outcome if we print `My_diet`. Will it be printed with the variable names, or with the data that is stored in that variable names?


```python
print(My_diet)
```

    {True: ['Fruits', 'Nuts', 'Grains', 'Vegetables'], False: ['Meat', 'Fish']}
    

You must have understood by now what we meant to say.

### Is a Dictionary mutable or immutable?

**Mutable** means whether a data-type allows us to do changes within them once they are defined. **Immutable** data-types do not allow us to change their content. Either we can use its content to create a new data-type, or we totally overwrite them and assign them new content again. 

It may be difficult to remember which data-types are *mutable* or *immutable*. Why not let us check ourselves? No, do not Google it up. We can check it using Python itself. Let us print our `fruits` dictionary again.


```python
print(fruits)
```

    {'Orange': 2, 'Mango': 16, 'Banana': 12, 'Apples': 5}
    

Now I remember that I have much more 'Oranges'. I have 10 'Oranges'. In *lists*, *strings*, *tuples*, the elements within them can be accessed by **index**. The first element of a *list* can be accessed by `list_name[0]`, *string* by `string_name[0]`, and so on for tuples. 

But how to access the *key-value* pairs of a dictionary? Forget about checking mutability if we don't know that. 

This thing can be done using this way as shown below.


```python
print(fruits['Orange']) # Accessing list item using key. If the key is present, then corresponding value will be printed.
```

    2
    


```python
print('I have {} mangoes, {} bananas, and {} apples'.format(fruits['Mango'], fruits['Banana'], fruits['Apples']))
```

    I have 16 mangoes, 12 bananas, and 5 apples
    

Do not worry if you are unable to understand what happened in the above line. We have just used string formatting for nicer output. You should get the logic by now, how to access any *value* from a dictionary using *key* name.

We can also use `get()` method to access a *value* for a *key* in the dictionary


```python
print(fruits.get('Orange'))
```

    2
    

But there is a significant difference between `[]` and `get()` method. If we use `[]` and search for the *value* of a *key* which is not present in the dictionary, then `KeyError` is raised, whereas in case of `get()`, no error is raised, and `None` is returned.


```python
print(fruits['Guava'])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-14-59ba86ded67e> in <module>
    ----> 1 print(fruits['Guava'])
    

    KeyError: 'Guava'



```python
print(fruits.get('Guava'))
```

    None
    

**Why indexing is not used to access elements in dictionary?**

It is because the ordering of pairs in a dictionary is not fixed. They can change in due course. In the `fruits` dictionary, `'Orange'` belongs to the first pair now. But, during many operations (adding more pairs, removing pairs), the ordering may change, and it may not belong to the first pair forever. That's why indexing does not matter in *dictionaries*. The thing which matters is the *key-value* pair itself, whether it is present, or not.

Now, come again to the question whether a dictionary is *mutable* or not? Let's check. I have 10 `'Orange'` now.


```python
fruits['Orange'] = 10 # Assigning the value of 'Orange' to be 10
print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Banana': 12, 'Apples': 5}
    

Yeah! We **successfully replaced** the *value* of the `'Orange'` *key* to 10. 

That means, **Dictionaries are Mutable**. Now you can search Google and confirm whether this is right or not :)

One thing to note is that a same *key* cannot be present in a dictionary more than one time. You will know why.

### Adding elements in Dictionary

How to add new *key-value* pairs in a dictionary? Well you probably know this one. We use the same `[]` method to add new *key-value* pairs.


```python
# Adding Pears. I have a lot of pears.
fruits['Pear'] = 42
print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Banana': 12, 'Apples': 5, 'Pear': 42}
    

Let's add some more tasty fruits


```python
fruits['Strawberry'] = 5
fruits['Watermelon'] = 1
fruits['Raspberry'] = 18
fruits['Lychee'] = 50

print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Banana': 12, 'Apples': 5, 'Pear': 42, 'Strawberry': 5, 'Watermelon': 1, 'Raspberry': 18, 'Lychee': 50}
    

Wow, we have many many fruits. Now we should also be able to delete fruits from a *dictionary*.

### Deleting elements from a Dictionary

Well there are more ways to delete elements than to add elements. Let's list them all, and use them one by one.
* `pop()` method: Include the *key* inside parenthesis to delete a pair. The corresponding value is returned before deletion.
* `popitem()` removes any random pair, outputting the removed pair as a *tuple*.
* `del` to delete a pair using *key*, or to delete the entire dictionary itself.
* `clear()` to remove all pairs from the dictionary, making the dictionary empty.

Let's see each one with examples.


```python
# Removing 'Lychee' key and its corresponding value
fruits.pop('Lychee')
```




    50



The corresponding value *50* is returned. The thing **return** means that it only shows output in Python Shell, not in text editors, until and unless it is printed using `print(fruits.pop('Lychee'))`.


```python
print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Banana': 12, 'Apples': 5, 'Pear': 42, 'Strawberry': 5, 'Watermelon': 1, 'Raspberry': 18}
    

Now its the time to use `popitem()`.


```python
fruits.popitem()
```




    ('Raspberry', 18)



A *random* corresponding pair is returned and removed from the dictionary. Remember, it is random because **ordering of elements does not matter in dictionary**. 


```python
print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Banana': 12, 'Apples': 5, 'Pear': 42, 'Strawberry': 5, 'Watermelon': 1}
    

Now, `del`.


```python
# Removing 'Banana' and its corresponding value
del fruits['Banana']
print(fruits)
```

    {'Orange': 10, 'Mango': 16, 'Apples': 5, 'Pear': 42, 'Strawberry': 5, 'Watermelon': 1}
    

Now we will use `clear()`.


```python
fruits.clear()
print(fruits)
```

    {}
    

This made our *dictionary* empty. Now, we can delete our dictionary itself using `del`.


```python
del fruits
```

It must have deleted our *dictionary*. It means, now nothing is stored in `fruits`. So, if we try `print(fruits)`, it should show us an error.


```python
print(fruits)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-26-c5ba58fe0871> in <module>
    ----> 1 print(fruits)
    

    NameError: name 'fruits' is not defined


As expected, `NameError` is raised, saying,
> name 'fruits' is not defined

Now, let us define a new *dictionary* of `vegetables`.


```python
vegetables = {'Broccoli': 4, 'Cauliflower': 2}
print(vegetables)
```

    {'Broccoli': 4, 'Cauliflower': 2}
    


```python
# Adding more vegetables
vegetables['Tomato'] = 25
vegetables['Potato'] = 10
vegetables['Corn'] = 6
print(vegetables)
```

    {'Broccoli': 4, 'Cauliflower': 2, 'Tomato': 25, 'Potato': 10, 'Corn': 6}
    

We said sometime ago that a dictionary **cannot have more than one same *key***. It should be obvious now why it is not possible. 

Let's add `'Tomato'` as a *key* again.


```python
vegetables['Tomato'] = 18
print(vegetables)
```

    {'Broccoli': 4, 'Cauliflower': 2, 'Tomato': 18, 'Potato': 10, 'Corn': 6}
    

The old value of `'Tomato'` was overwritten by the new value. That's why, same *key* is not possible multiple time. But same *value* can be present multiple times for different *keys*.
