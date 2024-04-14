# String Methods in Python

Strings are immutable.

## Formatting and Casing

```python
x = "hello, nice to meet you".capitalize() # Capitalizes the first letter here only 'h' becomes 'H', rest all converted to lower
```

```python
x = "HELLO".casefold() # Converts to lowercase like lower() but more characters
```

```python
txt = "#".lower() # Converts to lowercase
```

```python
txt = "Nice".upper() # Converts to Uppercase
```

```python
x = "   banana  ".strip() # removes any leading, and trailing whitespaces
```

```python
x = "Hello".swapcase() # Swaps cases, lower case becomes upper case and vice versa
```

## Checking Values

```python
x = 'hello'.endswith('o') # Returns True if ends with the value passed else false.
```
```python
x = 'hello'.startswith('h') # Returns True if starts with the value passed else false.
```

```python
x = 'hello'.count("l") # Returns the count of specific sub string eg. 2
```

```python
txt = "Morning".isalpha() # Returns True or False based on if the string has all characters in alphabets i.e a-z.
```

```python
txt = "Morning".isdigit() # Returns True or False based on if the string has all numbers
```

```python
txt = "morning".islower() # Returns True or False based on if the string is lowercase
```

```python
txt = "MORNING".isupper() # Returns True or False based on if the string is uppercase
```

## Manipulating Strings

```python
nums = [1,2,3]
txt = "#".join(nums) # Joins the iterable elements with a separator in quotes eg. 1#2#3 | if no separator then just concat
```

```python
txt = "Nice".replace('N','Thr') # Replaces the value with provided one
```

```python
txt = "welcome to the jungle"
x = txt.split() # Split a string into a list where each word is a list item
```

## Searching
```python
txt = "Hello, welcome to my world.".find("welcome") # Returns the index at which the value starts which is present else returns -1
```

```python
txt = "Hello, welcome to my world.".index("welcome") # Returns the index at which the value starts which is present else returns error
# use .find() method instead.
```