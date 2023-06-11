Primary Categories: [[01 - Administration]] 
Secondary Categories: [[]] 
Links: [[Python]] - [[Programming]] - [[Coding]]
Search Tag: #📖  

# [[03 - Python Fundamentals]] 

## Strings
```Python
#print string
print("Hello, World!")
print('Hello, World!')

#print string with multiple lines
print("""this string runs
multiple lines!""")

#print string with concatenate 
print("this string is "+"awesome!")

# line break
print('\n') 
```

## Math
```Python
#Basic maths
print(50 + 50) #Adding
print(50 - 50) #Subtraction
print(50 * 50) #Multiplication
print(50 / 50) #Division
print(50 + 50 - 50 * 50 / 50) #PEMDAS
print(50 ** 2) #Expondents
print(50 % 6) #Modulo
print(50 // 6) #Rounds 
```

## Variables and Methods
```Python
#Quote is the variable - stored information that can be called upon
quote = "all is fair in love and war"
print(quote)
#Methods
print(quote.upper()) #Uppercase
print(quote.lower()) #lowercase
print(quote.title()) #Capital first letter
print(len(quote)) #Count characters in variable

name = "Josh" #String
age = 32 #int int(30)
gpa = 3.2 #Float float(3.2)
print(int(age)) #Will print age without decible 
print(int(30.1)) #Will only show whole number, does not round
print("my name is " + name + " and i am" + str(age) + " years old.")
```

## Functions
```Python
print("Here is a function:")

def who_am_i():
	name = "Josh"
	age = 30
	print("my name is " + name + " and i am " + str(age) + " years old.")
who_am_i()

#adding parameters
def add_one_hundred(num):
    print(num + 100)
add_one_hundred(100)

#multiple parameters
def add(x,y):
    print (x + y)
add(7,7)

#store parameter for later
def multiply(x,y):
    return x * y
print(multiply(7,7))

#square root function
def square_root(x):
    print(x ** .5)
square_root(64)

#Using a function to make a short cut for a line break
def nl():
    print('\n')
nl()
```

## Boolean Expressions (True or False)
```Python
print("boolean expressions:")
bool1 = True
bool2 = 3*3 == 9
bool3 = False
bool4 = 3*3 != 9
print(bool1,bool2,bool3,bool4)
print(type(bool1))
```

## Relational and Boolean Operators
```Python
greater_than = 7 > 5 #true
less_than = 5 > 7 #true
greater_than_equal_to = 7 >= 7 #true
less_than_equal_to = 7<= 7 #true

#Both (AND) have to be true/false to be true/false
test_and = (7 > 5) and (5 < 7) #true
test_and2 = (7 > 5) and (5 > 7) #false

#Either (OR) has to be true/false to be true/false
test_or = (7 > 5) or (5 < 7) #true
test_or2 = (7 > 5) or (5 > 7) #false

#kinda confusing, look up truth table on google
test_not = not True #false
```

## Conditional Statements
```Python
#Variable with 2 outcomes
def drink(money):
    if money >=  2:
        return "You've got yourself a drink!"
    else:
        return "No drink for you!"
print(drink(3))
print(drink(1))

#Multiple variables with different outcomes
def alchohol(age,money):
    if (age >= 21) and (money >= 5):
        return "We're getting and drink!"
    elif (age >= 21) and (money < 5):
        return "Come back with more money."
    elif (age < 21) and (money >= 5):
        return "Nice try, Kid!"
    else:
        return "You're too poor and too young"
print(alchohol(21,5))
print(alchohol(21,4))
print(alchohol(20,5))
print(alchohol(20,4))
```

## Lists (Lives in brackets [ ])
```Python
heros = ["Thor", "Spiderman", "Superman", "Batman"]
print(heros[1]) #Spiderman - Lists start with 0 ... 1, 2, 3
print(heros[0]) #Thor
print(heros[1:3]) #Grabs spiderman and superman - includes 1 but stops at 3
print(heros[1:]) #Grabs spiderman through batman - includes 1 and everything after it
print(heros[:1]) #Grabs Thor but nothing else
print(heros[-1]) #Grabs the last item on the list

print(len(heros)) #Counts how many things in the list
heros.append("joker") #Add something to end of list
heros.pop() #Removes the last item in a last
heros.pop(0) #Removes item in the named position
```

