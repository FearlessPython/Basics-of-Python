---
mathjax: true
layout: repo-code
comments: true
title:
---

# Loops

We do programming to simplify our day to day life. Huge tasks can be done in a matter of seconds. Sometimes, many tasks involve repeatition, doing the same thing again and again, like printing your name for 10 times, printing the numbers 0 to 5, or printing the number of guest names contained in a list, with a greeting. How can we do this in Python? Let's try.

**Printing the name "Smith" 10 times.**


```python
my_name = "Smith"
print(my_name)  # 1
print(my_name)  # 2
print(my_name)  # 3
print(my_name)  # 4 
print(my_name)  # 5
print(my_name)  # 6
print(my_name)  # 7
print(my_name)  # 8
print(my_name)  # 9
print(my_name)  # 10
```

    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    

**Printing the numbers 0 to 5.**


```python
print(0)
print(1)
print(2)
print(3)
print(4)
print(5)
```

    0
    1
    2
    3
    4
    5
    

**Printing the number of guest names contained in a list, with a greeting.**


```python
guest_names = [
    'Leonardo DiCaprio', 
    'Christian Bale', 
    'Hugh Jackman',
    'Matthew McConaughey',
    'Brad Pitt',
    'Matt Damon',
    'Denzel Washington',
    'Russell Crowe',
    'Benedict Cumberbatch',
    'Joaquin Phoenix'
]
```

Yes, we can write a list like that if it is too long. Make sure to include a comma (`,`) between every element. 

First, make sure our `guest_names` list has 10 guests. We cannot afford more than 10 guests in our party.


```python
print(len(guest_names))
```

    10
    

Okay, we can successfully take care of our all elite guests. But, before including them in our party, we have to write a program to print a greeting for all our guests.


```python
greeting = 'Welcome to the party, Mr.'
print(greeting, guest_names[0])
print(greeting, guest_names[1])
print(greeting, guest_names[2])
print(greeting, guest_names[3])
print(greeting, guest_names[4])
print(greeting, guest_names[5])
print(greeting, guest_names[6])
print(greeting, guest_names[7])
print(greeting, guest_names[8])
print(greeting, guest_names[9])
```

    Welcome to the party, Mr. Leonardo DiCaprio
    Welcome to the party, Mr. Christian Bale
    Welcome to the party, Mr. Hugh Jackman
    Welcome to the party, Mr. Matthew McConaughey
    Welcome to the party, Mr. Brad Pitt
    Welcome to the party, Mr. Matt Damon
    Welcome to the party, Mr. Denzel Washington
    Welcome to the party, Mr. Russell Crowe
    Welcome to the party, Mr. Benedict Cumberbatch
    Welcome to the party, Mr. Joaquin Phoenix
    

We accessed all the members of `guest_names` list one by one using the index notation (0, 1, 2, etc.,).

This is nice, isn't it? By programming, we can do amazing things. There are much more things which we can do. But do you notice that we are doing the same thing again and again. Why will we repeat something again and again, if the computers are here for us?

