# Day 1

## Part 2
```
list = []
with open('input') as file:
    for line in file:
        list.append(int(line.strip()))

for a in range(len(list)):
    for b in range(len(list)):
        for c in range(len(list)):
            if list[a]+list[b]+list[c] == 2020:
                num1 = list[a]
                num2 = list[b]
                num3 = list[c]
sum = num2 * num1 * num3
print(sum)
```


