#  Python How-To
Building with Python

I will dump my current Python how-to notes here and update them when I can. 

#  F Strings
**

F strings are only available in python 3.6 or higher. 

name = "Jameson"
age = 85
weird_greeting = f"Hello, {name}, you are {age}."
print(weird_greeting)

The f string allows more functional string formatting by not having to convert int to str, etc. 

As written above, the variables in weird_greeting become immutable, because the variables are already declared for weird_greeting. To remedy this, use the .format method:

name = "Jameson"
better_greeting = f"How are you, {}?"
format_greeting = better_greeting.format(name)
print(format_greeting)

This effectively creates a template that can be used with any name in the name variable. 



##  Quick conversion task

First, ask the user for their name. Then, print out the greeting "Hello, NAME"
Remember the uppercase H, the comma, and the space between words!
name = input("Enter your name: ")
print(f"Hello, {name}")

Secondly, ask the user for their age and convert it into a number.
Then, print out how many months that equals to (you'll have to multiply the age by 12).
age = int(input("Enter your age: "))
months = age * 12
print(months)

#  Sets, Tuples, Lists, Dictionaries


Lists: [] Lists are mutable and easily changed with .append and .remove methods
list1 = [value1, value2, value3]
list1.add(value4)
print(List1)

Sets: {} Sets do not keep order, printing results in random order. You can modify a set using the .add and .remove methods. Sets are useful for comparisons using the .difference() method. Sets will not contain duplicates
Example 1- difference method:
set1 = {value1, value2, value3}
set2 = {value4, value 1}
set1_but_not_set2 = set1.difference(set2)
print(set1_but_not_set2)

Example 2 - symmetric difference (values not in both sets):
set1 = {value1, value2, value3}
set2 = {value4, value 1}
not_in_both = set1.symmetric_difference(set2)
print(not_in_both)

Example 3 - Intersection (values in both sets):
set1 = {value1, value2, value3}
set2 = {value4, value 1}
one_and_two = set1.intersection(set2)
print(one_and_two)

Example 4 - Union (all values in all sets, no duplicates)
set1 = {value1, value2, value3}
set2 = {value4, value 1}
all_sets = set1.union(set2)
print(all_sets)



Tuples: () Tuples are immutable, as opposed to lists. If you want to add to a tuple, you must create a new tuple with the old tuple inside: tuple1 = (value1, value2, value3)
			newTuple = (tuple1, value4)

Dictionaries: Key-value store, defined with {} can be modified and added to. colons are only used inside the dictionary as bindings, not used in python for value assignment. Dictionaries cannot have duplicates, and the order is maintainedpost-python 3.7. tuples can be converted to dictionaries with the dict() function.
dictionary1 = {key1:value1, key2:value2, key3:vlaue3}
dictionary1[key4] = value4
print(dictionary1[1])

#  Length and sum


Sum
you can add together the integer values of a list with the sum() function.
List1 = [2,4,6,8]
total = sum(list1)
print(total)
20

You can also get the length of a list with the len() function. 
list1 = [2,4,6,8]
length = len(list1)
print(length)
4

These functions are especially handy for arithmetic on lists:
average = total / length
print(average)
5

## Lotto Exercise

lottery_numbers = {13, 21, 22, 5, 8}
 
"""
A player looks like this:
 
{
    'name': 'PLAYER_NAME',
    'numbers': {1, 2, 3, 4, 5}
}
 
Define a list with two players (you can come up with their names and numbers).
"""
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
 
For each of the two players, print out a string like this: "Player PLAYER_NAME got 3 numbers right.".
Of course, replace PLAYER_NAME by their name, and the 3 by the amount of numbers they matched with lottery_numbers.
You'll have to access each player's name and numbers, and calculate the intersection of their numbers with lottery_numbers.
Then construct a string and print it out.
 
Remember: the string must contain the player's name and the amount of numbers they got right!
name = players[0]["name"]
numbers = players[0]["numbers"].intersection(lottery_numbers)
print(f"Player {name} got {len(numbers)} numbers right.")


# Join Lists


you can join lists to make them more easy to read, by using the Join method

Example:
family = ["Tiffanie", "Teagan", "Adrian"]
print(f"My family is {family}.")

Result:
My family is ["Tiffanie", "Teagan", "Adrian"].

Joining uses a delimiter to separate out the list. For example:

family = ["Tiffanie", "Teagan", "Adrian"]
comma_separated = ", ".join(family)
print(f"My family is {comma_separated}.")

Result:
My family is Tiffanie, Teagan, Adrian.


# Control Flow


Control Flow is a blanket term for different structures and statements and basic decisions made by a program based on inputs from the user or other similar conditions, that ultimately result in a desired output or function. Control flow refers to the sequence in which the statements of a program are executed, including various structures and statements that control the flow of execution based on conditions, loops, and function calls. These structures and statements allow the program to make decisions, iterate over data, and execute code blocks selectively, ultimately leading to the desired output or behavior. Control flow is essential for programming as it determines the logic and order of operations within a program, enabling it to perform different tasks based on specific conditions or inputs.

## If/Elif/Else Statements


If statements allow your program to make decisions based on a Boolean value. the 'if' command executes an evaluation of a specific condition, and if true, it takes the true path of the tree, and if not, it takes the false path of the tree. 

Syntax:
if condition == condition:
	print("True.")
	print("Also True.")

print("This is not part of the if statement body.")

The if statement is initialized with the keyword "if" and evaluates the condition that follows it. The colon is necessary to define the body of the if statement, and the indentation defines what is contained within the body. Everything indented under the if statement will be contained within it, and once the indentation is broken, the if statement is over. 

Example:
name = "Name1"
user_name = input("Enter your username: ")

if user_name == name:
	print(f"Welcome back, {name}!")

it is possible to write multiple if statements for multiple conditions, however it is much simpler to convert the basic 'if' statement seen above into a compound if statement using the 'else' keyword. This will evaluate every other condition that does not meet the initial if statement as false.

Example:
name = "Name1"
user_name = input("Enter your username: ")

if user_name == name:
	print(f"Welcome back, {name}!")
else:
	print("Welcome, stranger.")


When an if statement is evaluated, Python will pass every value through the bool() function to evaluate whether it is True or False. The bool() result of an empty string will always evaluate to False. Generally, any value on its own is considered true by default, unless compared to another value.


friends = ["Rolf", "Bob", "James"]
family = ["Tiffanie", "Teagan", "Adrian"]

user_name = input("Please enter your name.")

if user_name in family:
	print("Welcome, Family.")

if user_name in friends:
	print("Welcome, friend.")
else:
	print("Welcome, stranger.")
	
Result:
Please enter your name: Tiffanie
Welcome, Family.
Welcome, stranger.

This result comes because of the logical execution of the example code. The value "Tiffanie" exists in the family list. When the code executes, it evaluates the first if statement, finds the true value, and prints the result. It then moves to the next if statement, evaluates it, and finds the false (else) value, and prints the result. The solution here is 'elif' to ensure that multiple conditions can be evaluated in a single statement and then a final else statement will be the result if all other conditions are false. 

Example:
friends = ["Rolf", "Bob", "James"]
family = ["Tiffanie", "Teagan", "Adrian"]

user_name = input("Please enter your name.")

if user_name in family:
	print("Welcome, Family.")
elif user_name in friends:
	print("Welcome, friend.")
else:
	print("Welcome, stranger.")
	
Result:
Please enter your name: Tiffanie
Welcome, Family.

 
There can be as many elif staetments as necessary, and remember that they are evaluated in order! The first one that runs, means that the others don't run. 

## While Loops

Loops are used to repeat things multiple times. A while loop will iterate through boolean conditions and run while the desired state is true. It is especially useful when repeating a process an undefined number of times- i.e. until a user tells the code to stop. 

Syntax: Similar to if statements, in that the loop must be initialized with a colon (:), and the body must be indented immediately beneath the while statement. 

Example:

is_learning = True

while is_learning:
	print("You are learning!")

This will print "You are learning!" to the console indefinitely, because the value is set to True. As long as the value is true, the while loop will keep iterating through and printing the desired output. Here is how we can get around this

is_learning = True

while is_learning:
	print("You are learning!")
is_learning = input("Are you still learning?")
	
Is the user enters yes, the while loop will evaluate the value of is_learningn as true, and iterate again. A blank or no value will result in the termination of the loop, as these values evaluate to False. Alternatively:

is_learning = True

while is_learning:
	print("You are learning!")
	is_learning = False
	
This will also work to terminate the loop, but does not offer the flexibility of input or value modification of the variable. 

Another option is to evaluate the user input as its own variable and do a simple comparison against the is_learning variable value. 

is_learning = True

while is_learning:
	print("You are learning!")
	user_input = input("Are you still learning?")
	is_learning = user_input == "yes"
	
This takes the initial True value of the is_learning variable and compares it to the user_input variable. If the user enters anything except "yes", then the while loop evaluates a False, and terminates; a yes input will result in the loop iterating again, and printing the "You are learning!" output to the console. This is a common way of structuring user menus, or places where users may need to repeat something multiple times. 

Example:
user_input = input("Do you wish to run the program? (yes/no): ")

while user_input == "yes":
	print("We are running!")
	user_input = input("Do you wish to run the program? (yes/no): ")
	
print("We stopped running.")

	
	
	
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
user_input = ...

user_input = input("Type p or q to see what happens.")

Then, begin a while loop that runs for as long as the user doesn't type 'q'.
Inside the loop, have an if statement that checks if the user typed 'p'.
   If they did, print "Hello"
Still inside the loop, ask the user again
user_input = ...

while user_input != "q":
    if user_input == "p":
        print("Hello")
  
    user_input = input("Once more, type p or q.")
       

    # user_input = input("Once more, type p or q.")
    



Very Common Example:
i = 0
while i < 20:
	print(f'Repeated {i} times.')
	i += 1

## For Loops

For loops, like While loops, are used to iterate through certain conditions and output depending on the evaluation of those conditions. Unlike While loops, however, For loops are used to repeat something a defined number of times. Python's approach to For loops is unique to other languages, which may use For Each. 

Syntax: The same as a While loop, but with For instead. 

family = ["Tiffanie", "Teagan", "Adrian"]

for member in family:
	print(member)

Result:
Tiffanie
Teagan
Adrian

The For loop reads each iterable (element of the list) as the new variable "member" and assigns a single value to that variable for each iteration of the list. It then prints each one, moving to the next with each iteration of the loop. This has a finite amount of times it can run, with the amount being equal to the number of elements in the list. For example, the new variable could be anything, as could the printed output.

Example: 

family = ["Tiffanie", "Teagan", "Adrian"]

for _in family:
	print("Hello world")
	
Result:
Hello world
Hello world
Hello world

Example:

elements = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for index in elements:
	print("Hello, world!")


You can also use the range keyword to iterate a for loop through a range of numbers:

for index in range (5, 10)
	print(index)
	
Result:
5
6
7
8
9

OR 

for index in range (2, 20, 3)
	print(index)

Result:
2
5
8
11
14
17


Example:
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
	
Result:
Jeff has a grade of 90.
Bob has a grade of 78.
Barb has a grade of 100.
Luke has a grade of 80.



Finding prime numbers exercise:

for n in range(2, 10):
	for x in range(2, n):
		if n % x == 0:
			print(f"{n} equals {x} * {n//x}")
			break
	else:
		print(f"{n} is a prime number.")
		
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
currencies = 0.8, 1.2
Usd, eur = currencies

This example takes the values usd and eur and assigns them to their respective tuple value, in the order that they are written. The first value of the tuple, 0.8, is now assigned to the new variable called usd.

Example:
friends = [{"Rolf", 25}, {"Bob", 34}, {"Jen", 37}, {"Anne", 22}]

for name, age in friends:
	print(name, age)
	
Result:
Rolf 25
Bob 34
Jen 37
Anne 22

But you could also add an f string to make the output more readable:

friends = [{"Rolf", 25}, {"Bob", 34}, {"Jen", 37}, {"Anne", 22}]

for name, age in friends:
	print(f"{name} is {age} years old.")
	
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
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Stopping production, faulty car found.")
		break
	print(f"This car is {status}.")
	
Result:
This car is ok.
This car is ok.
This car is ok.
This car is ok.
Stopping production, faulty car found.


The continue keyword allows the loop to continue while handling the defined parameter differently than the rest. 

Example:
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
	
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
cars = ["ok", "ok", "ok", "ok", "faulty", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
else:
	print("All cars built successfully. No faulty cars.")

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


cars = ["ok", "ok", "ok", "ok", "ok", "ok"]

for status in cars:
	if status == "faulty":
		print("Faulty car found. Continuing production.")
		continue
	print(f"This car is {status}.")
	print("Shipping to customer.")
else:
	print("All cars built successfully. No faulty cars.")

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
list = ["Name1", "Name2", "Name3", "Name4", "Name5"]

print(list1[1:3])
Result:
["Name2", "Name3"]

Slicing can be exclusionary, depending on the configuration of the colon and place numbers; for example:
list = ["Name1", "Name2", "Name3", "Name4", "Name5"]

print(list1[1:])
Result:
["Name2", "Name3", "Name4", "Name5"]

OR 

print(list1[:4])
Result:
["Name1", "Name2", "Name3", "Name4"]


You can also slice from the end of the list using negative numbers. 
Example:

print(list1[-3:])
Result:
["Name3", "Name4", "Name5"]

this counts backwards from the end o f the list, and output begins with that value, and counts forward from there. 

## Comprhensions
Comprehensions are a Python feature that allows the creation of new lists using elements from other lists. 

Example:
numbers = [0, 1, 2, 3, 4]
doubled_numbers = []

for number in numbers:
	doubled_numbers.append(number * 2)
	
print(doubled_numbers)

Result: [0, 2, 4, 6, 8]

But this is just a For loop. Using list comprehension, we can output the same result, but with much more succinct and efficient code.

Use list comprehension instead:
 
numbers = [0, 1, 2, 3, 4]
doubled_numbers = [number * 2 for number in numbers]

Result: [0, 2, 4, 6, 8]

This is the same as the For loop, but simpler in the coding. 

List comprehension can also be used for data normalization  
