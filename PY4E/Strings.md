# Exercise 6.5 

>Write code using find() and string slicing (see section 6.10) to extract the number at the end of the line below. Convert the extracted value to a floating point number and print it out.

## Theory:
- the find() searches a string for a matching substring and returns its position
- String Slicing can be done as string[start:end:step]

## code:
```py
text = "X-DSPAM-Confidence:    0.8475"
pos = text.find(":")
text = text[pos+1:]
value = float(text.strip())
print(value)
```
## Concepts Learnt:
- searching a string
- slicing a string 
