---
title: "`isinstance` vs `type` and `==` vs `is`"
author: "Deven Mistry"
date: "2022-11-18"
categories: [python]
---

There are multiple ways in Python to achieve a single task and at times you can get away with implementing things the wrong way and getting the correct answer.

This TIL has come into existence as I struggled with a issue that I was trying to fix at work.

## `isinstance` vs `type`

We've all used the `type` and the `isinstance` method at some point in our functions.

```py
s = 'foo'
if type(s) == str:
    print('this variable is of string type')

if isinstance(s, str):
    print('this variable is of string type')
```

If you were to execute this code, you would get the same output.

But what's the difference between them?

`instance` can check types of even derived classes (meaning, it is intended to be used in cases involving inheritence) whereas `type` is not.

TLDR; [^1]

```py
class Person: pass

class Student(Person): pass


isinstance(Person(), Person)        # returns True
type(Student()) == Student          # returns True
isinstance(Student(), Person)       # returns True
type(Student()) == Person           # returns False, and this probably won't be what you want.
```

There's a similar confusion between `is` and `==`.

## `is` vs `==`

`is` looks for the same object (in memory), whereas `==` looks for the values referred by the variables.

TLDR; [^2]

```py
n = 5
if n == 5: print('Yep!')    # prints Yep!
if n is 5: print('Yay!')    # prints Yep!

L = []
L.append(1)

if L == [1]: print('Yay!')  # prints Yep!
if L is [1]: print('Yay!')  # prints nothing
```


[^1]: [differences between type() and isinstance()?](https://stackoverflow.com/questions/1549801/what-are-the-differences-between-type-and-isinstance)
[^2]: [difference between "==" and "is"?](https://stackoverflow.com/questions/132988/is-there-a-difference-between-and-is)

H/T to [Zach Mueller](https://github.com/muellerzr) for helping me understand this