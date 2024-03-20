#  Python How-To
Building with Python

I will dump my current Python how-to notes here and update them when I can. 

# Data Types
Data types classify the kind of values that variables can hold, data structures provide a way of organizing and storing data in a specific format or layout to facilitate efficient access and manipulation. Python provides a rich set of built-in data types and data structures that can be used to represent and organize data in various ways.

**Data Types:**

**Integer (int):** Represents whole numbers without fractional parts.
```
x = 10
y = -5
```

**Float (float):** Represents decimal numbers.
```
x = 3.14
y = -0.5
```

**String (str):** Represents sequences of characters enclosed in quotes.
```
name = "Alice"
message = 'Hello, world!'
```

**Boolean (bool)**: Represents True or False values.
```
is_active = True
is_valid = False
```

**List (list):** Represents ordered collections of items.
```
numbers = [1, 2, 3, 4, 5]
names = ['Alice', 'Bob', 'Charlie']
```

**Tuple (tuple):** Represents ordered collections of items, similar to lists but immutable.
```
coordinates = (10, 20)
colors = ('red', 'green', 'blue')
```

**Dictionary (dict):** Represents key-value pairs.
```
person = {'name': 'Alice', 'age': 30, 'city': 'New York'}
```

**Set (set):** Represents unordered collections of unique items.
```
unique_numbers = {1, 2, 3, 4, 5}
```

**NOTE: **
Lists, tuples, sets, and dictionaries are data types because they represent specific classifications or categories of data that variables can hold. Each of these data types has its own characteristics and behaviors in terms of how data is organized and accessed. Lists, tuples, sets, and dictionaries are also considered data structures because they are ways of organizing and storing data in memory. They provide specific methods and functionalities for working with collections of data elements, such as adding, removing, accessing, and iterating over elements.

**NoneType (None):** Represents the absence of a value.
```
no_value = None
```

##  F Strings
**

F strings are only available in python 3.6 or higher. 
```
name = "Jameson"
age = 85
weird_greeting = f"Hello, {name}, you are {age}."
print(weird_greeting)
```
The f string allows more functional string formatting by not having to convert int to str, etc. 

As written above, the variables in weird_greeting become immutable, because the variables are already declared for weird_greeting. To remedy this, use the .format method:
```
name = "Jameson"
better_greeting = f"How are you, {}?"
format_greeting = better_greeting.format(name)
print(format_greeting)
```
This effectively creates a template that can be used with any name in the name variable. 


# Data Structures

Data structures represent the way that data is organized and stored to support efficient operations on collections of data elements or data types. Data structures are differentiated from data types because structures are higher-level constructs that use data types to organize and manage data. Without data types, there could be no data structures. 

**Data structures:**

**Stack:** Represents a last-in, first-out (LIFO) collection.
```
stack = []
stack.append(1)
stack.append(2)
stack.pop()  # Removes and returns the last item (2)
```

**Queue:** Represents a first-in, first-out (FIFO) collection.
```
from collections import deque
queue = deque()
queue.append(1)
queue.append(2)
queue.popleft()  # Removes and returns the first item (1)
```

**Heap (Priority Queue):** Represents a binary heap used for priority queue operations.
```
import heapq
heap = []
heapq.heappush(heap, 5)
heapq.heappush(heap, 3)
heapq.heappop(heap)  # Removes and returns the smallest item (3)
```

**Tree:** Represents hierarchical data structures with nodes connected by edges.
```
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

root = Node(10)
root.left = Node(5)
root.right = Node(15)
```

**Graph:** Represents networks of nodes connected by edges.
```
graph = {
    'A': ['B', 'C'],
    'B': ['C', 'D'],
    'C': ['D'],
    'D': ['C'],
    'E': ['F'],
    'F': ['C']
}
```

**Linked List:** Represents a linear data structure where elements are linked sequentially.
```
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
```

**Hash Table (Dictionary):** Represents a data structure that maps keys to values for efficient lookup.
```
hashtable = {}
hashtable['Alice'] = 30
hashtable['Bob'] = 25
```

**Array:** Represents a collection of items stored at contiguous memory locations.
```
import array
numbers = array.array('i', [1, 2, 3, 4, 5])  # 'i' indicates integer type
```

## Other Data Structures

These data structures are more advanced or specialized and may not be needed in many scenarios. The choice of data structure depends on the specific requirements of the problem being solved and the efficiency considerations for operations like insertion, deletion, search, and traversal.

**Deque (Double-ended Queue):** A data structure that supports adding and removing elements from both ends efficiently.

**Priority Queue:** A data structure where each element has a priority associated with it, and elements are removed based on their priority.

**Graph Algorithms (DFS, BFS):** While graphs were mentioned, specific algorithms such as Depth-First Search (DFS) and Breadth-First Search (BFS) are often used for graph traversal and search.

**Binary Indexed Tree (Fenwick Tree):** A specialized data structure used for efficient prefix sum queries and updates.

