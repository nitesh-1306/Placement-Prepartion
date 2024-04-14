# Datetime Module in Python

## Difference of days between 2 dates
```python
from datetime import datetime
date1 = datetime(2023, 4, 10)
date2 = datetime(2023, 5, 15)

difference = date2 - date1
print(difference.days)
```

## Checking Leap Year
```python
import calendar
if calendar.isleap(2024):
    print("Leap year")
```

## Checking Next Leap Year
```python
import calendar
year = 2024
while True:
    year += 1
    if calendar.isleap(year):
        print("Next leap year:", year)
        break
```


## Getting day for the date
```python
from datetime import datetime
date = datetime(2023, 4, 10)
day = date.strftime("%A")

'''
Strftime queries:
%A - Dayname (Wednesday)
%B - Monthname (December)
%Y - Year (2024)
'''
```