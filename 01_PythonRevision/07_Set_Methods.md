# Set methods in Python

A set is a collection which is unordered, unchangeable*, and unindexed.
Note: Set items are unchangeable, but you can remove items and add new items.

Sets are written with curly brackets.
```python
thisset = {"apple", "banana", "cherry"}
```
## Basic Operations
```python
fruits = {"apple", "banana", "cherry"}
fruits.add("orange") # Adds elements to set
```

```python
fruits = {"apple", "banana", "cherry"}
fruits.discard("banana") # Removes item from set (no error is not present)
fruits.remove("banana") # Removes item from set (error is item not present)
fruits.pop() # Removes random item from set
```

```python
fruits = {"apple", "banana", "cherry"}
fruits.clear() # Clears the set
```

```python
fruits = {"apple", "banana", "cherry"}
x = fruits.copy() # Copies a set to another variable
```

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

x.update(y) # Extends set x with set y(Adds set y to set x)
```


## Boolean Methods
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "facebook"}

z = x.isdisjoint(y) # Return True if both sets are different(no common elements)

# Answer : True
```

```python
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}

z = x.issubset(y) # Returns true if set y is subset of set x
```

```python
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}

z = y.issuperset(x) # Returns true if set y is superset of set x
```


## Set Operations

### Intersection
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.intersection(y) # Return a set that contains the items that exist in both set x, and set y
z = x & y # Alternate Syntax

# Answer: {'apple'}
```

### Union
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.union(y) # Return a set that contains all items from both sets, duplicates are excluded
z = x | y # Alternate Syntax

# Answer: {'google', 'banana', 'apple', 'microsoft', 'cherry'}
```

### Difference

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.difference(y) # Return a set that contains the items that only exist in set x, and not in set y
z = x-y # Alternate syntax

# Answer : {'cherry', 'banana'}
```

### Symmetric Difference
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.symmetric_difference(y) # Return a set that contains all items from both sets, common items discarded
z = x ^ y # Alternate Syntax

# Answer: {'google', 'cherry', 'banana', 'microsoft'}
```