**Segment Tree:** Another tree-based data structure used for efficient range queries and updates.

**Skip List:** A probabilistic data structure used for maintaining sorted lists with efficient search, insertion, and deletion operations.

**Suffix Array and Suffix Tree:** Data structures used in string processing and pattern matching algorithms.

**Trie (Prefix Tree):** A tree-based data structure used for efficient retrieval of strings with common prefixes.




##  Quick conversion task

First, ask the user for their name. Then, print out the greeting "Hello, NAME"
Remember the uppercase H, the comma, and the space between words!
```
name = input("Enter your name: ")
print(f"Hello, {name}")
```
Secondly, ask the user for their age and convert it into a number.
Then, print out how many months that equals to (you'll have to multiply the age by 12).
```
age = int(input("Enter your age: "))
months = age * 12
print(months)
```

#  Sets, Tuples, Lists, Dictionaries


**Lists: []** Lists are mutable and easily changed with .append and .remove methods
```
list1 = [value1, value2, value3]
list1.add(value4)
print(List1)
```

**Sets: {}** Sets do not keep order, printing results in random order. You can modify a set using the .add and .remove methods. Sets are useful for comparisons using the .difference() method. Sets will not contain duplicates
Example 1- difference method:
```
set1 = {value1, value2, value3}
set2 = {value4, value 1}
set1_but_not_set2 = set1.difference(set2)
print(set1_but_not_set2)
```

Example 2 - symmetric difference (values not in both sets):
```
set1 = {value1, value2, value3}
set2 = {value4, value 1}
not_in_both = set1.symmetric_difference(set2)
print(not_in_both)
```
Example 3 - Intersection (values in both sets):
```
set1 = {value1, value2, value3}
set2 = {value4, value 1}
one_and_two = set1.intersection(set2)
print(one_and_two)
```

Example 4 - Union (all values in all sets, no duplicates)
```
set1 = {value1, value2, value3}
set2 = {value4, value 1}
all_sets = set1.union(set2)
print(all_sets)
```

**Tuples: () **Tuples are immutable, as opposed to lists. If you want to add to a tuple, you must create a new tuple with the old tuple inside:
```
tuple1 = (value1, value2, value3)
newTuple = (tuple1, value4)
```

Dictionaries: Key-value store, defined with {} can be modified and added to. colons are only used inside the dictionary as bindings, not used in python for value assignment. Dictionaries cannot have duplicates, and the order is maintainedpost-python 3.7. tuples can be converted to dictionaries with the dict() function.
```
dictionary1 = {key1:value1, key2:value2, key3:vlaue3}
dictionary1[key4] = value4
print(dictionary1[1])
```

# Length and sum


**Sum**
you can add together the integer values of a list with the sum() function.
```
List1 = [2,4,6,8]
total = sum(list1)
print(total)
20
```

**Len**
You can also get the length of a list with the len() function. 
```
list1 = [2,4,6,8]
length = len(list1)
print(length)
4
```

These functions are especially handy for arithmetic on lists:
```
average = total / length
print(average)
5
```

## Lotto Exercise
```
lottery_numbers = {13, 21, 22, 5, 8}
 
#A player looks like this:
 
{
    'name': 'PLAYER_NAME',
    'numbers': {1, 2, 3, 4, 5}
}
 
#Define a list with two players (you can come up with their names and numbers).

players = [
    {
        "name": "Rolf",
        "numbers": {1, 3, 8, 22, 21}
    },
    {
        "name": "Jose",
        "numbers": {4, 9, 10, 12, 15}
    }
]
 
#For each of the two players, print out a string like this: "Player PLAYER_NAME got 3 numbers right.".
#Of course, replace PLAYER_NAME by their name, and the 3 by the amount of numbers they matched with lottery_numbers.

#Remember: the string must contain the player's name and the amount of numbers they got right!
name = players[0]["name"]
numbers = players[0]["numbers"].intersection(lottery_numbers)
print(f"Player {name} got {len(numbers)} numbers right.")
```

# Join Lists

you can join lists to make them more easy to read, by using the Join method

Example:
```
family = ["Tiffanie", "Teagan", "Adrian"]
print(f"My family is {family}.")
```
Result:
My family is ["Tiffanie", "Teagan", "Adrian"].

Joining uses a delimiter to separate out the list. For example:
```
family = ["Tiffanie", "Teagan", "Adrian"]
comma_separated = ", ".join(family)
print(f"My family is {comma_separated}.")
```
Result:
My family is Tiffanie, Teagan, Adrian.


# Control Flow
Control Flow is a blanket term for different structures and statements and basic decisions made by a program based on inputs from the user or other similar conditions, that ultimately result in a desired output or function. Control flow refers to the sequence in which the statements of a program are executed, including various structures and statements that control the flow of execution based on conditions, loops, and function calls. These structures and statements allow the program to make decisions, iterate over data, and execute code blocks selectively, ultimately leading to the desired output or behavior. Control flow is essential for programming as it determines the logic and order of operations within a program, enabling it to perform different tasks based on specific conditions or inputs.

## If/Elif/Else Statements
If statements allow your program to make decisions based on a Boolean value. the 'if' command executes an evaluation of a specific condition, and if true, it takes the true path of the tree, and if not, it takes the false path of the tree. 

Syntax:
```
if condition == condition:
	print("True.")
	print("Also True.")

print("This is not part of the if statement body.")
```

The if statement is initialized with the keyword "if" and evaluates the condition that follows it. The colon is necessary to define the body of the if statement, and the indentation defines what is contained within the body. Everything indented under the if statement will be contained within it, and once the indentation is broken, the if statement is over. 

Example:
```
name = "Name1"
user_name = input("Enter your username: ")

if user_name == name:
	print(f"Welcome back, {name}!")
```
it is possible to write multiple if statements for multiple conditions, however it is much simpler to convert the basic 'if' statement seen above into a compound if statement using the 'else' keyword. This will evaluate every other condition that does not meet the initial if statement as false.

Example:
```
name = "Name1"
user_name = input("Enter your username: ")

if user_name == name:
	print(f"Welcome back, {name}!")
else:
	print("Welcome, stranger.")
```

When an if statement is evaluated, Python will pass every value through the bool() function to evaluate whether it is True or False. The bool() result of an empty string will always evaluate to False. Generally, any value on its own is considered true by default, unless compared to another value.
```
friends = ["Rolf", "Bob", "James"]
family = ["Tiffanie", "Teagan", "Adrian"]

user_name = input("Please enter your name.")

if user_name in family:
	print("Welcome, Family.")

if user_name in friends:
	print("Welcome, friend.")
else:
	print("Welcome, stranger.")
```
Result:
Please enter your name: Tiffanie
Welcome, Family.
Welcome, stranger.

This result comes because of the logical execution of the example code. The value "Tiffanie" exists in the family list. When the code executes, it evaluates the first if statement, finds the true value, and prints the result. It then moves to the next if statement, evaluates it, and finds the false (else) value, and prints the result. The solution here is 'elif' to ensure that multiple conditions can be evaluated in a single statement and then a final else statement will be the result if all other conditions are false. 

Example:
```
friends = ["Rolf", "Bob", "James"]
family = ["Tiffanie", "Teagan", "Adrian"]

user_name = input("Please enter your name.")

if user_name in family:
	print("Welcome, Family.")
elif user_name in friends:
	print("Welcome, friend.")
else:
	print("Welcome, stranger.")
```	
Result:
Please enter your name: Tiffanie
Welcome, Family.

 
There can be as many elif staetments as necessary, and remember that they are evaluated in order! The first one that runs, means that the others don't run. 

## While Loops

Loops are used to repeat things multiple times. A while loop will iterate through boolean conditions and run while the desired state is true. It is especially useful when repeating a process an undefined number of times- i.e. until a user tells the code to stop. 

Syntax: Similar to if statements, in that the loop must be initialized with a colon (:), and the body must be indented immediately beneath the while statement. 

Example:
```
is_learning = True

while is_learning:
	print("You are learning!")
```

This will print "You are learning!" to the console indefinitely, because the value is set to True. As long as the value is true, the while loop will keep iterating through and printing the desired output. Here is how we can get around this

```
is_learning = True

while is_learning:
	print("You are learning!")
is_learning = input("Are you still learning?")
```	
If the user enters yes, the while loop will evaluate the value of is_learningn as true, and iterate again. A blank or no value will result in the termination of the loop, as these values evaluate to False. Alternatively:

```
is_learning = True

while is_learning:
	print("You are learning!")
	is_learning = False
```
	
This will also work to terminate the loop, but does not offer the flexibility of input or value modification of the variable. 

Another option is to evaluate the user input as its own variable and do a simple comparison against the is_learning variable value. 
```
is_learning = True

while is_learning:
	print("You are learning!")
	user_input = input("Are you still learning?")
	is_learning = user_input == "yes"
```
	
This takes the initial True value of the is_learning variable and compares it to the user_input variable. If the user enters anything except "yes", then the while loop evaluates a False, and terminates; a yes input will result in the loop iterating again, and printing the "You are learning!" output to the console. This is a common way of structuring user menus, or places where users may need to repeat something multiple times. 

Example:
```
user_input = input("Do you wish to run the program? (yes/no): ")

while user_input == "yes":
	print("We are running!")
	user_input = input("Do you wish to run the program? (yes/no): ")
	
print("We stopped running.")
```	
	
Use case:

A menu is something that repeats over and over again until the user types something that makes the program terminate.
In our menu, the user will be able to choose from two options:
	• If they type p , we will print "Hello"
	• If they type q , we will terminate the program
	• If they type something else, we will ask them for input again
How will we go about it?
First, we'll ask the user for what they want to do first. Do they want to print (p ), or do they want to exit without printing (q )?
Then we'll have a while  loop that will repeat until the user types q .
Inside the while loop, we'll have an if  statement that checks whether the user typed p . If they did, we'll print "Hello" .
Inside the loop but outside the if statement, we'll ask the user again whether they want to print or quit.


Ask the user to choose one of two options:
if they type 'p', our program should print "Hello" and then ask the user again. Keep repeating this until...
if they type 'q', our program should terminate.

Let's begin by asking the user to type either 'p' or 'q'. You know how to do this using input()
```
user_input = ...

user_input = input("Type p or q to see what happens.")
"""
Then, begin a while loop that runs for as long as the user doesn't type 'q'.
Inside the loop, have an if statement that checks if the user typed 'p'.
   If they did, print "Hello"
Still inside the loop, ask the user again
user_input = ...
"""
while user_input != "q":
    if user_input == "p":
        print("Hello")
  
    user_input = input("Once more, type p or q.")
       

    # user_input = input("Once more, type p or q.")
```    



Very Common Example:
```
i = 0
while i < 20:
	print(f'Repeated {i} times.')
	i += 1
```

## For Loops

For loops, like While loops, are used to iterate through certain conditions and output depending on the evaluation of those conditions. Unlike While loops, however, For loops are used to repeat something a defined number of times. Python's approach to For loops is unique to other languages, which may use For Each. 

Syntax: The same as a While loop, but with For instead. 
```
family = ["Tiffanie", "Teagan", "Adrian"]

for member in family:
	print(member)
```
Result:
Tiffanie
Teagan
Adrian

The For loop reads each iterable (element of the list) as the new variable "member" and assigns a single value to that variable for each iteration of the list. It then prints each one, moving to the next with each iteration of the loop. This has a finite amount of times it can run, with the amount being equal to the number of elements in the list. For example, the new variable could be anything, as could the printed output.

Example: 
```
family = ["Tiffanie", "Teagan", "Adrian"]

for _in family:
	print("Hello world")
```	
Result:
Hello world
Hello world
Hello world

Example:
```
elements = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for index in elements:
	print("Hello, world!")
```

You can also use the range keyword to iterate a for loop through a range of numbers:
```
for index in range (5, 10)
	print(index)
```	
Result:
5
6
7
8
9

OR 
```
for index in range (2, 20, 3)
	print(index)
```
Result:
2
5
8
11
14
17


Example:
```
Students = [
	{"name": "Jeff", "grade": 90},
	{"name": "Bob", "grade": 78},
	{"name": "Barb", "grade": 100},
	{"name": "Luke", "grade": 80}
]

For student in students:
	Name = student["name"]
	Grade = student["grade"]
	
	Print(f"{name} has a grade of {grade}.")
```	
Result:
Jeff has a grade of 90.
Bob has a grade of 78.
Barb has a grade of 100.
Luke has a grade of 80.



Finding prime numbers exercise:
```
for n in range(2, 10):
	for x in range(2, n):
		if n % x == 0:
			print(f"{n} equals {x} * {n//x}")
			break
	else:
		print(f"{n} is a prime number.")
```		
Result:
2 is a prime number.
3 is a prime number.
4 equals 2 * 2
5 is a prime number.
6 equals 2 * 3
7 is a prime number.
8 equals 2 * 4
9 equals 3 * 3

This will iterate n as every numerical value in the range, and run the loop for each. If the range was (2,1000), the loop would execute 998 times. The x value is assigned the n value each time, and then divides n by x. If the remainder is 0,  then the number is not prime. If the remainder is anything other than 0, the else statement will execute, telling us that the number is prime. As an optimization, we don't really need to check the second for loop from range (2,n), you really only need to check from 2 through the square root of n. 

## Destructuring Syntax


There are many different ways to write Python, but there are some that are easier to read, some that are more efficient at runtime, and some that are just easier to write. Destructuring is a way to make things easier to read, and improves writing efficiency. 

Tuple example:
```
currencies = 0.8, 1.2
Usd, eur = currencies
```
This example takes the values usd and eur and assigns them to their respective tuple value, in the order that they are written. The first value of the tuple, 0.8, is now assigned to the new variable called usd.

Example:
```
friends = [{"Rolf", 25}, {"Bob", 34}, {"Jen", 37}, {"Anne", 22}]

for name, age in friends:
	print(name, age)
```
Result:
Rolf 25
Bob 34
Jen 37
Anne 22

But you could also add an f string to make the output more readable:
```
friends = [{"Rolf", 25}, {"Bob", 34}, {"Jen", 37}, {"Anne", 22}]

for name, age in friends:
	print(f"{name} is {age} years old.")
```
	
Result:
Rolf is 25 years old. 
Bob is 34 years old.
Jen is 37 years old.
Anne is 22 years old.

There are many different ways to write this same output, but the destructuring method here is the best way.

## Break & Continue


Break and continue are syntax keywords that can help handle certain exceptions.

Break can completely stop a loop when a certain defined condition is encountered during iteration.
 
Example:
```
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Stopping production, faulty car found.")
		break
	print(f"This car is {status}.")
```	
Result:
This car is ok.
This car is ok.
This car is ok.
This car is ok.
Stopping production, faulty car found.


The continue keyword allows the loop to continue while handling the defined parameter differently than the rest. 

Example:
```
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
```
	
Result:
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
Faulty car found. Continuing production.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.

## Else in Loops

Else can be used as a keyword trigger when using loops. This else statement will be executed only if the loop encounters no breaks/continues; in other words, if the loop runs completely without exceptions.

Syntax: The else keyword is on the same indentation level as the for/while loop statement. 

Example:
```
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
else:
	print("All cars built successfully. No faulty cars.")
```
Result:
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
Faulty car found. Continuing production.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.

```
cars = ["ok", "ok", "ok", "ok", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
else:
	print("All cars built successfully. No faulty cars.")
```
Result:
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
This car is ok.
Shipping to customer.
All cars built successfully. No faulty cars.

## Slicing

Slicing is the process of getting part of a list, dictionary, tuple, or other iterable. The first number is the starting number in the list, and the last is the last number in the list. 

Example (Basic):
```
list = ["Name1", "Name2", "Name3", "Name4", "Name5"]

print(list1[1:3])
```
Result:
["Name2", "Name3"]

Slicing can be exclusionary, depending on the configuration of the colon and place numbers; for example:
```
list = ["Name1", "Name2", "Name3", "Name4", "Name5"]

print(list1[1:])
```
Result:
["Name2", "Name3", "Name4", "Name5"]

OR 
```
print(list1[:4])
```
Result:
["Name1", "Name2", "Name3", "Name4"]


You can also slice from the end of the list using negative numbers. 
Example:
```
print(list1[-3:])
```
Result:
["Name3", "Name4", "Name5"]

this counts backwards from the end o f the list, and output begins with that value, and counts forward from there. 

## Comprehensions
Comprehensions are a Python feature that allows the creation of new lists using elements from other lists. 

Example:
```
numbers = [0, 1, 2, 3, 4]
doubled_numbers = []

for number in numbers:
	doubled_numbers.append(number * 2)
	
print(doubled_numbers)
```
Result: [0, 2, 4, 6, 8]

But this is just a For loop. Using list comprehension, we can output the same result, but with much more succinct and efficient code.

Use list comprehension instead:
 ```
numbers = [0, 1, 2, 3, 4]
doubled_numbers = [number * 2 for number in numbers]
```
Result: [0, 2, 4, 6, 8]

This is the same as the For loop, but simpler in the coding. 

List comprehension can also be used for data normalization  


## Enumeration

Enumeration is a data type that assigns numeric values to items in a list. 

Without enumeration:
```
friends = ["Rolf", "John", "Anne"]

counter = 0

for friend in friends
	print(counter)
	print(friend)
	counter = counter + 1
	
Result:
0
Rolf
1
John
2
Anne
```


With enumeration:
```
for counter, friend in enumerate(friends):
	print(counter)
	print(friend)
```		
By default, the enumeration function starts the count at 0, but you can specify the starting number as a parameter in the function i.e., "enumerate(friends, start=1)".

## Improved Lotto Exercise
```
import random

# This line creates a set with 6 random numbers
lottery_numbers = set(random.sample(list(range(22)), 6))

# Here are your players; find out who has the most numbers matching lottery_numbers!
players = [
    {"name": "Rolf", "numbers": {1, 3, 5, 7, 9, 11}},
    {"name": "Charlie", "numbers": {2, 7, 9, 21, 10, 5}},
    {"name": "Anna", "numbers": {13, 14, 15, 16, 17, 18}},
    {"name": "Jen", "numbers": {19, 20, 12, 7, 3, 5}},
]

# Then, print out a line such as "Jen won 1000.".
# The winnings are calculated with the formula:
# 100 ** len(numbers_matched)

name = players[0]["name"]
numbers_matched = players[0]["numbers"].intersection(lottery_numbers)
winnings = 100 ** len(numbers_matched)
print(f"{name} won {winnings}.")
```

## Functions
Functions are blocks of reusable code that serve a specific function. Since they are reusable, they can be called by name and made to execute or operate again and again. 

Syntax: Always start with the "def" keyword. "Def" is short for define, and it lets Python know that you are defining a new function. Folllowing the "def" keyword, the name of the function followed by parenthesis. Just like in loops, the function name and parenthesis is followed by a colon. Following that comes the body of the function, where the function is fully defined. 

Structure Example:
```
def function1():
	Body
```
	
A more functional example:
```
def greet():
	name = input("Please enter your name: ")
	print(f"Hello, {name}!")
	
greet()
```

As you can see in the example, the function is defined and invoked by entering the function name following the definition. Without entering the name of the function, the program only understands that a function was defined, and will not run the function. 

Best practice dictates that shorter and more specific functions are better, there is less overhead and functions should be used for a single purpose. There is no limit to how much you can put into the body of a function, but the longer the function is, the more jumping around there will be in the program runtime. 

Also note that variables created inside of a function are not global variables, they are only defined in that particular function, and cannot be called outside it. 

### Arguments and Parameters

Arguments and parameters are used inside functions to make them more generic and more broadly usable with various pieces of data.

**Argument** = value passed into the function when a function call is made

**Parameter** = variable that accepts a value inside of a function, defined in the function, receives the argument, and executes based on the value of the argument. 

Example:
```
cars = [
	{"make": "Ford", "model": "Focus", "mileage": 23000, "fuel_consumed": 460 },
	{"make": "Chevy", "model": "Malibu", "mileage": 56000, "fuel_consumed": 900},
	{"make": "Dodge", "model": "Charger", "mileage": 17000, "fuel_consumed": 330},
	{"make": "VW", "model": "Passat", "mileage": 20000, "fuel_consumed": 425}
]

def calculate_mpg(car):
	mpg = car["mileage"]/ car["fuel_consumed"]
	name = f"{car['make']} {car['model']}"
	print(f"{name} does {mpg} miles per gallon.")
	
for car in cars:
	calculate_mpg(car)'
```	

### Return

The return keyword is used to return values inside of a function. It can be used as the value of the function variable when that function is called in other functions. 

Example:
```
cars = [
	{"make": "Ford", "model": "Focus", "mileage": 23000, "fuel_consumed": 460 },
	{"make": "Chevy", "model": "Malibu", "mileage": 56000, "fuel_consumed": 900},
	{"make": "Dodge", "model": "Charger", "mileage": 17000, "fuel_consumed": 330},
	{"make": "VW", "model": "Passat", "mileage": 20000, "fuel_consumed": 425}
]

def calculate_mpg(car):
	mpg = car["mileage"]/ car["fuel_consumed"]
	name = f"{car['make']} {car['model']}"
	print(f"{name} does {mpg} miles per gallon.")
	
for car in cars:
calculate_mpg(car)
```













# Glossary of Terms
## Variable

A named storage location in computer memory that holds an assigned value.

 ## Data Type

Classification of data that determines the type of operations that can be performed on it.

## String

A sequence of characters, typically used to represent text.

## Integer

A whole number, no decimal or fractional parts.

## Float

A numerical data type that represents 'floating-point' numbers with decimal parts.

## Boolean

a data type that represents two possible values: True or False. 

## List

Ordered collection of items that can be of different data types; mutable. 

## Tuple

Ordered collection of items, similar to a list, but immutable.

## Dictionary

A collection of key-value pairs, each key associated to a specific value. 

## Set

Unordered collection of unique elements. Eliminates duplicate values.

## Enumeration (Enum)

A data type that consists of a set of named constants. Each constant represents a unique value within the enumeration.

## Array

A data structure that consists of a collection of items stored at contiguous memory locations. 

## Slice

A way of extracting a portion of a sequence or collection (list, string, etc) by specifying start, stop, and optional step indices. 

## Index(ing)

A numerical value representing a position within a data structure's sequence. Typically begins from 0 as the first element. Indexing is accessing individual elements within the data structure by referencing the specific positional values. 

## Call

the act of invoking a function or method to execute its code with specified arguments, which are usually in parenthesis.

## Iteration

Repeatedly executing a block of code over a sequence of items, such as in a loop.

## Control Flow

The order in which statements are executed in a program, determined by conditionals, loops, function calls, etc. 

## Loop

A control flow statement that repeatedly executes a block of code until a specified condition is met. 

## Conditional Statement

A control flow statement that allows the execution of different blocks of code based on the evaluation of a specified condition. 

## If Statement

A conditional statement that executes if a specified condition is True.  

## Else Statement

Part of an if statement that executes if all other parts of an if statement evaluate to False. 

## Elif Statement

A part of an if statement that allows testing multiple conditions sequentially after the initial if condition. Typically followed by a final Else statement. 

## Comparison Operator

Operators used to compare two values or expressions, such as == (equal), != (not equal), < (less than), > (greater than), <= (less than or equal to), >= (greater than or equal to). 

## Logical Operator

Operators used to combine or maniplulate boolean values, such as and, or, not, can create complex conditional expressions. 

## Function

A block of reusable code that performs a specific task.

## Parameter

A variable used in a function definition to represent input data. 

## Argument

A value passed through a parameter when the parameter is called by a function. 

## Return Value

The result or output of a function

## Insertion

Adding a new element into a data structure, such as adding an item to a list or inserting a record into a database.

## Deletion

Removing an existing element from a data structure, such as deleting an item from a list or removing a record from a database.

## Search

Looking for a specific element or value within a data structure, such as finding a particular item in a list or searching for a record in a database based on certain criteria.

## Traversal

Visiting and processing each element or node in a data structure systematically, such as iterating through all items in a list or visiting all nodes in a tree.

## Stream

A continuous flow of data, often used in the context of input/output operations where data is processed or transferred in a sequential manner, like reading from or writing to a file or network stream.

## Built-in Function

A predefined function that comes built into Python. Always available for use

## Module

A file containing Python code, usually a collection of functions, classes, and variables. 

## Package

A collection of modules organized in a directory structure. 

## Import Statement

A statement used to bring modules or objects from specific modules into the current namespace. 

## Namespace

A context in which names (variables, functions, etc) are unique and can be referenced without ambiguity. 

## Dot Notation

Syntax used to access attributes and methods of objects. Involves using a dot ('.') 

## Exception

An event that occurs during the execution of a program that disrupts the normal flow of instructions and can be handled by the program. 

## Try-Except Block

A block of code used to handle exceptions that may occur during execution. 

## Raise Statement

Statement used to explicitly raise an exception. 

## Library

A collection of predefined reusable code and resources that provide specific functionality. Ex Numpy, tkinter

## File I/O

Input/Output operations performed on files, typically reading or writing to files. 

## Open Function

A function used to open files for reading or writing. 

## Read Function

A function used to read data from an opened file. 

## Write Function

A function used to write data to an opened file. 

## Append Function

A function used to add data to the end of an opened file. 

## Close Method

A function used to close an opened file and release associated system resources. 

## Context Manager

An object that manages resources within a block of code using the "with" statement. 

## Class

a Blueprint for creating objects that defines attributes and methods.

## Object

An data structure that is an instance of a class that encapsulates both data (attributes and properties) and methods (functions or procedures) that operate on that data (behavior). 

## Method

A function defined within a class that operates on its object's data (attributes); can perform actions or computations using the object's attributes or modify and object's state. 

## Attribute

A piece of data stored within an object, representing a state or characteristic. Attributes are accessed and manipulated using dot notation ('object.attribute') and can be variables, constants, or references to other objects. 

## State

Refers to the current condition or configuration of an object or program at a particular point in time. Can encompass the values of variables, status of objects, etc. 

## Stateful

A program or system that retains information about previous interactions or events.  

## Constant

A variable whose value remains unchanged throughout the program's execution. Once assigned, it cannot be modified, reassigned or changed. Typically used for fixed mathematical values such as pi, configuration settings, etc. 

## Inheritance

Mechanism where a class inherits attributes and methods from another class. 

## Decorator

Special type of function that modifies behavior of other functions or methods. 

## Lambda Function

A small anonymous function defined with 'lambda' keyword, allowing creation of a function without a formal name. Useful for short, one-time operations in which a full function definition is unnecessary. 

## Persistence

The ability of a program to save and retrieve data between different executions or sessions. Involves storing data in a persistent storage medium (file, db, etc) which remains accessible after the program terminates. 

## Transience

Opposite of Persistence. Information or data that is temporary and only relevant within the current session or program execution. Once the program terminates, transient state data is usually lost unless explicitly persisted.

## Algorithm

A step-by-step procedure for solving a problem or accomplishing a task. 

## Data Structure

An efficient way of organizing and storing data to perform specific operations. 

## Stack

A memory paradigm that follows the Last-in, First-out (LIFO) principle. 

## Heap

A specialized tree-based memory paradigm used to maintain a priority queue. 

## Queue

A data structure for storing and managing data that follows First-In, First-Out (FIFO) principle. 

## Linked List

A linear data structure where elements are stored in nodes with pointers to the next node. 

## Tree

A hierarchical data structure consisting of nodes connected by edges. 

## Edges

Represent connections or relationships between nodes in a graph or network data structure. They define how nodes are linked or related to each other. 

## Graph

A collection of nodes (vertices) connected by edges representing relationships. 

## Hash

A function that converts input data into a fixed-size value. 

## Hash Table

A data structure that uses a hash function to map keys to values for efficient lookup and validation. 

## Binary Search

A search algorithm that finds the position of a target value within a sorted array by repeatedly dividing the search interval in half. 

## Sorting Algorithm

An algorithm that arranges elements in a specific order, such as ascending or descending. 

## Recursion

A technique or mechanism where a function calls itself to solve smaller instances of the same problem. 

## Complexity Analysis

Study of the performance characteristics of algorithms in terms of time and space.

## Big O Notation

Mathematical notation used to describe the upper bound or worst-case time complexity of an algorithm. 

## Binary

Number system with a base of 2, using only digits 0 and 1. 

## Hexadecimal

Number system with a base of 16, using digits 0-9 and letters A-F. 

## Octal

Number system with a base of 8, using digits 0-7.

## Boolean Logic

Branch of algebra that deals with logical operations on binary variables. 

## Truth Table

A table used to represent outcomes of all possible combinations of inputs in a logical expression. 

## Buffer

A temporary storage area designated to hold data while it is being transferred between devices or processes. 

## Buffer Overflow

Occurs when a program tries to store more data in a buffer than the buffer is designed to handle, potentially leading to security vulnerabilities. 

## Runtime

The period during which a program is executing or running. 

## Notebook 

An interactive computing environment that allows combining code, visualizations, and text in a single document, commonly used in data science and analysis.

## Data Frame 

A two-dimensional, labeled data structure in pandas that resembles a table, with rows and columns, suitable for data manipulation and analysis.

## Anaconda

A distribution of Python and its associated libraries for data science, machine learning, and scientific computing, providing tools like conda for package management.

## IronPython

An implementation of Python for the .NET Framework, allowing Python code to interact with .NET libraries and frameworks.

## NumPy 

A library for numerical computing in Python, providing support for arrays, matrices, and mathematical functions, essential for scientific computing and data analysis.

## Pandas

A powerful library for data manipulation and analysis in Python, offering data structures like data frames and tools for cleaning, transforming, and analyzing data.

## Tkinter

The standard GUI (Graphical User Interface) toolkit included with Python, used for creating desktop applications with widgets like buttons, labels, and entry fields.

## Node

An individual element in a data structure, such as a linked list or a tree. Nodes can contain data and references or pointers to other nodes.

## Branching

Controlling the flow of program execution based on conditions. 

## Looping

Repeating a block of code multiple times until a condition is met. 

## Bitwise Operation

Manipulation of individual bits of binary numbers. 

## Pointer

A variable that stores the memory address of another variable. 

## Reference

A value that refers to another object's memory address. 

## Memory Allocation

Reservation of memory space for data storage during program execution. 

## Garbage Collection

Automatic process of reclaiming memory occupied by unreferenced objects. 

## Segmentation Fault

Error that occurs when a program tries to access restricted memory regions. 

## Compilation

A program that translates source code written in a high-level programming language into machine code or bytecode.

## Interpreter

A program that directly executes code written in a high-level programming language without compiling it into machine code.

## Bytecode

Intermediate code generated by compilers and typically executed by a VM.

## Machine Code

Low-level instructions directly executable by a computer's CPU. 

## Syntax

The set of rules governing the structure and format of statements in a language.

## Semantics

The meaning or interpretation of code in the context of a language. 

## Compilation Error

An error that occurs during the compilation process due to syntax or semantic issues. 

## Runtime Error

An error that occurs while a program is running due to unexpected conditions. A disruption of the normal (expected) execution conditions. 

## Logic Error

An error in the program's logic that causes it to behave incorrectly, often without a crash. 

## Deadlock

A situation where two or more processes are unable to proceed because each is waiting for the other to release a resource. 

## Debugging

The process of identifying and fixing errors or bugs in a program. 

## Breakpoint

A designated point in a program's execution that causes an intentional pause for inspection during debugging. 

## Profiling

Analyzing the performance of a program to identify bottlenecks or inefficiencies. 

## Optimization

Improving the performance or efficiency of a program by making it faster or reducing resource consumption.

## Abstraction

Simplifying complex systems by focusing on high-level concepts and hiding implementation details. 

## Modularity

Organizing code into separate, interchangeable components to promote reusability and maintainability. 

## Unit Testing

Software testing approach where individual units or components of a program are tested in isolation to ensure they work correctly and meet specified standards or requirements. 

## Encapsulation

Bundling data and methods that operate on the data into a single unit, hiding implementation details. 

## Polymorphism

The ability of objects to take on different forms or respond differently to the same message or method call.

## Repository

Typically refers to a version control system, used to store and manage source code, project files, and related resources. 

## Extensions

Additional modules or packages that enhance the functionality of the core language. These can provide new features, libraries, or tools that can extend Python's capabilities for specific tasks or domains. 

## GUID

Globally Unique Identifier- a unique ID that is generated algorithmically to ensure uniqueness across distributed systems or relational databases. 

## GUI

Graphical User Interface- the visual interface that enables user interaction with programs or applications using elements such as windows, buttons, menus, forms, etc. 

## Artifact

any output or result produced during the software development process. This can include compiled files, documentation, libraries, executables, or any other byproduct of the dev tools. 

## Async (Asynchronous) 

Asynchronous programming allows tasks to run concurrently and independently, enabling non-blocking execution and efficient resource utilization. 

## Thread

A small unit of execution within a process, capable of running concurrently with other threads. Threads share the same memory space and resources within a process. 

## Hyperthreading

A technology that allows a single physical CPU core to appear as multiple logical cores, improving parallel processing and multitasking performance. 

## Multithreading

A programming technique where multiple threads within a single process execute concurrently, improving performance and responsiveness in handling tasks. 

## Multiprocessing

Involves using multiple processors or CPU cores to execute tasks simultaneously, enhancing overall system performance and efficiency by distributing workload across multiple processing units. 
