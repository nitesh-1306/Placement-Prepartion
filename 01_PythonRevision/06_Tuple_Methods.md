# Tuple Methods in Python

In Python, a tuple is a collection of items, just like a list, but it is immutable, meaning its elements cannot be changed after creation. Tuples are created using parentheses (), and elements are separated by commas. Unlike lists, tuples cannot be modified, which makes them suitable for storing data that should not be changed.

It has just 2 methods

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)
x = thistuple.count(5) # returns the count of specific element
print(x)
```

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)
x = thistuple.index(5) # returns the index of specific element
print(x)
```