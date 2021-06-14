# Python Exercise and Projects

## Project 1: Band name generator
This progam is used to generate the band name by taking two parameters from the user i.e. city name and pet name.

```python
#1. Create a greeting for your program.
print("Welcome to the Band Name Generator")
#2. Ask the user for the city that they grew up in.
city_name = input("What's name of the city you grew up in?\n")
#3. Ask the user for the name of a pet.
pet_name = input("What's your pet name?\n")
#4. Combine the name of their city and pet and show them their band name.
print("Your band name could be " + city_name + " " + pet_name + "\n")
```

![](/images/1.2.png)

## Exercise 1

Write a program that adds the digits in a 2 digit number. e.g. if the input was 35, then the output should be 3 + 5 = 8.

```python
two_digit_number = input("Type a two digit number: ")

num1 = int(two_digit_number[0])
num2 = int(two_digit_number[1])
print(num1 + num2)
```

![](/images/2.2.png)

## Exercise 2

Write a program that calculates the Body Mass Index (BMI) from a user's weight and height.

```python
height = input("enter your height in m: ")
weight = input("enter your weight in kg: ")

new_height = float(height)
new_weight = int(weight)

bmi = int(new_weight / (new_height**2))
print("Your bmi is {}".format(bmi))
```

![](/images/3.2.png)

## Exercise 3

Create a program using maths and f-Strings that tells us how many days, weeks, months we have left if we live until 90 years old.

```python
age = input("What is your current age?")

new_age = int(age)
days = (90*365) - (new_age * 365) 
weeks = (90*52) - (new_age * 52)
months = (90*12) - (new_age * 12)

print(f"You have {days} days, {weeks} weeks, and {months} months left")
```

![](/images/4.2.png)

## Project 2: TIP Calculator

```python
#If the bill was $150.00, split between 5 people, with 12% tip. 
#Each person should pay (150.00 / 5) * 1.12 = 33.6
#Format the result to 2 decimal places = 33.60

print("Welcome to the tip calculator.")
total_bill = float(input("What was the total bill? $"))
percentage = int(input("What percentage tip would you like to give? 10, 12, or 15? "))
split_bill = int(input("How many people to split the bill? "))

amount_to_be_paid = (total_bill / split_bill) * (1 + (percentage/100))
final_amount = round(amount_to_be_paid,2)
final_amount = "{:.2f}".format(amount_to_be_paid)
print(f"Each person should pay: ${final_amount}")
```

![](/images/5.2.png)

## Exercise 4

Write a program that works out whether if a given number is an odd or even number.

```python
number = int(input("Which number do you want to check? "))

if number%2==0:
  print("This is an even number")
else:
  print("This is an odd number")
```

![](/images/6.2.png)

## Exercise 5

Write a program that interprets the Body Mass Index (BMI) based on a user's weight and height.

It should tell them the interpretation of their BMI based on the BMI value.

- Under 18.5 they are underweight
- Over 18.5 but below 25 they have a normal weight
- Over 25 but below 30 they are slightly overweight
- Over 30 but below 35 they are obese
- Above 35 they are clinically obese.

```python
height = float(input("enter your height in m: "))
weight = float(input("enter your weight in kg: "))

bmi = round(weight / (height**2))
if bmi < 18.5:
  print(f"Your BMI is {bmi}, you are underweight")
elif bmi < 25:
  print(f"Your BMI is {bmi}, you are normal weight")
elif bmi < 30:
  print(f"Your BMI is {bmi}, you are slightly overweight")
elif bmi < 35:
  print(f"Your BMI is {bmi}, you are obese")
else:
  print(f"Your BMI is {bmi}, you are clinically obese")
```

![](/images/7.2.png)

## Exercise 6

Write a program that works out whether if a given year is a leap year. A normal year has 365 days, leap years have 366, with an extra day in February. This is how you work out whether if a particular year is a leap year:
- on every year that is evenly divisible by 4 
- **except** every year that is evenly divisible by 100 
- **unless** the year is also evenly divisible by 400

```python
year = int(input("Which year do you want to check? "))

if year%4==0:
  if year%100==0:
    if year%400==0:
      print("This is a leap Year")
    else:
      print("Not a leap year")
  else:
    print("This is a leap year")    
else:
  print("Not a leap year")
```

![](/images/8.2.png)

## Exercise 7

Congratulations, you've got a job at Python Pizza. Your first job is to build an automatic pizza order program.

