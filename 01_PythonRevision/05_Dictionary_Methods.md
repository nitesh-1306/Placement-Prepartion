# Dictionary methods in python

## Searching

```python
lst = {
    "name": "Test"
}
x = lst.get("name") # Returns the value of the key from dictionary
```

```python
lst = {
    "name": "Test"
}
x = lst["name"] # Returns the value of the key from dictionary
```



## Adding
```python
dct = {}
dct["name"] = "Test" # Adds element to the dictionary
```


## Removing

```python
lst = {
    "name": "Test",
    "age": 2
}
lst.pop("age") # Removes element from the list at specific key
```

```python
lst = {
    "name": "Test",
    "age": 2
}
lst.popitem() # Removes last key-value pair eg. in this case "age"

# In versions before python 3.7, the popitem() method removes a random item.
```




## Extra Useful

```python
dct = {}
pairs = list(dct.items()) # Returns a list of tuples of key and value pairs eg. [(1,1),(2,2)] | Use list funtion to make it a list
```
```python
dct = {}
keys = list(dct.keys()) # Returns a list of keys eg. [1,2] | Use list funtion to make it a list
```
```python
dct = {}
keys = list(dct.values()) # Returns a list of keys eg. [3,4] | Use list funtion to make it a list
```

```python
dct = {}
dct.clear() # Clears the list
```

```python
keys = [1,2,3]
dct = dict.fromkeys(keys, 0) # .fromkeys(keyslist, value) initializes a dictionary with set of keys and a fix value for all
```

```python
dct = {}
dct.clear() # Clears the list
```

```python
dct = {
    "name" : "Test"
}
dct2 = dct.copy() # Makes a copy of the list (Important when passing in functions)
```