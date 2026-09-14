# Exercise 2.2

>Write a program that uses input to prompt a user for their name and then welcomes them. Note that input will pop up a dialog box. Enter Sarah in the pop-up box when you are prompted so your output will match the desired output.

## Theory: 
- Taking input from a user using `input()` command..
- Printing the output using `print()`

## Code: 
```py
# The code below almost works
name = input("Enter your name")
print("Hello "+name)
```

## Concepts Learnt 
- How to take input from users
- printing variables

# Exercise 2.3 

>Write a program to prompt the user for hours and rate per hour using input to compute gross pay. Use 35 hours and a rate of 2.75 per hour to test the program (the pay should be 96.25). You should use input to read a string and float() to convert the string to a number. Do not worry about error checking or bad user data.

## Theory:
- Taking a specific data type as input using input() wrapped in data_type()
- Basic calculation using user-input

## Code:
```py
# This first line is provided for you

hrs = float(input("Enter hours: "))
rate = float(input("Enter rate: "))
pay = rate * hrs
print("Pay:", pay)
```

## Concepts Learnt:
- not every input taken by `input()` works for arithmetic
- Only valid datatype works with a specific types of input