In programming, we should not repeat ourselves. There is a concept in programming called [DRY (Don't Repeat Yourself)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself). Computers need to repeat the same thing again and again, we don't. For this purpose, there are **loops** in Python (and many other programming languages). Using *loops*, we can make a block of code to repeat again and again, for any number of times. By few lines of code, you can print your name even for 30,000 times just in a matter of seconds.

Basically, there are **two types of *loops*** in Python listed below:
* `for` loop
* `while` loop

Both of them do the same thing, repeating a code block again and again, but their application and syntax is slightly different. In `for` loop, we know that how many times we have to repeat, whereas in `while` loop, we know upto when we have to repeat. We will discuss both of the loops with example. 

Let's start with `for` loop.

## 1. `for` loop

To use the `for` loop, first we need to know the inbuilt `range()` function in Python. `for` loop can be used without using `range()` function also (like looping through the elements of a list, or a string), but it is important to know about the `range()` function by now. Most of the time they are used with `for` loop.

### `range()` function
The `range()` function returns a range of integers from a *starting point* to an *ending point*, increasing the numbers *step by step*. The `range()` function takes some arguments (inside the parenthesis of `range()`). It takes a minimum of 1 argument and a maximum of 3 arguments. We have to see all the cases.


```python
print(range(0, 10))
```

    range(0, 10)
    

Doing this simply won't work. It merely tells us that this is a range of numbers from `0` to `9` (not including `10`). It expects us to know what it does. So it does not list the whole range of numbers. We humans are smart enough. We know the other way around to see the whole list of numbers. We just have to add a functionality.


```python
print(list(range(0, 10)))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    

Yes, this works. We converted the sequence to a Python list. So, we provided 2 arguments here, `0`, and `10`. Here, `0` is the starting point and `10` is the ending point, but the ending point is not included. Only the integer prior to the ending point is included. There are many similar instances in Python (like slicing) where the ending point is not included. 

Above, we saw that the numbers started from `0`, increases step by step by `1`, and ended just before `10`. Let's see more examples. What if we provide only one argument?


```python
print(list(range(10)))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    

What we did is exactly similar to the previous example. If we provide *only one argument*, then it is regarded as the *ending point*, and the default starting point is `0`.

Now, we can also provide three arguments of the `range()` function. In that case, the third argument will be regarded as the step, by which every integer will progress in the sequence.


```python
print(list(range(0, 20, 1)))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
    


```python
print(list(range(0, 20, 2)))
```

    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
    


```python
print(list(range(0, 20, 5)))
```

    [0, 5, 10, 15]
    


```python
print(list(range(0, 20, 10)))
```

    [0, 10]
    


```python
print(list(range(0, 20, 20)))
```

    [0]
    

We can also change the *starting integer*.


```python
print(list(range(5, 20, 2)))
```

    [5, 7, 9, 11, 13, 15, 17, 19]
    

So, now you should know that if we do not provide the 3rd argument, its default value is 1.

We can also print a reverse sequence.


```python
print(list(range(20, 0, -1)))
```

    [20, 19, 18, 17, 16, 15, 14, 13, 12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
    

The *starting point* here is `20`, the *ending point* is `0`, and the step is `-1`, so the numbers are gradually decreasing one by one.

What will happen if we provide `0` as the *step*? 


```python
print(list(range(0, 25, 0)))
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-16-7131dfd75d66> in <module>
    ----> 1 print(list(range(0, 25, 0)))
    

    ValueError: range() arg 3 must not be zero


That seems an error, which is very logical. How can there be a sequence if they do not increase at all? Every number is going to be the same (0, 0, 0, ...), then, it will never reach the *ending point* (25), so it will progress forever infinite times. So, the 3rd argument can never be a `0`.

See few more cases.


```python
print(list(range(10, 20, -1)))
```

    []
    

That's an empty list because how can the series proceed from `10` to `20` if every number is going to **decrease** by 1?

A same empty list will be generated if we do `list(range(20, 10))`.


```python
print(list(range(20, 10))) # equivalent to print(list(range(20, 10, 1)))
```

    []
    

Now we are ready to encounter the `for` loop. `for` is a reserved Python keyword for its application in loops. Till now, we printed the sequence generated via `range()` function by converting it to a list. By using `for` loop, we can print each term of the sequence one by one, on each line. The general structure of a `for` loop is like this.


```python
for term in range(0, 10): # A colon (:) is required, which indicates that the block of for loop is to be started.
    print(term)
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    

The result is as expected. When we started the `for` loop, we wrote
```Python
for term in range(0, 10):
```
`range(0, 10)` means sequence from `0` to `10` (not including `10`). So we are asking for each `term` *in* the sequence, we want to do something (`in` is a reserved keyword in Python which checks the elements within sequence/list/tuple etc). It will loop several times over the sequence. 

In the first loop, `term = 0`, and then the rest code block below will be executed with the value of `term = 0`. After the whole code block gets executed, the Python interpreter  will again come to the line `for term in range(0, 10):`. Now this time, second loop gets started, and `term = 1`, and so on, until `term = 9`. After that, our Python interpreter will again come to the `for` loop line, and now it will see that the sequence is exhausted. So, it will exit out of the loop. 

One thing to note is that you can provide any variable in place of `term`, as long as it is meaningful to you. Most of the time, `i` is used, which stands for iteration (repitition process in each looping cycle).

Here, the code block of our `for` loop is `print(term)`. Notice that we have provided an *indentation*. You can press `Tab` key of your keyboard, or include either `2` or `4 space` of indentation. Some people even provide `8 space` of indentation. But that is not recommended. The official Python style is to use `4 space` indentation, like we used here. You should be consistent throughout your code. If you include irregular spaces of indentation (like, somewhere 4 spaces, and somewhere 2 spaces), then you are likely to get `IndentationError`.

What *indentation* means is that, our block of code has started. Here, we provided `print(term)` as the code block within the `for` loop. That means as the value of `term` is changing in different looping cycles, it will be printed out one by one. Whenever we stop giving the *indentation*, that will mean that we have stopped writing the code which will be included inside the `for` loop.

Let's see all the examples one by one.


```python
for i in range(10):
    print(i)
print("Is this line inside the loop?")
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    Is this line inside the loop?
    

We can see that we wrote the line `print("Is this line inside the loop?")` without providing indentation, while the previous line is given an indentation. If the last line was inside the code block of the `for` loop, then it should have been printed 10 times (10 iterations/looping cycles, from 0 to 9). Now we will provide an indentation to that line too and see whether it is printed 10 times or not.


```python
for i in range(10):
    print(i)
    print("Is this line inside the loop?")
```

    0
    Is this line inside the loop?
    1
    Is this line inside the loop?
    2
    Is this line inside the loop?
    3
    Is this line inside the loop?
    4
    Is this line inside the loop?
    5
    Is this line inside the loop?
    6
    Is this line inside the loop?
    7
    Is this line inside the loop?
    8
    Is this line inside the loop?
    9
    Is this line inside the loop?
    

Now you must have understood the significance of *indentation*. Do you have any idea now, how can you use this technique to print your name thousands of times? We can use
```Python
for i in range(30000):
    print("Will Smith")
```
This will print the name `"Will Smith"` 30000 times. But we won't print here for 30000 times, because if we do so, then you have to scroll for a long time to reach the bottom of this page to view the other content. But be sure to try this out at home and annoy your friends/brother/sister by printing your name for thousands of time, may be millions of time, and show them how important you are.

We can print here for 10 times at least.

**Printing the name "Smith" 10 times (using `for` loop)**


```python
for i in range(0, 10):
    print("Smith")
```

    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    Smith
    

Cool! Isn't it? We did the same thing above without using loops at all, and we wrote 11 lines there. Here, only 2 lines. Now printing the numbers from 0 to 5 will be a cake-walk for us.

**Printing the numbers 0 to 5 (using `for` loop)**


```python
for number in range(0, 6):
    print(number)
```

    0
    1
    2
    3
    4
    5
    

We can also do the same thing by looping/iterating over the elements of a list. We can access each element using the index of that element in the list. There are actually two ways to iterate over a list. In one way, we have to use the `range()` function and the indices of the list elements, and in an other way, without using `range()` function or the indices. We will continue with our previous `guest_names` list.

**Printing the number of guest names contained in a list, with a greeting (using `for` loop) - Level 1**


```python
print(guest_names) # Viewing the previous guest_names list again.
```

    ['Leonardo DiCaprio', 'Christian Bale', 'Hugh Jackman', 'Matthew McConaughey', 'Brad Pitt', 'Matt Damon', 'Denzel Washington', 'Russell Crowe', 'Benedict Cumberbatch', 'Joaquin Phoenix']
    


```python
greeting = 'Welcome to the party, Mr.'
for index in range(0, 10): # Ten elements in the list, so the index will be from 0 to 9
    print(greeting, guest_names[index])
```

    Welcome to the party, Mr. Leonardo DiCaprio
    Welcome to the party, Mr. Christian Bale
    Welcome to the party, Mr. Hugh Jackman
    Welcome to the party, Mr. Matthew McConaughey
    Welcome to the party, Mr. Brad Pitt
    Welcome to the party, Mr. Matt Damon
    Welcome to the party, Mr. Denzel Washington
    Welcome to the party, Mr. Russell Crowe
    Welcome to the party, Mr. Benedict Cumberbatch
    Welcome to the party, Mr. Joaquin Phoenix
    

We used `range(0, 10)` here (equivalent to `range(10)`). But what if the list contains hundreds, or even thousands of guests? Then we won't know what we have to use in place of `range(10)`. Suppose there are 6154 guests in our list. Then if we mistakenly use `range(6100)`, then 54 last guests in the list won't be greeted, and they will feel bad. If we use `range(6200)`, then none of the guests will be greeted (it will be an `IndexError`). Oh! How stupid can I be? We can use the Python inbuilt `len()` function to find out the number of guests in the list, and use it inside `range()` function. The output of `len()` is consistent with `range()`, we ourselves don't have to know the length of the list at all. We are plugging it inside the `range()` function, and `len()` is telling the length of list only to the `range()`, not us. It's all plug and play.


```python
greeting = 'Welcome to the party, Mr.'
for index in range(len(guest_names)): # len(guest_names) outputs 10, so the index will be from 0 to 9
    print(greeting, guest_names[index])
```

    Welcome to the party, Mr. Leonardo DiCaprio
    Welcome to the party, Mr. Christian Bale
    Welcome to the party, Mr. Hugh Jackman
    Welcome to the party, Mr. Matthew McConaughey
    Welcome to the party, Mr. Brad Pitt
    Welcome to the party, Mr. Matt Damon
    Welcome to the party, Mr. Denzel Washington
    Welcome to the party, Mr. Russell Crowe
    Welcome to the party, Mr. Benedict Cumberbatch
    Welcome to the party, Mr. Joaquin Phoenix
    

Well, we are making huge progress. Thousands, or even millions of guests can be greeted, with just those few lines of code, not millions of lines of code.

Now, it is the time for *Level 2*, where we won't use `range()`, `len()`, or *indices* of the elements at all. Will this level be harder?

**Printing the number of guest names contained in a list, with a greeting (using `for` loop) - Level 2**


```python
for element in guest_names:
    print(element)
```

    Leonardo DiCaprio
    Christian Bale
    Hugh Jackman
    Matthew McConaughey
    Brad Pitt
    Matt Damon
    Denzel Washington
    Russell Crowe
    Benedict Cumberbatch
    Joaquin Phoenix
    

Wooho! It was a lot more easier. Just as previously we were iterating over the terms of a sequence, and used them to access list elements via their indices, here we are directly iterating over the elements of the list. No indices are required to access them.

Now let's greet our guests.


```python
greeting = 'Welcome to the party, Mr.' 
# We don't have to assign this again and again, its already stored in memory, but just for your convenience

for element in guest_names:
    print(greeting, element)
```

    Welcome to the party, Mr. Leonardo DiCaprio
    Welcome to the party, Mr. Christian Bale
    Welcome to the party, Mr. Hugh Jackman
    Welcome to the party, Mr. Matthew McConaughey
    Welcome to the party, Mr. Brad Pitt
    Welcome to the party, Mr. Matt Damon
    Welcome to the party, Mr. Denzel Washington
    Welcome to the party, Mr. Russell Crowe
    Welcome to the party, Mr. Benedict Cumberbatch
    Welcome to the party, Mr. Joaquin Phoenix
    

We can apply the same method not only to the lists, but to strings also, where the loop will iterate over the characters of the string.


```python
greeting = 'Welcome to the party, Mr.' 

for char in greeting:
    print(char)
```

    W
    e
    l
    c
    o
    m
    e
     
    t
    o
     
    t
    h
    e
     
    p
    a
    r
    t
    y
    ,
     
    M
    r
    .
    

It is amazing, right? Loops are really amazing and fascinating. Now it's the right time to introduce `while` loop to you.

## 2. `while` loop

Unlike `for` loop, we don't need the `range()` function to make `while` loop work. In `for` loop, when we use the `range()` function, we know that how many iterations/repititions will take place. (*e.g*., If we use `range(10)`, then we know that there will be 10 repititions). But in case of `while` loop, we don't exactly know how many iterations will take place (but eventually number of iterations can be found out after whole `while` loop is executed). 

In `while` loop, we know that upto which condition the iterations will take place. `while` loop utilises `True` or `False` booleans. If a condition evaluates to `True`, then looping will continue, and if a condition evaluates to `False`, the Python interpreter immediately exits out of the loop. And moreover, we should also check that the condition used in `while` loop don't remains the same forever, because if the condition evaluates to `True` forever, then infinite number of looping cycles will occur, due to which, Python interpreter never exits the loop, and you have to forcibly stop the program to end the loop, without any end result. Well, these things are very technical. Everything will be clear with the following examples.

**The general structure of `while` loop (The syntax)**
```Python
while condition:
    # CODE BLOCK
    # Change the condition as required within the block per iteration
```

Let us understand `while` loop by printing the numbers 0 to 5.

**Printing the numbers 0 to 5 (using `while` loop)**


```python
start = 0
end = 5

while start <= end: # The condition (start<=end) evaluates to True until start = 5. When start = 6, it Evaluates to False.
    print(start)    # printing the value of start
    start = start + 1   # Changing the value of start per iteration so that our condition evaluates to False in future.
```

    0
    1
    2
    3
    4
    5
    

Have you got it? If we don't do `start = start + 1`, then the value of start will never change (it will remain `0` forever), so the condition `start <= end` will always return `True`, and that will make us enter into *infinite loop*.

Here is a look of the code which if executed will be entered into an *infinite loop*.
```Python
i = 0

while i < 2:
    print(i)
```
*Output*
```Python
0
0
0
...
# prints 0 forever
```

In this condition, to escape from the *infinite loop*, we will increment `i` by 1. When `i = 2`, the condition `i < 2` evaluates to `False`, and Python interpreter will exit out now of the loop.


```python
i = 0

while i < 2:
    print(i)
    i += 1    # incrementing i by 1 after each looping cycle
```

    0
    1
    

Now, you must have understood the working of `while` loop. You will be more clear after more upcoming examples.

**Printing the name "Smith" 10 times (using `while` loop)**


```python
num_of_printing = 10
i = 1

while i <= num_of_printing:
    print("Smith", i)
    i += 1
```

    Smith 1
    Smith 2
    Smith 3
    Smith 4
    Smith 5
    Smith 6
    Smith 7
    Smith 8
    Smith 9
    Smith 10
    

**Printing the number of guest names contained in a list, with a greeting (using `while` loop)**


```python
print(guest_names) # Viewing the previous guest_names list again.
```

    ['Leonardo DiCaprio', 'Christian Bale', 'Hugh Jackman', 'Matthew McConaughey', 'Brad Pitt', 'Matt Damon', 'Denzel Washington', 'Russell Crowe', 'Benedict Cumberbatch', 'Joaquin Phoenix']
    


```python
greeting = 'Welcome to the party sponsored by while loop, Mr.'
index = 0

while index < len(guest_names):
    print(greeting, guest_names[index])
    index += 1
```

    Welcome to the party sponsored by while loop, Mr. Leonardo DiCaprio
    Welcome to the party sponsored by while loop, Mr. Christian Bale
    Welcome to the party sponsored by while loop, Mr. Hugh Jackman
    Welcome to the party sponsored by while loop, Mr. Matthew McConaughey
    Welcome to the party sponsored by while loop, Mr. Brad Pitt
    Welcome to the party sponsored by while loop, Mr. Matt Damon
    Welcome to the party sponsored by while loop, Mr. Denzel Washington
    Welcome to the party sponsored by while loop, Mr. Russell Crowe
    Welcome to the party sponsored by while loop, Mr. Benedict Cumberbatch
    Welcome to the party sponsored by while loop, Mr. Joaquin Phoenix
    

You must be wondering when to use `for` loop and when to use `while` loop. Most of the things can be done with both types of loops, but sometimes, `for` loop is more useful, and sometimes, `while` loop. As you gather more experience, you will learn which type of loop is required in different cases. As a general note, if number of iterations is known to you, then you should use a `for` loop, and if number of iterations is not determined, but it is known that till what condition the loop will continue, you should use a `while` loop.

## The `break` and `continue` statements
In Python, `break` and `continue` are reserved keywords. They have a great application in loops (both `for` and `while`). Sometimes, we want to alter the flow of a loop. What a loop generally does? In case of `for` loop, it keeps repeating the code block a certain number of times, while in the case of `while` loop, it keeps repeating the code block until a certain testing condition is met.

### Using `break` in `for` and `while` loop
#### `break` in `for` loop
Suppose, in case of a `for` loop, we are iterating through the elements of a *list*. `for` loop will go through all the elements of the *list*, and will print them all if the code is like this given below:


```python
programming_lang = ['JavaScript', 'C', 'Python', 'Assembly', 'Perl', 'C++', 'Erlang', 'Julia']
```

Suppose I want to stop the iteration in `for` loop whenever `'Python'` comes in the list. The loop will stop whenever `'Python'` will come in the list. This can be achieved using the `break` statement.


```python
for language in programming_lang:
    print(language)    
    if language == 'Python':
        break
```

    JavaScript
    C
    Python
    

The above code checks that whenever `language == 'Python'` will be `True`, then the looping cycle will immediately end. The operation of `break` in `while` loop is also similar. 

#### `break` in `while` loop
Let's see again the general structure of a `while` loop.

```Python
while test_condition:
    # do something
```

The `while` loop will be executed as long as `test_condition` is `True`. But, if we include another `condition` with an `if` and `break` statement, then iterations in `while` loop will immediately end when `condition` is `True` irrespective of the `test_condition`. Let's see a working example to understand this better.

Suppose there is a competition going on. In that competition, everyone have to insert thread in the needle within 30 seconds. Those who will be able to complete this in time will get a normal prize. There is another option. If some player wants to challenge themselve, then they can set their own countdown time within 30 seconds. Those who will complete the challenge within their own countdown, will get bonus prizes. And if unable to complete within own set countdown time, they will get no prize. 
>*E.g.* Mark told that he will finish the challenge within 20 seconds, so the countdown timer will count upto 10 only, instead of 0. If he does it upto 10, then he will get bonus prize, otherwise no prize. 

So, we have to write a program which will print the countdown seconds in a huge display board so that audience can watch it.


```python
time = 30 # seconds
ending_time = 0
challenged_time = 10

while time > ending_time:
    if time == challenged_time:
        print("You challenged yourself to finish upto", challenged_time, "countdown.")
        break
    time = time - 1
    print(time)
```

    29
    28
    27
    26
    25
    24
    23
    22
    21
    20
    19
    18
    17
    16
    15
    14
    13
    12
    11
    10
    You challenged yourself to finish upto 10 countdown.
    

From 29 to 10, the player will get 20 seconds.

If someone is not challenging themselve and opted to complete within the normal countdown,


```python
time = 30 # seconds
ending_time = 0
challenged_time = 0    # No Challenge, so no bonus prize

while time > ending_time:
    if time == challenged_time:
        print("You challenged yourself to finish upto", challenged_time, "countdown.")
        break
    time = time - 1
    print(time)
```

    29
    28
    27
    26
    25
    24
    23
    22
    21
    20
    19
    18
    17
    16
    15
    14
    13
    12
    11
    10
    9
    8
    7
    6
    5
    4
    3
    2
    1
    0
    

They will get 30 seconds.

Now, the while loop should be in an infinite loop if the code looks like this:
```Python
while True:
    # do something
```
Because we have provided no *testing condition*, and provided `True` in place of the *testing condition*, then this loop should be executed forever. It will not exit out. It is true, but we can write `while` loop like this without letting it enter in an infinite loop if we use `break` statement.

It will be not difficult to understand with and example. We will print the natural numbers upto 5. Let us do this using the way we learnt.


```python
i = 1 # Our starting number. We will increment i by 1 after each iteration
end = 5

while i <= end:   # Loop is executed as long as (i <= end) is True
    print(i)
    i += 1        # This step is very important, otherwise (i <= end) will always remain True
```

    1
    2
    3
    4
    5
    

Here, the *testing condition* we used with `while` is `i <= end`.

Now, we will do the same thing by using `while True:` statement. But we will use the same *testing condition* in an `if` statement (but slightly modifying it), and will exit out of the loop using `break` when the `if` statement is `True`.


```python
i = 1
end = 5

while True:
    if i > end: # We used our testing condition here by slightly manipulating it
        break
    print(i)
    i += 1      # incrementing i is also necessary here, otherwise (i > end) will never be True, and loop will never break
```

    1
    2
    3
    4
    5
    

In the previous `while` loop, which do not uses `break` or `if` statement, our *testing condition* was `i <= end`. The loop will be executed as long as `i <= end` is `True`. And in the latest `while` loop, which uses `break` and `if`, our *testing condition* is just the opposite, i.e., `i > end`. The loop will **not break** as long as `i <= end` is `True`, and will break immediately if `i > end` is `True`. So either way, the logic is the same. You have to position your `print` statement accordingly. You will not get your desired output if you write the code like this.


```python
i = 1
end = 5

while True:
    print(i)    
    if i > end:
        break
    i += 1
```

    1
    2
    3
    4
    5
    6
    

Because the undesired result (`6`) will be printed just before exiting the loop. So you should work carefully. You can also write the code like this to get your desired output.


```python
i = 1
end = 5

while True:
    print(i)
    i += 1
    if i > end:
        break
```

    1
    2
    3
    4
    5
    

So, it totally depends on you how you write your code, as long as you understand the logic. 

### Using `continue` in `for` and `while` loop

#### `continue` in `for` loop
Let's continue with our `programming_lang` list.


```python
programming_lang = ['JavaScript', 'C', 'Python', 'Assembly', 'Perl', 'C++', 'Erlang', 'Julia']
```

Suppose someone hates the *Perl* programming language. So, he/she will avoid printing that language using `for` loop. We can use the `continue` statement to achieve this.


```python
for language in programming_lang:
    if language == "Perl":
        continue
    print(language)
```

    JavaScript
    C
    Python
    Assembly
    C++
    Erlang
    Julia
    

Hurray! We have successfully avoided printing `"Perl"` from our `programming_lang` list. So you must have understood what `continue` statement does. If a certain condition is `True` in a particular iteration, then that iteration is skipped immediately. So, the interpreter does not even reached the line `print(language)` when `language == "Perl"`. It is very easy. 

The `continue` statement is different from the `break` statement if you remember, because the `break` statement completely stops the execution of a loop, whereas the `continue` statement only skips a particular iteration.

#### `continue` in `while` loop
Have a look at the code below.


```python
for i in range(0, 10, 2):
    print(i)
```

    0
    2
    4
    6
    8
    

We can easily achieve this using the `while` loop.


```python
i = 0
end = 10

while i < 10:
    print(i)
    i += 2
```

    0
    2
    4
    6
    8
    

Very easy. Let's test our skills by using `continue` in the `while` loop. We will increment `i` only by `1` instead of `2`.


```python
i = 0
end = 10

while (i < end):
    i += 1
    if (i % 2 != 0):   # (i % 2) returns the remainder after dividing i by 2
        continue
    print(i-2)
```

    0
    2
    4
    6
    8
    

It is not as good as the previous one, but still it works. We showed it here to demonstrate the application of `continue` inside a `while` loop. You have to take care while using `continue` inside a `while` loop. Have a look at this.
```Python
i = 0
end = 10

while (i < end):
    if (i % 2 != 0):
        continue
    print(i)
    i += 1
```
This program will never work, and instead, it will be an infinite loop. See the step by step execution below.
1. In the first iteration, the value of `i = 0`. Since `i < end` is `True`, so, the interpreter will enter the code block of `while` loop.
2. `(i % 2 != 0)` is `False`, since the remainder of $\displaystyle{\frac{0}{2}}$ is `0`, so the interpreter will not enter inside the code block of `if` statement.
3. The value of `i` will be printed due to `print(i)`. The value of `i` is still equal to `0`, so, `0` will be printed.
4. Now, the new value of `i` is: $i = 0 + 1 = 1$.
5. The next iteration is started. `i < end` is still `True`, so interpreter will enter the code block of `while` loop.
6. Now, `i % 2 = 1`, i.e., the remainder of $\displaystyle{\frac{1}{2}}$ is $1$. So, `i % 2 != 0` is `True`. So the interpreter will enter inside the code block of `if` statement.
7. Due to `continue`, this iteration/looping cycle will be skipped. So, the lines below the `continue` will not be executed anymore in this iteration.
8. In the fresh iteration again, the value of `i` is still `1`. It was not incremented due to the `continue` statement in the previous iteration. So, this iteration will be same as the previous one. And this cycle will be continued forever. `i` can never become more than `1`. It will be an infinite loop.

So, you have to take care while incorporating `continue` inside the `while` loop.

So, this was all about loops. There are only two types of loops, `for` and `while`, but infinite number of things can be achieved using just these two types of loops.
