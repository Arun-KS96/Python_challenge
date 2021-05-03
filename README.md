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

![](/images/12.1.png)

![](/images/12.2.png)

![](/images/12.3.png)

## Exercise 10

You are going to write a program which will select a random name from a list of names. The person selected will have to pay for everybody's food bill.
**Important**: *You are not allowed to use the choice() function.*

![](/images/13.1.png)

![](/images/13.2.png)

## Exercise 11

Write a program which will mark a spot with an X.

![](/images/14.1.png)

![](/images/14.2.png)

## Project 4: Rock Paper Scissor

![](/images/15.1.png)

![](/images/15.2.png)

![](/images/15.3.png)

![](/images/15.4.png)

## Exercise 12

Write a program that calculates the average student height from a List of heights.e.g. student_heights = [180, 124, 165, 173, 189, 169, 146]

**Important:** You should not use the sum() or len() functions in your answer. You should try to replicate their functionality using for loops.

![](/images/16.1.png)

![](/images/16.2.png)

## Exercise 13

Write a program that calculates the highest score from a List of scores.e.g. student_scores = [78, 65, 89, 86, 55, 91, 64, 89]

**Important:** You are not allowed to use the max or min functions.

![](/images/17.1.png)

![](/images/17.2.png)

## Exercise 14

Write a program that calculates the sum of all the even numbers from 1 to 100. Thus, the first even number would be 2 and the last one is 100:
i.e. 2 + 4 + 6 + 8 +10 ... + 98 + 100

**Important:** There should only be 1 print statement in your console output. It should just print the final total and not every step of the calculation.

![](/images/18.1.png)

![](/images/18.2.png)

## Exercise 15

Write a program that automatically prints the solution to the FizzBuzz game.
- Your program should print each number from 1 to 100 in turn.
- When the number is divisible by 3 then instead of printing the number it should print "Fizz".
- When the number is divisible by 5, then instead of printing the number it should print "Buzz". 
- When the number is divisible by 5, then instead of printing the number it should print "Buzz". 
- And if the number is divisible by both 3 and 5 e.g. 15 then instead of the number it should print "FizzBuzz"

![](/images/19.1.png)

![](/images/19.2.png)

![](/images/19.3.png)

![](/images/19.4.png)

## Project 5: Password Generator

1. Easy level approach to generate a password:

   ![](/images/20.1.png)

   ![](/images/20.2.png)

2. High level approach to generate a password:

   ![](/images/20.3.png)

   ![](/images/20.4.png)
   
   ![](/images/20.5.png)
