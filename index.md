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
##### Pickle was also used in this assignment. Pickle is by definition from the Python website (link) https://docs.python.org/3/library/pickle.html#:~:text=%E2%80%9CPickling%E2%80%9D%20is%20the%20process%20whereby,back%20into%20an%20object%20hierarchy." “Pickling” is the process whereby a Python object hierarchy is converted into a byte stream, and “unpickling” is the inverse operation, whereby a byte stream (from a binary file or bytes-like object) is converted back into an object hierarchy". Python is a useful module which ensures consistency between user sessions and helps ensure that there will be no corrupt files... This means it can be reloaded on other servers and still have its integrity intact. Pickle cannot be used on other programmiing languages as it is only compatible to Python. 

##### To use Pickle you must first import the Pickle module as seen in Fig 4. After this any data input is then converted into characters and stored into the file using 'pickle.dump'. As seen in Fig 5 there is a "random" string of characters which have been dumped into the '.dat' file. To be able to read this string we need to de-serialize the file by using '.load' which will load one string of data. A way to load all data would to be to use a while loop and to break the loop we could use the error handling for EOFError which would break the loop. For this Assignment though I've kept it with loading only one line. 


![Running Command Prompt](https://github.com/louisY95/-ITFnd100--Mod07-/blob/master/Running%20in%20command%20prompt.PNG "Running Command prompt") ####