## Tuples (Cannot be changed, have ( ) )
```Python
grades = ("a", "b", "c", "d", "f") #Once defined, cannot be changed
print(grades[1]) #Prints "b"
```

## Looping
```Python
#For loops - Start to finish of an iterate
vegtables = ["cucumber", "spinach", "cabbage"]
for x in vegtables:
    print(x)

#While loops - Execute as long as true
i = 1
while i < 10:
    print(i)
    i += 1
```

# Importing Modules
```Python
import sys #System functions and perameters
import os #Allows the use of operating system functions
from datetime import datetime #Can import a specific part of a module
from datetime import datetime as dt #Import with alias
print(sys.version)
print(datetime.now())
print(dt.now())
```

## Advanced Strings
```Python
my_name = "Josh"
print(my_name[0]) #Prints first letter
print(my_name[-1]) #Prints last letter

sentence = "this is a sentence."
print(sentence[:4]) #Prints by the letter, prints "this"
print(sentence.split()) #Breaks out individual words

sentence_split = sentence.split()
sentence_join = ' '.join(sentence_split) #Takes split words and rejoins
print(sentence_join)

quote = "He said, 'Give me all your money'" #Can use single quotes inside double quotes
print(quote)
quote = "He said, \"Give me all your money\"" #Called character escaping, tells it to keep it a string
print(quote)

too_much_space = "               hello                 "
print (too_much_space.strip()) #Removes the extra space

print("A" in "Apple") #Shows true, case sensitive!
letter = "A"
word = "Apple"
print(letter.lower() in word.lower()) #Puts everything in lowercase, removes case sensitivity

movie = "The Hangover"
print("my favorite movie is {}".format(movie)) #Uses {} as a place holder, and format to call variable
```

## Dictionaries - Key/Value pairs { }
```Python
drink = {"White Russian": 7, "Old Fashion": 10, "Lemon Drop": 8} #Drink is key, price is value
print(drink)

#Multiple key:value's
employees = {"Finance" : ["Bob", "Linda", "Tina"], "IT" : ["Gene", "Louise", "Teddy"], "HR" : ["Jimmy jr.", "Mort"]}
employees['legal'] = ['Mr. Frond'] #add new key:value pair
employees.update({'Sales': ['Andie', 'Ollie']}) #add new key:value pair
print(employees)

drink['White Russian'] = 8 #Update value to the key
print(drink.get("White Russian")) #Gets value from key
```

## Sockets
```Python
import socket
#Define target IP/Port
HOST = '127.0.0.1'
PORT = 7777
#AF_INET is an IP address - SOCK_STREAM is a port
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) #Very common string for socket
s.connect((HOST,PORT))
```

## Port Scanner Project
```Python
import socket
import sys
from datetime import datetime

#Define our target
if len(sys.argv) == 2:
    target = socket.gethostnamebyname(sys.argv[1]) #Translate hostname to IPv4
else:
    print("Invalid amount of arguments.")
    print("Syntax: python3 scanner.py <ip>")

#Add pretty banner
print("-" * 50)
print("Scanning target "+target)
print("Time Started: "+str(datetime.now()))
print("-" * 50)

try:
    for port in range(50,85):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        socket.setdefaulttimeout(1)
        result = s.connect_ex((target,port)) #reutns an error indicator
        #print("Checking port {}".format(port)) #Will print every port it checks
        if result == 0:
            print("Port {} is open".format(port))
        s.close()
except KeyboardInterrupt:
    print("\nExiting Program.")
    sys.exit()
except socket.gaierror:
    print("Hostname could not be resolved.")
    sys.exit()
except socket.error:
    print("Couldn't connect to server.")
    sys.exit()
```

## User Input
```Python
name = input("Enter your name: ")
drink = input("What's your favorite drink?: ")
print("Hello" +name+ "!" " Have a" +drink)
```

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: February 16th 2023 (09:56 pm) 
Last Modified Date: February 16th 2023 (09:56 pm)
