# Day 4
## Part 1
```python
total = 0
with open('input4') as file:
    data = file.read()
    split = data.split("\n\n")
    for l in split:
        passport = {}
        temp = l.replace('\n', ',')
        string = temp.replace(' ', ',')
        key_value = string.split(",")

        for v in key_value:
            aux = v.split(":")
            passport[aux[0]] = aux[1]

        if 'cid' in passport.keys():
            del passport['cid']
        if len(passport) == 7:
            print(passport)

            total += 1
print(total)
```
## Part 2
```python
import re


def checkbyr(byr):
    if 1920 <= int(byr) <= 2002:
        # print(byr)
        return True


def checkiyr(iyr):
    if 2010 <= int(iyr) <= 2020:
        # print(iyr)
        return True


def checkeyr(eyr):
    if 2020 <= int(eyr) <= 2030:
        # print(eyr)
        return True


def checkhgt(hgt):
    split = re.split('(\d+)', hgt)
    if split[2] == 'cm' and 150 <= int(split[1]) <= 193:
        return True
    elif split[2] == 'in' and 59 <= int(split[1]) <= 76:
        return True
    else:
        return False


def checkhcl(hcl):
    match = re.search(r'^#(?:[0-9a-f]{3}){1,2}$', hcl)
    if match:
        return True


def checkecl(ecl):
    a = ['amb', 'blu', 'brn', 'gry', 'grn', 'hzl', 'oth']
    if ecl in a:
        return True


def checkpid(pid):
    if len(pid) == 9 and pid.isdigit():
        return True


total = 0
with open('input4') as file:
    data = file.read()
    split = data.split("\n\n")
    for l in split:
        passport = {}
        temp = l.replace('\n', ',')
        string = temp.replace(' ', ',')
        key_value = string.split(",")

        for v in key_value:
            aux = v.split(":")
            passport[aux[0]] = aux[1]

        if 'cid' in passport.keys():
            del passport['cid']
        if len(passport) == 7:
            byr = checkbyr(passport['byr'])
            iyr = checkiyr(passport['iyr'])
            eyr = checkeyr(passport['eyr'])
            hgt = checkhgt(passport['hgt'])
            hcl = checkhcl(passport['hcl'])
            ecl = checkecl(passport['ecl'])
            pid = checkpid(passport['pid'])
            if byr and iyr and eyr and hgt and hcl and ecl and pid:
                total += 1

print(total)
```
