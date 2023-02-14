Ans1) An exception is an event, which occurs during the execution of a program that disrupts the normal flow of the program's instructions. In general, when a Python script encounters a situation that it cannot cope with, it raises an exception. An exception is a Python object that represents an error.

Difference: Syntax errors occur when the parser detects an incorrect statement while exception error occurs whenever syntactically correct Python code results in an error.

Ans2) The runtime system will abort the program and an exception message will print to the console.

Ans3) Try and except statements are used to catch and handle exceptions in python.


```python
try :
    10/0
except Exception as e :
    print(e)
```

    division by zero


Ans4)
```python
## try else
def divide(x, y):
    try:
        result = x // y
    except ZeroDivisionError:
        print("You are dividing by zero ")
    else:
        print("Your answer is :", result)
divide(3, 2)
divide(3, 0)
```

    Your answer is : 1
    You are dividing by zero 



```python
## finally
def divide(x, y):
    try:
        result = x // y
    except ZeroDivisionError:
        print("You are dividing by zero ")
    else:
        print("Your answer is :", result)
    finally:
        print('This is always executed')  
divide(3, 2)
divide(3, 0)
```

    Your answer is : 1
    This is always executed
    You are dividing by zero 
    This is always executed



```python
## raise
s = 'apple'
try:
	num = int(s)
except ValueError:
	raise ValueError("String can't be changed into integer")

```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[7], line 4
          3 try:
    ----> 4 	num = int(s)
          5 except ValueError:


    ValueError: invalid literal for int() with base 10: 'apple'

    
    During handling of the above exception, another exception occurred:


    ValueError                                Traceback (most recent call last)

    Cell In[7], line 6
          4 	num = int(s)
          5 except ValueError:
    ----> 6 	raise ValueError("String can't be changed into integer")


    ValueError: String can't be changed into integer


Ans5) In Python, we can define custom exceptions by creating a new class that is derived from the built-in Exception class. We can subclass custom exception classes as well to create a hierarchy.


```python
class validateage(Exception) : 
    def __init__(self, msg) :
        self.msg = msg
```


```python
def validate_age(age) : 
    if age < 0 : 
        raise validateage("age should not be lesser then zeor " )
    elif age > 200 : 
        raise validateage("age is too high " )
        
    else :
        print("age is valid" )
```


```python
try : 
    age = int(input("enter your age"))
    validate_age(age)
except validateage as e : 
    print(e)
```

    enter your age 999


    age is too high 

Ans6)

```python
class Error(Exception):
	pass

class TransitionError(Error):
	def __init__(self, prev, nex, msg):
		self.prev = prev
		self.next = nex

		# Error message thrown is saved in msg
		self.msg = msg

try:
	raise(TransitionError(2, 3*2, "Not Allowed"))

except TransitionError as error:
	print('Exception occurred: ', error.msg)

```

    Exception occurred:  Not Allowed



```python

```

