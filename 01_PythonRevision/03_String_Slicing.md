# String Slicing

we will cover 2 methods of string slicing, one using the in-build slice() method and another using the [:] array slice. String slicing in Python is about obtaining a sub-string from the given string by slicing it respectively from start to end.

Indices for iterating string straight and in reverse
![String Indices](https://media.geeksforgeeks.org/wp-content/uploads/20191220092949/slice.jpg)

## Method 1: Using the slice() method

The slice() constructor creates a slice object representing the set of indices specified by range(start, stop, step).

### Syntax:

- slice(stop)
- slice(start, stop, step)

Eg.
```python
string = "Morning"
s1 = slice(3) # slice(first_n_characters)
print(String(s1)) # Need to use String class. Out: Mor

s2 = slice(1, 5, 1) # slice(start[exclusive], end[includive], step)
print(String(s2)) # Need to use String class. Out: orni
```

## Method 2: Using the List/array slicing  [ :: ]  method
Prefer using this method instead of slice.

This is an easy and convenient way to slice a string using list slicing and Array slicing both syntax-wise and execution-wise.

```python
text = "Morning"

# text[start:] removes first n characters
# Mo : rning ✓
print(text[2:]) # Output : rning


# text[:end] returns first n characters
# ✓ Mo : rning
print(text[:2]) # Output : Mo


# text[start:end] returns substring between start and end
# Mo(2) : rni(5)✓ : ng
print(text[2:5]) # Output : rni


# text[start:end:step] returns substring between start and end jumping over n steps
# M✓ - o - r✓ - n - i ✓
print(text[0:5:2]) # Output : Mri | Starts from start and jump to step until end


# text[::-1] reverse the string
print(text[::-1]) # Output : gninroM
```

## Use cases
- Reverse a string
- Rotate a string (slice for first part, then second then concate according to left or right rotate)
- Get substring
- Slicing list from Kth element to last