# Exercise 8.4 

> Open the file romeo.txt and read it line by line. For each line, split the line into a list of words using the split() method. The program should build a list of words. For each word on each line check to see if the word is already in the list and if not append it to the list. When the program completes, sort and print the resulting words in python sort() order as shown in the desired output.


## Theory:
- Python has the option for forming lists which can store an order of items in a single variable
- lists are iterable in a for loop

## Code:
```py
f = open(romeo.txt)
lst = list()
for line in f:
    words = line.split()
    for word in words:
        if word not in lst:
            lst.append(word)
lst.sort()
print(lst)
```

## Concepts Learnt:
- basics abput lists in python
- sorting a list (ascending/descending)
- appending a list

# Exercise 8.5 

> Open the file mbox-short.txt and read it line by line. When you find a line that starts with 'From ' like the following line: `From stephen.marquard@uct.ac.za Sat Jan  5 09:14:16 2008`
> You will parse the From line using split() and print out the second word in the line (i.e. the entire address of the person who sent the message). Then print out a count at the end.

## Theory:
- Lists starts from index 0.. ie first element at 0, second at 1 and so on
- the `.startswith()` function matches a string to a substring and returns the count

## Code:

```py
fname = input("Enter file name: ")
fhand = open(fname)

count = 0

for line in fhand:
    line = line.strip()
    if not line.startswith('From '): continue
    words = line.split()
    count+=1
    print(words[1])

print("There were", count, "lines in the file with From as the first word")
```

## Concepts Learnt:
- basics about lists in python
- converting a given text to a list
