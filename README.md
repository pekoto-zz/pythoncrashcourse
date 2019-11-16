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

## Numbers

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
