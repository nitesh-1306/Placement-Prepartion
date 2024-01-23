# Python Code and Notes

Here's a Python script with comments explaining various string and list operations.


# Define two strings
```python
test = "Hello,World"
test2 = " testtest "
```

# String slicing
```python
print(test[6:11])  # index 5 inclusive and 10 exclusive | works on strings and lists
```

# String method: strip
```python
print(test2.strip())  # Remove trailing and leading whitespaces
```

# String method: split
```python
x = test.split(',')
print(x)  # Splits string into a list | nothing passed means space else the delimiter
```

# String method: join
```python
separator = '-'
res = separator.join(x)
print(res)  # The values will be joined, and a separator will be added
```

# String method: find
```python
print(test.find("World"))  # Finds a substring in the string and returns the starting index, else -1
```

# String method: count
```python
print(test.count('l'))  # Counts the occurrence of a character in the string
```

# List operations
```python
x.append("How")  # Adds a new element
print(x)

y = ['are', 'you']
x.extend(y)  # Joins two lists
print(x)

x.insert(1, "Bloody")  # Adds an element at a specific index
print(x)

x.remove("World")  # Removes the first occurrence
x.pop(1)  # Removes an element at a specific index
print(x)

z = [3, 6, 1, 3, 7, 2, 5, 8]
z.sort(key=None, reverse=False)  # Sorts the list, key is the criteria of sorting, e.g., len
print(z)
print(z.count(3))  # Returns the count of an element in the list
z.reverse()  # Reverses the list
print(z)
```

# Enumerate a list with starting index
```python
for key, ele in enumerate(x, 1):
    print(f'{key}] {ele}')
```

# Filter elements based on a function
```python
ages = [5, 12, 17, 18, 24, 32]
def myFunc(x):
  if x < 18:
    return False
  else:
    return True

adults = filter(myFunc, ages)   # Passes values to the function; if true, return that value
for x in adults:
  print(x)
```

# List operations: sum, max, min
```python
print(sum(ages))  # Sum of the integer list
print(max(ages), min(ages))  # Prints the max and min values inside a list
```