**Dev:** *LYencken*  
**Date:** *8.22.2020*

# Title 
## Structured error handling (try - except)
## Introduction
##### In this assignment we learnt how to use 'error handling' and 'Pickle' for Python.


## Topic 1
##### When using Python error handling can be used to ensure that traceback errors occur because of bugs. Bugs can be caused by such things as dividing by zero, inccorect user input or for this assignment using pickl reading the end of the file which will cause a traceback error. to use 'try-except' we must capture the block of code where the error is occuring. for example if we have a block of code that ask for user input with a script that uses division then dividing by zero will cause a error. To stop this occuring because a try-except using "ZeroDivisionError". This can return a print message such as "cannot divide by zero". An example of this is as seen in Fig 1 "Structured error handling for division by zero".
```
try:
    x = int(input("enter a number: "))
    y = int(input("enter a number: "))
    num = (x/y)
    print(num)

except ZeroDivisionError:
    print(" cannot divide by zero ")
```    
##### Fig 1: Structured error handling for division by zero

![Structured error handling for division by zero](https://github.com/louisY95/-ITFnd100--Mod07-/blob/master/DivisionBy%20Zero.PNG "Structured error handling for division by zero") ####
##### Figure 2: Structured error handling for division by zero

### Subtopic
## Summary
