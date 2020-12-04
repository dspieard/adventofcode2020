# Day 2
## Part 1
```python
total = 0
with open('input2') as file:
    for line in file:
        line = line.strip()
        split_string = line.split(' ', 3)
        range = split_string[0]
        character = split_string[1].replace(':','')
        password = split_string[2]

        split_range = range.split ('-', 1)
        start_range = int(split_range[0])
        end_range = int(split_range[1])

        count = 0
        for option in password:
            if option == character:
                count += 1
        if start_range <= count <= end_range:
            total += 1
print (total)
```
## Part 2
```python
total = 0

with open('input2') as file:
    for line in file:
        line = line.strip()
        split_string = line.split(' ', 3)
        range = split_string[0]
        character = split_string[1].replace(':', '')
        password = split_string[2]

        split_range = range.split('-', 1)
        start_range = int(split_range[0])
        end_range = int(split_range[1])

        c1 = password[start_range - 1]
        c2 = password[end_range - 1]

        if c1 == character or c2 == character:
            if c1 != c2:
                total += 1

print(total)
```

