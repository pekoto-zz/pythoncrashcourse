# Python Crash Course

## Strings

### Interpolation

_Python 3: Use f_

```python
name = 'Graham'
print(f'Hello, {name}')
```

_Python 2: Use .format()_

```python
first_name = 'graham'
last_name = 'mc'
print('Hello, {} {}'.format(first_name, last_name))
```

## Numbers

### Exponents

```python
print(2**3)
# prints 8
```

### Division

Integer division will __ALWAYS__ return a float.

```python
print(3/2)
# prints 1.5

```

## Constants

There is no constant type, but constants are conventionally written in all-caps.

```python
MAX_CONNECTIONS = 48
```

## Comments

Comments use #

```python
# This is a comment.
print('hi')
```

## Lists

Lists are declared with __[ ]__

* append(elem)
* insert(pos, elem)
* del[index]
* pop()
* pop(index)
* remove(elem)

```python
a_list = ['tea', 'coffee', 'sugar']

# 'tea'
print(a_list[0])

# 'sugar'
print(a_list[-1])

# .append(elem): add an element to the end of the list
a_list.append('biscuits')

# .insert(pos, elem): insert an element at a specific position in the list
# ['tea', 'strawberries', 'coffee', 'sugar', 'biscuits']
a_list.insert(1, 'strawberries')

# del[index]: remove an element at a specific index
# ['tea', 'coffee', 'sugar', 'biscuits']
del a_list[1]

# pop(): remove and return the last element in the list
# ['tea', 'coffee', 'sugar']
last_item = a_list.pop()

# pop(index): remove and return the element at index
# ['coffee', 'sugar']
first_item = a_list.pop(0)

# remove(elem): remove the (first) occurrence of elem
# ['coffee]
a_list.remove('sugar')
```

### Sorting lists

* .sort(): sort in place
* .sort(reverse=True): sort backwards
* sorted(list): sort copy
* .reverse(): reverse list order
* len(list): get length of the list

```python
a_list = ['c', 'a', 'b']

# .sort(): Sort list in place
# ['a', 'b', 'c']
a_list.sort()

# .sort(reverse=True): Sort reverse in place
# ['c', 'b', 'a']
a_list.sort(reverse=True)

# sorted(list): sorted copy
sorted_list = sorted(a_list)

# reverse: reverses the list order
# ['a', 'b', 'c'] > ['c', 'b', 'a']
a_list.reverse()

# len(list): get the length of a list
print(len(a_list))
```

### Loops

* Iterate: for ... in ...:

```python
a_list = ['c', 'a', 'b']

# loop: for elem in data_struct:
#           operation
for letter in a_list:
    print(letter)

```

### Range

* range(start, end): list of numbers from start to end (exclusive)
* list(range(start, end)): create list from start to end (exclusive)
* range(start, end, step): create list from start to end with step interval (exclusive)

```python
# range(start, end): make list from start to end (exclusive)
# prints 1, 2, 3, 4
for num in range(1, 5):
    print(num)

# range: can also be used to create lists
one_to_four = list(range(1, 5))

# range(start, end, step): The 3rd argument specifies step size.
# [2, 4, 6, 8, 10]
two_step = list(range(2, 11, 2))

```

### Helper functions

* max
* min
* sum

```python
# min: min value
min(two_step)

# max: max value
max(two_step)

# sum: sum list
sum(two_step)
```

### Comprehensions

```python
# comprehension: create list in single line
squares = [value**2 for value in range(1, 11)]
print(squares)
```

### Slicing

* list[start, end]: take elements from start to exclusive end -- like first 'end' items
* list[-start:]: get list start items in list

```python
letters = ['a', 'b', 'c', 'd', 'e']

# slice[start, end]: slicing is EXCLUSIVE
# ['b', 'c']
print(letters[1:3])

# slice[:end]: start to exclusive end (like, first n)
# ['a', 'b', 'c']
print(letters[:3])

# slice[start:]: start to end
# ['b', 'c', 'd', 'e']
print(letters[1:])

# slice[-n:]: last n elements in the list
# ['c', 'd', 'e']
print(letters[-3:])

# copy = my_list[:]: create a copy of the list
letters_copy = letters[:]
```

## Tuples 
Tuples are declared with __( , )__ (precisely, only the comma is needed). Tuples are immutable.

```python
points = (100, 300)

for point in points:
    print(point)

```

## Conditionals

* Use 'and' and 'or
* if ... :
* elif: else...if...
* if val in...: check if item in a list
* if val not in...: check if item not in a list
* if list: check if list not empty


```python
num = 10

# Use 'and'
# True
if (num > 0) and (num <= 10):
    print(True)
else:
    print(False)

# Use 'or'
# True
if (num != 0) or (num == 9):
    print(True)
else:
    print(False)

users = ['a', 'b', 'c']

# in: check element in list
if 'a' in users:
    print(True)
else:
    print(False)

# not in: check if element not in list
if 'z' not in users:
    print('New user')
else:
    print('Existing user')

# Use elif for else if
# 'You are on the way out'
age = 100

if age < 10:
    print('You are young')
elif age < 27:
    print('You are still pretty young')
else:
    print('You are on the way out')

# use if list to check if a list is not empty
# 'Whew. No errors.'

errors = []

if errors:
    print('There are errors!')
else:
    print('Whew. No errors')
```

## Methods vs. Functions

* Methods = for classes
* Functions = not part of class

## WSGI

__Web Server Gateway Interface__ (WSGI, pronounced _whisky_). A calling convention for web servers to forward requests to web applications written in Python. So applications written in different Python web frameworks can run on the same web server. If WSGI didn't exist, when they chose a Python web framework, they would be limited in the choice of web servers they could run their application on.

WSGI was created as an interface between web servers and web applications.

### Gunicorn

Green Unicorn. A Python WSGI server.

