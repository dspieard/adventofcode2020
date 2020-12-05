# Day 5

## Part 1 & 2
```python
seats = []

# https://www.geeksforgeeks.org/binary-decimal-vice-versa-python/
def binaryToDecimal(binary):
    binary = int(binary)
    decimal, i, n = 0, 0, 0
    while (binary != 0):
        dec = binary % 10
        decimal = decimal + dec * pow(2, i)
        binary = binary // 10
        i += 1
    return decimal


with open('input5') as file:
    for line in file:
        line = line.strip()
        binary = str(line.replace('F', '0').replace('B', '1').replace('R', '1').replace('L','0'))
        decimal = binaryToDecimal(binary)
        seats.append(decimal)

# Part 1
seats.sort()
print(f"Highest seadID: {max(seats)}")
# Part 2
minseatid = min(seats)
for id in seats:
    if id + 1 not in seats and id != max(seats):
        print(f"My seatID: {id +1}")
```
