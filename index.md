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
```
# ------------------------------------------------- #
# Title: Lab7-1
# Description: A simple example of storing data in a binary file
# ChangeLog: (Who, When, What)
# <LYencken>,<8/18/2020>,Created Script
# ------------------------------------------------- #
import pickle  # This imports code from another code file!

# Data -------------------------------------------- #
file_name = 'AppData.dat'
lstCustomer = []
strChoice = ""

# Processing -------------------------------------- #


def save_data_to_file(file_name, list_of_data):
    # TODO: Add code here
    """ Saves string data to a file
    :param data: (string) with data to save
    :param file_name: (string) with name of file
    :return: nothing
    """
    with open(file_name, "w") as file:  # using the WITH option
        file.write(data + "\n")
    file.close() # with automatically closes the file

def read_data_from_file(file_name):
    # TODO: Add code here

    """ Reads rows of data data from a file into a list
    :param file_name: (string) with name of file
    :return: (list) of data rows read from the file
    """
    data = [] # you must initialize the list variable before you use it
    for row in open(file_name, 'r'):
        data.append(row) # read one row of data in the file per loop
        # automatically closes the file
    return data




# Presentation ------------------------------------ #

while (True):

    print("""
    Menu of Options
    1) Add a new ID / Name.
    2) Store Data
    3) Read file data
    4) Exit
    """)

    strChoice = str(input("Select menu option: "))
    print()
    try:
    # TODO: Get ID and NAME From user, then store it in a list object
        if strChoice.strip() == "1":
            import pickle # This imports code from another code file!
            intId = (input("Enter an Id: ")).strip()
            strName = (input("Enter a Name: ")).strip()
            lstCustomer = [intId, strName]
            print(lstCustomer)

# TODO: store the list object into a binary file
        if strChoice.strip() == "2":
            objFile = open("AppData.dat", "ab")
            b = pickle.dump(lstCustomer, objFile)
            print("Data dumped")
            print()
            objFile.close()

# TODO: Read the data from the file into a new list object and display the contents
        if strChoice.strip() == "3":
            while True:
                objFile = open("AppData.dat", "rb")
                objFileData = pickle.load(objFile)  # load() only loads one row of data.
                print(objFileData)

                if EOFError: break

            objFile.close()
            continue

        elif strChoice.strip() == "4":
            print("Bye")
            exit()

        else:
            print('Please Enter Choice 1,2,3, or 4!')

    except EOFError and ValueError:
        print("error detected")

```
##### Fig 4: Script using Pickle module and Error Handling 

##### As seen in Fig 4 and Fig 5 The script is basic but details how the pickle module works and the data is serialized and then deserialized in when using Command Prompt in Fig 6. Also the error handling of 'EOFError' is used and 'ValueError' which will print "error detected". 

![Running Command Prompt](https://github.com/louisY95/-ITFnd100--Mod07-/blob/master/Running%20in%20command%20prompt.PNG "Running Command prompt") ####
##### Fig 6: Running Command prompt
