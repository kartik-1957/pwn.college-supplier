# Exercise 9.4 

>Write a program to read through the mbox-short.txt and figure out who has sent the greatest number of mail messages. The program looks for 'From ' lines and takes the second word of those lines as the person who sent the mail. The program creates a Python dictionary that maps the sender's mail address to a count of the number of times they appear in the file. After the dictionary is produced, the program reads through the dictionary using a maximum loop to find the most prolific committer.

## Theory:
- How to create an empty dictionary using `{}`
- the `dict.get()` command takes two arguments: a key, and a default value if key is not found
- `counts.items()` command returns a list of key-value pairs.. You can assign them to each other.

## Code:
```py
name = input("Enter file:")
if len(name) < 1:
    name = "mbox-short.txt"
handle = open(name)
counts = {}
for line in handle:
    if not line.startswith('From '): continue
    words = line.split()
    email = words[1]
    counts[email] = counts.get(email, 0) + 1
    
bestCount = None
bestKey = None
    
for key, val in counts.items():
    if bestCount is None or val > bestCount:
        bestKey = key
        bestCount = val

print(bestKey, bestCount)
```
## Concepts Learnt:
- basics about dictionariess
- basic commands related to dicktionaries like `dict.get()`, `count.items()` etc
