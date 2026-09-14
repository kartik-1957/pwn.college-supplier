# Exercise 10.2 

>Write a program to read through the mbox-short.txt and figure out the distribution by hour of the day for each of the messages. You can pull the hour out from the 'From ' line by finding the time and then splitting the string a second time using a colon.Once you have accumulated the counts for each hour, print out the counts, sorted by hour as shown below.

## Theory:
- Tuples are a immutable collection of items unlike lists
- `items()` command returns a list of tuples from a dictionary 

# Code:
```py
name = input("Enter file:")
if len(name) < 1:
    name = "mbox-short.txt"
handle = open(name)
counts = {}
for line in handle:
    if not line.startswith('From '): continue
    words = line.split()
    time = words[-2]
    timeSplit = time.split(":")
    hour = int(timeSplit[0])
    counts[hour] = counts.get(hour, 0) + 1
    
for key in sorted(counts):
    if key < 10: print("0"+str(key)+" "+str(counts.get(key)))
    else: print(key, counts.get(key))
```
## Concepts Learnt:
- basic concepts about tuples in python
- basic commands related too tuples
