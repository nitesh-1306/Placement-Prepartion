# Itertools Module Python

## Combinations
```python
# Generates all possible combinations of specified length from an iterable
print(list(itertools.combinations('ABCD', 2)))  # [('A', 'B'), ('A', 'C'), ('A', 'D'), ('B', 'C'), ('B', 'D'), ('C', 'D')]

```

## Permutations

```python
# Generates all possible permutations of specified length from an iterable
print(list(itertools.permutations('ABCD', 2)))  # [('A', 'B'), ('A', 'C'), ('A', 'D'), ('B', 'A'), ('B', 'C'), ('B', 'D'), ('C', 'A'), ('C', 'B'), ('C', 'D'), ('D', 'A'), ('D', 'B'), ('D', 'C')]

```

## Chain

```python
# Chains together several iterables into one long iterable
print(list(itertools.chain([1, 2], ['a', 'b'])))  # [1, 2, 'a', 'b']
```