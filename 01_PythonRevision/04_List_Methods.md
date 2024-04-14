# List methods in python

## Searching

```python
lst = [1,2,3,3,4,4,5,5]
x = lst.count(3) # Returns the count of the element inside the list
```

```python
lst = [1,2,3,4]
lst.index(3) # Returns the index of the value passed. Time Complexity: O(n) | Try Binary Search for sorted list.
```



## Adding
```python
lst = []
lst.append(3) # Adds element to the list
```

```python
lst = [1,2,4,5]
lst.insert(2, 3) # Adds element to the list at specific index or position "insert(index, value)"
```

```python
lst1 = [1,2,3]
lst2 = [4,5]
lst.extend(lst2) # Adds another list to the end eg. lst1 = [1,2,3,4,5]
```

## Removing

```python
lst = [1,2,3,4,5]
lst.pop(1) # Removes element from the list at specific index, default is last value
```

```python
lst = [1,2,3]
lst.remove(3) # Removes specific element from the list
```




## Extra Useful

```python
lst = []
lst.sort() # Sorts the list in place. Time Complexity: O(nlogn)
```

```python
lst = []
lst.reverse() # Reverses the list in place. Time Complexity: O(n)
```

```python
lst = []
lst.clear() # Clears the list
```

```python
lst = []
lst2 = lst.copy() # Makes a copy of the list (Important when passing in functions)
```
