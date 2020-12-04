# Day 3
## Part 1
```python
grid = []
with open('input3') as file:
    linelist = file.readlines()
    count = linelist[len(linelist) - 1]

with open('input3') as file:
    for line in file:
        x = list(line)
        if line != count:
            x.remove(x[-1])
        grid += [x]

x = 0
trees = 0

for line in grid:
    if line[x % len(line)] == '#': trees += 1
    x += 3

print(trees)
```
## Part 2
```python
grid = []
with open('input3') as file:
    linelist = file.readlines()
    count = linelist[len(linelist) - 1]

with open('input3') as file:
    for line in file:
        x = list(line)
        if line != count:
            x.remove(x[-1])
        grid += [x]


def count_trees(steps, slopes):
    count = 1
    x = 0
    tree = 0
    for line in grid:
        count += 1
        if count % slopes == 0:
            if line[x % len(line)] == '#': tree += 1
            x += steps
    return tree


total = count_trees(3, 1) * count_trees(1, 1) * count_trees(5, 1) * count_trees(7, 1) * count_trees(1, 2)
print(total)
```
