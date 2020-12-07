# Day 7
## Part 1 & 2

```python
bags = {}
total = 0
count = 0

with open('input7') as file:
    for line in file:
        dict = {}
        find_first_bag = line.split(' ')
        bag = f"{find_first_bag[0]} {find_first_bag[1]}"

        line= line.strip()
        remove_dot = line.replace('.', '')
        contains = remove_dot.split('contain', 1)
        other_bags = contains[1]
        other_bags = other_bags.split(',')
        for other_bag in other_bags:
            if other_bag != ' no other bags':
                other_bag_split = other_bag.split(' ')
                other_bag = f"{other_bag_split[2]} {other_bag_split[3]}"
                dict[other_bag]= other_bag_split[1]
        bags[bag] = dict


def shinie(bag):
    if bag == 'shiny gold':
        return True
    else:
        for bag in bags[bag]:
            if shinie(bag):
                return True
    return False


def bags_in_shinie(shinie):
    global count
    for bag in bags[shinie]:
        times = int((bags[shinie][bag]))
        count += times
        i = 0
        while i < times:
            bags_in_shinie(bag)
            i += 1


# Part 1
for bag in bags:
    if shinie(bag):
        total += 1
print(f"Part 1: {total -1}")

# Part 2
for bag in bags:
    if bag == 'shiny gold':
        bags_in_shinie(bag)
print(f"Part 2: {count}")
```
