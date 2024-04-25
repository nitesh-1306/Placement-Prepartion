# Collections Module Python

## Counter

```python
from collections import Counter

test = [1,2,3,41,2,3,4,12,3]
test = Counter(test) # Converts list into a dict of counts of each element
print(dict(test))
```

## Deque

```python
from collections import deque

# Double Ended queue (Useful for array k rotations)

test = deque([1,2,3,41,2,3,4,12,3])
test.append(5)
test.appendleft(6)
test.extend([1,2,3])
test.extendleft([5,6,7])
test.pop()
test.popleft()
test.rotate(2)
print(list(test))
```