Based on a user's order, work out their final bill.

- Small Pizza: $15
- Small Pizza: $15
- Medium Pizza: $20
- Medium Pizza: $20
- Large Pizza: $25
- Large Pizza: $25
- Pepperoni for Small Pizza: +$2
- Pepperoni for Small Pizza: +$2
- Pepperoni for Medium or Large Pizza: +$3
- Pepperoni for Medium or Large Pizza: +$3
- Extra cheese for any size pizza: + $1

```python
print("Welcome to Python Pizza Deliveries!")
size = input("What size pizza do you want? S, M, or L ")
add_pepperoni = input("Do you want pepperoni? Y or N ")
extra_cheese = input("Do you want extra cheese? Y or N ")

bill = 0

if size == "S":
  bill += 15
elif size == "M":
  bill += 20
else:
  bill += 25

if add_pepperoni == "Y":
  if size == "S":
    bill += 2
  else:
    bill += 3
    
if extra_cheese == "Y":
  bill += 1
  
print(f"Your final bill is: ${bill}.")
```

![](/images/9.2.png)

## Exercise 8

Write a program that tests the compatibility between two people.

To work out the love score between two people:

Take both people's names and check for the number of times the letters in the word TRUE occurs. Then check for the number of times the letters in the word LOVE occurs. Then combine these numbers to make a 2 digit number.

- For Love Scores less than 10 or greater than 90, the message should be: "Your score is **x**, you go together like coke and mentos."

- For Love Scores between 40 and 50, the message should be: "Your score is **y**, you are alright together."

- Otherwise, the message will just be their score. e.g.: "Your score is **z**."

```python
print("Welcome to the Love Calculator!")
name1 = input("What is your name? \n")
name2 = input("What is their name? \n")

concatenated_string = name1 + name2
string_in_lowercase = concatenated_string.lower()

t = string_in_lowercase.count("t")
r = string_in_lowercase.count("r")
u = string_in_lowercase.count("u")
e = string_in_lowercase.count("e")

true = t + r + u + e

l = string_in_lowercase.count("l")
o = string_in_lowercase.count("o")
v = string_in_lowercase.count("v")
e = string_in_lowercase.count("e")

love = l + o + v + e
love_score = int(str(true) + str(love))

if love_score < 10 or love_score > 90:
  print(f"Your score is {love_score}, you go together like coke and mentos.")
elif love_score >= 40 and love_score <= 50:
  print(f"Your score is {love_score}, you are alright together.")
else:
  print(f"Your score is {love_score}")
```

![](/images/10.2.png)

## Project 3: Treasure Island

