# Day 5

## Part 1 & 2
```python
seats = []

with open('input5') as file:
    for line in file:
        binary = str(line.replace('F', '0').replace('B', '1').replace('R', '1').replace('L','0'))
        decimal = int(binary,2)
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
