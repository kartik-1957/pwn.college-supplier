# Finding Numbers in a Haystack

> In this assignment you will read through and parse a file with text and numbers. You will extract all the numbers in the file and compute the sum of the numbers.

## Theory:
- regex module can be imported using `import re`. This is cruicial for us to import the module before writing the code.
- using the command `r'...'` converts a string to the raw string, which is useful for regex methods (RegEx = regular expressions)
- Using Regex makes searching much more easier for complex searches..

## Code:

```py
import re
fname = "regex_sum_2470668.txt"
fhand = open(fname)

total = 0

for line in fhand:
    numbers = re.findall(r'[0-9]+', line)
    for num in numbers:
        total += int(num)

print(total)
```

- Final answer: `457295`

## Concepts Learnt:
- How to write regular expressions in Python 
- Using regex methods to make searching within large files simpler and more efficient
