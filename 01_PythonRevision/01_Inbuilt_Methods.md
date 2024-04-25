# Python Built-in Functions

## Backup
In case you forgot any functions for any ds or module use dir().
```python
dir(set())

import itertools
dir(itertools)

# for checking built-in functions
import builtins
print(dir(builtins))
```

## Conversions
```python
var = abs(-1) # Converts negative to positive
x = abs(3+5j) # Returns positive value of complex no i.e +5.83....
```

```python
x = bin(36) # Returns its binary Number eg 0b100100 (0b is extra)
x = int('100100',2) # Returns integer of any binary (if 0b is added, pass 0 instead of 2, python identifies it)
```

```python
x = chr(97) # Returns the character value of any ascii number eg. a
x = ord('a') # Returns the ascii number eg. 97
```

```python
x = hex(25) # Returns the hex value of the number eg. 0x19 (0x is extra)
x = int('0x19', 0) # Returns the int value of the hex eg. 25 (if 0x is not present, pass 16 instead of 0 in int function)
```

```python
x = oct(8) # Returns the octal value of the number eg. 0o10 (0x is extra)
x = int('10', 8) # Returns the int value of the octal eg. 8 (if 0o is not present, pass 8 instead of 0 in int function)
```

## For iterables like list and tuples
```python
for index, element in enumerate(arr): # Returns a tuple of index and the element
```

```python
ages = [5, 12, 17, 18, 24, 32]

def myFunc(x): # Filter callback, returns true only for elements to be stayed.
  if x < 18:
    return False
  else:
    return True

adults = filter(myFunc, ages) # Takes first filter callback function and ssecond the list to be filtered

for x in adults:
  print(x) # eg. 18 24 32

```

```python
def myfunc(a):
  return len(a)

x = map(myfunc, ('apple', 'banana', 'cherry')) # Maps any iterable into a function eg in this case returns a map of the length of each element.
# convert the map into a list, for readability:
print(list(x))
```

```python
x = reversed([1,2,3]) # Returns reverse list iter so convert to list using list()
# Instead use list.reverse() - reverses the list in place
```

```python
x = sorted([2,1,3]) # Returns sorted list iter so convert to list using list()
# Instead use list.sort() - sorts the list in place
# In both can pass reverse=True for descending list
```

```python
a = (1, 2, 3, 4, 5)
x = sum(a) # Returns the sum of any iterable eg. 15
print(max(a), min(a)) # Returns the min and max values in a list
```

```python
x = range(5) # Returns a range object, convert it to list using list() returns [0,1,2,3,4]
x = list(range(3,6)) # [3,4,5]
x = list(range(0, 12, 2)) # Increments by 2 so [0,2,4,6,8,10]
```

## Mathematical and Optional

```python
x = pow(4, 3) # Returns the value with power eg same as 4*4*4
```

```python
x = round(5.76543,2) # Rounds a number, can enter the precision eg here 5.77
```

```python
eval('print(5)') # Evaluate the expression eg. in this case print
```

```python
matrix = [[1,2,3],[4,5,6],[7,8,9]]
matrix = [list(row) for row in zip(*matrix)] # Transposing a matrix

# For rotating matrix, transpose it and just reverse every row
matrix = [row[::-1] for row in matrix]

# For spiral matrix, print the row, pop it, transpose and reverse it.

while matrix:
    print(*matrix.pop(0), end = " ")
    matrix = [list(row) for row in zip(*matrix)][::-1]
```