```python
print('''
*******************************************************************************
          |                   |                  |                     |
 _________|________________.=""_;=.______________|_____________________|_______
|                   |  ,-"_,=""     `"=.|                  |
|___________________|__"=._o`"-._        `"=.______________|___________________
          |                `"=._o`"=._      _`"=._                     |
 _________|_____________________:=._o "=._."_.-="'"=.__________________|_______
|                   |    __.--" , ; `"=._o." ,-"""-._ ".   |
|___________________|_._"  ,. .` ` `` ,  `"-._"-._   ". '__|___________________
          |           |o`"=._` , "` `; .". ,  "-._"-._; ;              |
 _________|___________| ;`-.o`"=._; ." ` '`."\` . "-._ /_______________|_______
|                   | |o;    `"-.o`"=._``  '` " ,__.--o;   |
|___________________|_| ;     (#) `-.o `"=.`_.--"_o.-; ;___|___________________
____/______/______/___|o;._    "      `".o|o_.--"    ;o;____/______/______/____
/______/______/______/_"=._o--._        ; | ;        ; ;/______/______/______/_
____/______/______/______/__"=._o--._   ;o|o;     _._;o;____/______/______/____
/______/______/______/______/____"=._o._; | ;_.--"o.--"_/______/______/______/_
____/______/______/______/______/_____"=.o|o_.--""___/______/______/______/____
/______/______/______/______/______/______/______/______/______/______/_____ /
*******************************************************************************
''')
print("Welcome to Treasure Island.")
print("Your mission is to find the treasure.") 

input1 = input('You are at a cross road. Where do you want to go? Type "left" or "right" \n' ).lower()

if input1 == "left":
  input2 = input('You came to a lake. There is an island in the middle of the lake. Type "wait" to wait for a boat. Type "swim" to swim across. \n').lower()
  if input2 == "wait":
    input3 = input('You arrive at the island unharmed. There is a house with 3 doors. One red, one yellow and one blue, Which color do you choose? \n').lower()
    if input3 == "yellow":
      print("You WIN \n")
    elif input3 == "red":
      print("Burned by fire. Game Over! \n")
    elif input3 == "blue":
      print("Eaten by beasts. Game Over! \n")
    else:
      print("Game Over! \n")
  else:
    print("Attacked by trout. Game Over! \n")
else:
  print("Fall into a hole. Game Over! \n")
```

![](/images/11.3.png)

## Exercise 9

Write a virtual coin toss program which will randomly tell the user "Heads" or "Tails".

```python
import random

random_number = random.randint(0,1)
if random_number == 1:
  print("Heads")
else:
  print("Tails")
```

![](/images/12.2.png)

![](/images/12.3.png)

## Exercise 10

You are going to write a program which will select a random name from a list of names. The person selected will have to pay for everybody's food bill.
**Important**: *You are not allowed to use the choice() function.*

```python
import random
# Split string method
names_string = input("Give me everybody's names, separated by a comma. ")
names = names_string.split(", ")

names_length = len(names)

random_choice = random.randint(0, names_length-1)
who_will_buy_meal = names[random_choice]

print(who_will_buy_meal + " is going to buy the meal today")
```

![](/images/13.2.png)

## Exercise 11

Write a program which will mark a spot with an X.

```python
row1 = ["⬜️","⬜️","⬜️"]
row2 = ["⬜️","⬜️","⬜️"]
row3 = ["⬜️","⬜️","⬜️"]
map = [row1, row2, row3]
print(f"{row1}\n{row2}\n{row3}")
position = input("Where do you want to put the treasure? ")

column = int(position[0])
row = int(position[1])

map[row-1][column-1] = 'x'

print(f"{row1}\n{row2}\n{row3}")
```

![](/images/14.2.png)

## Project 4: Rock Paper Scissor

```python
import random
rock = '''
    _______
---'   ____)
      (_____)
      (_____)
      (____)
---.__(___)
'''

paper = '''
    _______
---'   ____)____
          ______)
          _______)
         _______)
---.__________)
'''

scissors = '''
    _______
---'   ____)____
          ______)
       __________)
      (____)
---.__(___)
'''

user = int(input("What do you choose? Type 0 for Rock, 1 for Paper or 2 for Scissors.\n"))

if user == 0:
  print(rock)
elif user == 1:
  print(paper)
elif user == 2:
  print(scissors)
else:
  print("Choose from the given options")

print("Computer chooses:")  
computer = random.randint(0,2)

if computer == 0:
  print(rock)
elif computer == 1:
  print(paper)
elif computer == 2:
  print(scissors)

if (user == 0 and computer == 0) or (user == 1 and computer == 1)or (user == 2 and computer == 2) :
  print("Its a tie")
elif user == 0 and computer == 1:
  print("Computer wins")
elif user == 0 and computer == 2:
  print("User Wins")
elif user == 1 and computer == 0:
  print("User Wins")
elif user == 1 and computer == 2:
  print("Computer wins")
elif user == 2 and computer == 0:
  print("Computer Wins")
elif user == 2 and computer == 1:
  print("User Wins")
```

![](/images/15.4.png)

## Exercise 12

Write a program that calculates the average student height from a List of heights.e.g. student_heights = [180, 124, 165, 173, 189, 169, 146]

**Important:** You should not use the sum() or len() functions in your answer. You should try to replicate their functionality using for loops.

```python
student_heights = input("Input a list of student heights ").split()
for n in range(0, len(student_heights)):
  student_heights[n] = int(student_heights[n])

# This replicates the functionality of "sum" function
total_height = 0
for height in student_heights:
  total_height += height

# This replicates the functionality of "len" function
number_of_students = 0
for students in student_heights:
  number_of_students += 1

average_height = round(total_height / number_of_students)
print(average_height)
```

![](/images/16.2.png)

## Exercise 13

Write a program that calculates the highest score from a List of scores.e.g. student_scores = [78, 65, 89, 86, 55, 91, 64, 89]

**Important:** You are not allowed to use the max or min functions.

```python
student_scores = input("Input a list of student scores ").split()
for n in range(0, len(student_scores)):
  student_scores[n] = int(student_scores[n])
print(student_scores)

highest_scores = 0
for score in student_scores:
  if score > highest_scores:
    highest_scores = score
print(f"The highest score in the class is {highest_scores}")
```

![](/images/17.2.png)

## Exercise 14

Write a program that calculates the sum of all the even numbers from 1 to 100. Thus, the first even number would be 2 and the last one is 100:
i.e. 2 + 4 + 6 + 8 +10 ... + 98 + 100

**Important:** There should only be 1 print statement in your console output. It should just print the final total and not every step of the calculation.

```python
total = 0
for number in range(2, 101, 2):
  total += number
print(total)
```

![](/images/18.2.png)

## Exercise 15

Write a program that automatically prints the solution to the FizzBuzz game.
- Your program should print each number from 1 to 100 in turn.
- When the number is divisible by 3 then instead of printing the number it should print "Fizz".
- When the number is divisible by 5, then instead of printing the number it should print "Buzz". 
- When the number is divisible by 5, then instead of printing the number it should print "Buzz". 
- And if the number is divisible by both 3 and 5 e.g. 15 then instead of the number it should print "FizzBuzz"

```python
for number in range(1, 101):
  if (number % 3 == 0) and (number % 5 == 0):
    print("FizzBuzz")
  elif (number % 3 == 0):
    print("Fizz")
  elif (number % 5 == 0):
    print("Buzz")
  else:
    print(number)
```

![](/images/19.2.png)

![](/images/19.3.png)

![](/images/19.4.png)

## Project 5: Password Generator

1. Easy level approach to generate a password:

```python
#Password Generator Project
import random
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']

print("Welcome to the PyPassword Generator!")
nr_letters= int(input("How many letters would you like in your password?\n")) 
nr_symbols = int(input(f"How many symbols would you like?\n"))
nr_numbers = int(input(f"How many numbers would you like?\n"))

#Eazy Level - Order not randomised:e.g. 4 letter, 2 symbol, 2 number = JduE&!91
password = ""

for char in range(1, nr_letters+1):
  password += random.choice(letters)

for char in range(1, nr_symbols+1):
  password += random.choice(symbols)

for char in range(1, nr_numbers+1):
  password += random.choice(numbers)

print(f"Your password is: {password}")
```

   ![](/images/20.2.png)

2. High level approach to generate a password:

```python
#Password Generator Project
import random
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']

print("Welcome to the PyPassword Generator!")
nr_letters= int(input("How many letters would you like in your password?\n")) 
nr_symbols = int(input(f"How many symbols would you like?\n"))
nr_numbers = int(input(f"How many numbers would you like?\n"))

#Hard Level - Order of characters randomised:e.g. 4 letter, 2 symbol, 2 number = g^2jk8&P
password_list = []

for char in range(1, nr_letters+1):
  password_list += random.choice(letters)

for char in range(1, nr_symbols+1):
  password_list += random.choice(symbols)

for char in range(1, nr_numbers+1):
  password_list += random.choice(numbers)

random.shuffle(password_list)

password = ""
for char in password_list:
  password += char

print(f"Your password is: {password}")
```
   
   ![](/images/20.5.png)
   
## Exercise 16

Write a code for the hurdle loop challenge inside www.reeborg.ca/

1. Long code
```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()
    
def wall_in_front():
    turn_left()
    move()

def front_is_clear():
    move()
    turn_right()
    move()
    turn_left()

def run():
    wall_in_front()
    turn_right()
    front_is_clear()

move()
run()
move()
run()
move()
run()
move()
run()
move()
run()
move()
run()
```

![](/images/21.1.png)

2. Short code

```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()
    
def jump():
    move()
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()
    
for step in range(6):
    jump()
```

![](/images/21.2.png)

## Exercise 17

Write a code for the hurdle loop challenge inside www.reeborg.ca/ where the flag position is random.

```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()
    
def jump():
    move()
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()
    
while not at_goal():
    jump()
```

![](/images/22.1.png)

![](/images/22.2.png)

## Exercise 18

Write a code for the hurdle loop challenge inside www.reeborg.ca/ where the hurdle position is random.

```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()
    
def jump():
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()

    
while not at_goal():
    if wall_in_front():
        jump()
    else:
        move()
```

![](/images/23.1.png)

![](/images/23.2.png)

## Exercise 19

Write a code for the hurdle loop challenge inside www.reeborg.ca/ where the length of the hurdles is not constant.

```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()
    
def jump():
    turn_left()
    while wall_on_right():
        move()
        
    turn_right()
    move()
    turn_right()
    while front_is_clear():
        move()
        
    turn_left()

while not at_goal():
    if wall_in_front():
        jump()
    else:
        move()
```

![](/images/24.1.png)

![](/images/24.2.png)

## Project 6: Hangman

### Step 1

```python
#Step 1 
import random
word_list = ["aardvark", "baboon", "camel"]

#Randomly choose a word from the word_list and assign it to a variable called chosen_word.

chosen_word = random.choice(word_list)

#Ask the user to guess a letter and assign their answer to a variable called guess. Make guess lowercase.

guess = input("Guess a letter: ").lower()

#Check if the letter the user guessed (guess) is one of the letters in the chosen_word.

for letter in chosen_word:
  if letter == guess:
    print("Right")
  else:
    print("wrong")
```

![](/images/25.1.png)

### Step 2

```python
#Step 2

import random
word_list = ["aardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create an empty List called display.
#For each letter in the chosen_word, add a "_" to 'display'.
#So if the chosen_word was "apple", display should be ["_", "_", "_", "_", "_"] with 5 "_" representing each letter to guess.

guess = input("Guess a letter: ").lower()
display = []
word_length = len(chosen_word)
for letters in chosen_word:
  display.append("_")


#Loop through each position in the chosen_word;
#If the letter at that position matches 'guess' then reveal that letter in the display at that position.
#e.g. If the user guessed "p" and the chosen word was "apple", then display should be ["_", "p", "p", "_", "_"].

for position in range(word_length):
  letter = chosen_word[position]
  if letter == guess:
    display[position] = letter


#Print 'display' and you should see the guessed letter in the correct position and every other letter replace with "_".
#Hint - Don't worry about getting the user to guess the next letter. We'll tackle that in step 3.

print(display)
```

![](/images/25.2.png)

### Step 3

```python
#Step 3

import random
word_list = ["aardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)
word_length = len(chosen_word)

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"

#Use a while loop to let the user guess again. The loop should only stop once the user has guessed all the letters in the chosen_word and 'display' has no more blanks ("_"). Then you can tell the user they've won.

end_of_game = False

while not end_of_game:
  guess = input("Guess a letter: ").lower()

  #Check guessed letter
  for position in range(word_length):
      letter = chosen_word[position]
      print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
      if letter == guess:
          display[position] = letter

  print(display)

  if "_" not in display:
    end_of_game = True
    print("You Win '.'")
```

![](/images/25.3.png)

### Step 4

```python
#Step 4

import random

stages = ['''
  +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|   |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
  |   |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
      |
      |
      |
=========
''', '''
  +---+
  |   |
      |
      |
      |
      |
=========
''']

end_of_game = False
word_list = ["ardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)
word_length = len(chosen_word)

#Create a variable called 'lives' to keep track of the number of lives left. 
#Set 'lives' to equal 6.

lives = 6

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"

while not end_of_game:
    guess = input("Guess a letter: ").lower()

    #Check guessed letter
    for position in range(word_length):
        letter = chosen_word[position]
        # print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
        if letter == guess:
            display[position] = letter

    #If guess is not a letter in the chosen_word,
    #Then reduce 'lives' by 1. 
    #If lives goes down to 0 then the game should 
    #stop and it should print "You lose."
    if guess not in chosen_word:
      lives -= 1
      if lives == 0:
        end_of_game = True
        print("You Lose")

    #Join all the elements in the list and turn it into a String.
    print(f"{' '.join(display)}")

    #Check if user has got all letters.
    if "_" not in display:
        end_of_game = True
        print("You win.")

    #Print the ASCII art from 'stages' that corresponds to the current number of 'lives' the user has remaining.

    print(stages[lives])
```

![](/images/25.4.png)

### Step 5

```python
#Step 5
from replit import clear
import random
from hangman_words import word_list 
from hangman_art import stages

#Update the word list to use the 'word_list' from hangman_words.py
#Delete this line: word_list = ["ardvark", "baboon", "camel"]

chosen_word = random.choice(word_list)
word_length = len(chosen_word)

end_of_game = False
lives = 6

#Import the logo from hangman_art.py and print it at the start of the game.
from hangman_art import logo
print(logo)
#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"

while not end_of_game:
    guess = input("Guess a letter: ").lower()

    clear()
    #If the user has entered a letter they've already guessed, print the letter and let them know.
    if guess in display:
      print(f"You already guessed {guess}")

    #Check guessed letter
    for position in range(word_length):
        letter = chosen_word[position]
        #print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
        if letter == guess:
            display[position] = letter

    #Check if user is wrong.
    if guess not in chosen_word:
        #If the letter is not in the chosen_word, print out the letter and let them know it's not in the word.
        print(f"You already guessed {guess}, that's not in a word")
        lives -= 1
        if letter not in chosen_word:
          print(f"You entered the letter {letter}, which not in a chosen word")
        if lives == 0:
            end_of_game = True
            print("You lose.")

    #Join all the elements in the list and turn it into a String.
    print(f"{' '.join(display)}")

    #Check if user has got all letters.
    if "_" not in display:
        end_of_game = True
        print("You win.")

    #Import the stages from hangman_art.py and make this error go away.
    print(stages[lives])
```

![](/images/25.5.png)

![](/images/25.6.png)

![](/images/25.7.png)

![](/images/25.8.png)

## Exercise 20

You are painting a wall. The instructions on the paint can says that 1 can of paint can cover 5 square meters of wall. Given a random height and width of wall, calculate how many cans of paint you'll need to buy.

```python
import math

def paint_calc(height, width, cover):
  area = (height*width)
  number_of_cans = math.ceil(area/cover)
  print(f"You'll need {number_of_cans} cans of paint.")

test_h = int(input("Height of wall: "))
test_w = int(input("Width of wall: "))
coverage = 5
paint_calc(height=test_h, width=test_w, cover=coverage)
```

![](/images/26.1.png)

## Exercise 21

Write a function that checks whether if the number passed is a prime number or not.

```python
def prime_checker(number):
  is_prime = True
  for i in range(2, number):
    if number%i == 0:
      is_prime = False
  
  if is_prime:
    print("It's a prime number.")
  else:
    print("It's not a prime number.")

n = int(input("Check this number: "))
prime_checker(number=n)
```

![](/images/27.1.png)

![](/images/27.2.png)

## Exercise 22

You have access to a database of student_scores in the format of a dictionary. The keys in student_scores are the names of the students and the values are their exam scores.
Write a program that converts their scores to grades. By the end of your program, you should have a new dictionary called student_grades that should contain student names for keys and their grades for values.

```python
student_scores = {
  "Harry": 81,
  "Ron": 78,
  "Hermione": 99, 
  "Draco": 74,
  "Neville": 62,
}

student_grades = {}

for student in student_scores:
  if student_scores[student] > 90:
    student_grades[student] = "Outstanding"
  elif student_scores[student] > 80:
    student_grades[student] = "Exceeds Expectation"
  elif student_scores[student] > 70:
    student_grades[student] = "Acceptable"
  else: 
    student_grades[student] = "Fail"

print(student_grades)
```

![](/images/28.1.png)

## Exercise 23

Write a program that adds to a travel_log. You can see a travel_log which is a List that contains 2 Dictionaries. Write a function that will work with the following line of code on line 21 to add the entry for Russia to the travel_log.

```python
travel_log = [
{
  "country": "France",
  "visits": 12,
  "cities": ["Paris", "Lille", "Dijon"]
},
{
  "country": "Germany",
  "visits": 5,
  "cities": ["Berlin", "Hamburg", "Stuttgart"]
},
]

def add_new_country(country_name,no_visits,no_cities):
  new_country = {}
  new_country["country"] = country_name
  new_country["visits"] = no_visits
  new_country["cities"] = no_cities
  travel_log.append(new_country)


add_new_country("Russia", 2, ["Moscow", "Saint Petersburg"])
print(travel_log)
```

![](/images/29.1.png)

## Project 7: Secret Auction

```python
from replit import clear

from art import logo

print(logo)

print("Welcome to the secret auction program")

bids = {}
bidding_finished = False

def find_highest_bidder(bidding_record):
  highest_bid = 0
  winner = ""
  for bidder in bidding_record:
    bid_amount = bidding_record[bidder]
    if bid_amount > highest_bid:
      highest_bid = bid_amount
      winner = bidder
  print(f"The winner is {winner} with a bid of ${highest_bid}")

while not bidding_finished:
  name = input("What is your name?: ")
  price = int(input("What's your bid?: $"))
  bids[name] = price
  should_continue = input("Are there any other bidders? Type 'yes' or 'no'. \n")
  if should_continue == "no":
    bidding_finished = True
    find_highest_bidder(bids)
  elif should_continue == "yes":
    clear()
```    

![](/images/30.1.png)

![](/images/30.2.png)

![](/images/30.3.png)
