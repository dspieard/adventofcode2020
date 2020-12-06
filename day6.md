# Day 6
## Part 1
```python
total = 0
with open('input6') as file:
    data = file.read()
    split = data.split("\n\n")
    for l in split:
        questions_yes = []
        temp = l.replace('\n', '')
        for character in temp:
            questions_yes.append(character)
        questions_yes_without_dup = set(questions_yes)
        total += len(questions_yes_without_dup)
print(total)
```

## Part 2
```python
total = 0
with open('input6') as file:
    data = file.read()
    split = data.split("\n\n")
    for l in split:
        questions_yes = []
        lines = l.split('\n')
        temp = l.replace('\n', '')
        for character in temp:
            questions_yes.append(character)
        answers_per_question = {i: questions_yes.count(i) for i in questions_yes}
        for key in answers_per_question:
            if answers_per_question[key] == len(lines):
                total += 1
print(total)
```
