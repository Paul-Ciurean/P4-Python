# Welcome to Python Practice.

## Here you will get to practice some exercises using python basics.

## Exercise 1:
### Write a program that calculates perimeter and area of a right-angled triangle.

<details>

<summary> Solution 1.0 </summary>

```
a = 5
b = 4
c = 3

perimeter = a + b + c
area = a * b / 2

print(perimeter)
print(area)

```
</details>

### Now, let's make it dynamic. What that means? Everytime we run the program, it will ask us to input values for a, b and c.

<details>

<summary> Solution 1.1 </summary>

```
a = float(input("Enter value for a:"))
b = float(input("Enter value for b:"))
c = float(input("Enter value for c:"))

perimeter = a + b + c
area = a * b / 2

print(perimeter)
print(area)
``` 

</details>

## Exercise 2: 

### Write a program that takes two numbers, checks which one is the biggest and return a message. Output should tell the biggest number or if the numbers are equals.

<details>

<summary> Solution 2.0 </summary>

```
a = 1234
b = 5423

if a > b:
    print("a is greater than b")
elif a < b:
    print("a is smaller than b")
else:
    print("a is equal with b")
```
</details>

### Extra: Make it dynamic and implement exception handling.

<details>

<summary> Solution 2.1 </summary>

```
try:
    a = float(input("Enter a:"))
    b = float(input("Enter b:"))

    if a > b:
        print("a is greater than b")
    elif a < b:
        print("a is smaller than b")
    else:
        print("a is equal with b")
except ValueError:
    print("Please enter numeric values!")
```    

</details>

## Exercise 3:

### Write a program that is going to give the grade of a student according to the score obtained.​

### Score >= 90 : ‘A’    80<=score<=89: ‘B’    70<=score<=79 : ‘C’    60<=score<=69: ‘D’    score<59: ‘F’

<details>

<summary> Solution 3.0 </summary>


```
score = float(input("Enter your score (0-100):"))

if score >= 90:
    print("A")
elif 80 <= score <= 89:
    print("B")
elif 70 <= score <= 79:
    print("C")
elif 60 <= score <= 69:
    print("D")
else:
    print("F")
```

</details>

### Extra: Force the user to chose only numbers between 0 and 100.

<details>

<summary> Solution 3.1 </summary>

```
while True:
    try:
        score = float(input("Enter your score (0-100): "))
        if 0 <= score <= 100:
            break
        else:
            print("Please enter a score between 0 and 100.")
    except ValueError:
        print("Please enter a valid numeric score.")

if score >= 90:
    print("A")
elif 80 <= score <= 89:
    print("B")
elif 70 <= score <= 79:
    print("C")
elif 60 <= score <= 69:
    print("D")
else:
    print("F")
```
</details>

## Exercise 4:
### Write a program that, given a number, it will play fizz buzz game.

<details>

<summary> Solution 4 </summary>

```
a = float(input("Give a number:"))

if a % 3 == 0 and a % 5 == 0:
    print("Fizz Buzz")
elif a % 3 == 0:
    print("Fizz")
elif a % 5 == 0:
    print("Buzz")
else:
    print(int(a))
```

</details>

## Exercise 5:
### Create a program to ask the user to guess the number that has been randomly generated. The user will be able to try continuously until it finds the correct number. The program should stop as soon as the number is found.​

### At each iteration the program will tell the user if the number is too high, too low or the correct one.

<details>

<summary> Solution 5.0 </summary>

```

import random

number = random.randint(1, 100)
guess = -1

while guess != number:
    guess = int(input("Enter your guess:"))
    if guess == number:
        print(f"Congratulation !!! The number is {number}")
    elif guess < number:
        print("Your guess is too low")
    else:
        print("Your guess is too high")


```

</details>

### Extra: Implement a way to assign only 5 attempts to the user. Each iteration should show the attempt left.​

<details>

<summary> Solution 5.1.0 </summary>

```
import random

number = random.randint(1, 100)
guess = ''
attempts = 5

while guess != number and attempts > 0:
    print(f"You have {attempts} attempts")
    guess = int(input("Enter your guess:"))
    if guess == number:
        print(f"Congratulation !!! The number is {number}")
    elif guess < number:
        print("Your guess is too low")
        attempts -= 1
    else:
        print("Your guess is too high")
        attempts -= 1
if attempts == 0:
    print(f"GAME OVER!!! No more attempts, the number to guess was {number}")
```

</details>


<details>

<summary> Solution 5.1.1</summary>

```
import random

number = random.randint(1,100)
guess = -1
attempts = 5

while guess != number and attempts != 0:
    guess = int(input("Guess the number:"))
    if guess == number:
        print(f"Well done!!! You guessed it!!! The number is {number}")
    elif guess < number:
        print("Your guess is too low!")
        attempts -= 1
        print(f"You have {attempts} attempts left")
    else:
        print("Your guess is too high!")
        attempts -= 1
        print(f"You have {attempts} attempts left")
if attempts == 0:
    print(f"You failed!! The number was {number}.")

```

</details>


## Exercise 6: 
### Write a program that checks if a word is a palindrome.

<details>

<summary> Solution 6.0 </summary>

```
word = "civic"

reversed_word = word[::-1]

if word == reversed_word:
    print("Palindrome!!!")
else:
    print("Not palindrome")
```

</details>


<details>

<summary> Solution 6.1 </summary>

```
name1 = 'david'

if name1 == name1[::-1]:
    print("Palindrome!!! ")
else:
    print("Not Palindrome!!! ")


name2 = 'civic'

if name2 == name2[::-1]:
    print("Palindrome!!! ")
else:
    print("Not Palindrome!!! ")

```

</details>

### Extra: Make it dynamic:

<details>

<summary> Solution 6.2 </summary>

```
word = input("Enter a word: ")

reversed_word = word[::-1]

if word == reversed_word:
    print("Palindrome!!!")
else:
    print("Not palindrome")
```

</details>

## Exercise 7:
### Write a program to split a given string on hyphens and display each substring​
### str1 = "Emma-is-a-data-scientist"
### Output must have each sub-string on a new line

<details>

<summary> Solution 7.1 </summary>

```
str1 = "Emma-is-a-data-scientist"

print("This is the original statement: ", str1)

str2 = str1.split("-")

for str in str2:
    print(str)
```
</details>

<details>

<summary> Solution 7.2 </summary>

```
str1 = "Emma-is-a-data-scientist"
print("Original string is: ", str1)

sub_string = str1.split("-")

print("Display each substring")
for sub in sub_string:
    print(sub)
```
</details>

## Exercise 8:
### Given the following sentence, find a way to remove all the extra spaces and print the same sentence with just one space between words.

```
paragraph = "Argentina  wins   football   world cup 2022 in a nail biting final match that led to a       spectacular    penalty shootout. Football lovers   across the world   hailed   it as one of the most    memorable   matches."
```


<details>

<summary> Solution 8 </summary>

```
paragraph = "Argentina  wins   football   world cup 2022 in a nail biting final match that led to a       spectacular    penalty shootout. Football lovers   across the world   hailed   it as one of the most    memorable   matches."

new_paragraph = ' '.join(paragraph.split())
print(new_paragraph)
```
</details>


## Exercise 9:
### Write a program that count all letters, digits and special symbols from a given string:
### Input: word = "P@#yn26at^&i5ve"
### Output: letters = 8, digits = 3, symbols = 4 

<details>

<summary> Solution 9 </summary>

```
word = "P@#yn26at^&i5ve"

letters = 0
digits = 0
symbols = 0

for char in word:
    if char.isalpha():
        letters += 1
    elif char.isdigit():
        digits += 1
    else:
        symbols += 1

print(f"The word has {letters} letters, {digits} digits and {symbols} symbols")
```

</details>

## Exercise 10:
### Write a script that, given a sentence and a word it will tell if the word is included in the sentence.

<details>

<summary> Solution 10.1 </summary>

```
inp = "Alice's cat is in the hat"
inp2 = "cat"

words = inp.split()
if inp2 in words:
    print(f"The word {inp2} is in the sentence")
else:
    print(f"The word {inp2} is not in the sentence")


```

</details>

### Extra: Make it dynamic:

<details>

<summary> Solution 10.2 </summary>

```
inp = input("Please insert a sentence: ")
inp2 = input("Please insert a word to be searched: ")

words = inp.split()
if inp2 in words:
    print(f"The word {inp2} is in the sentence")
else:
    print(f"The word {inp2} is not in the sentence")

```

</details>


## Exercise 11:
### Write a script that given an integer, print a staircase made of number as shown below:
### Given the number 7:
- 1
- 22
- 333
- 4444
- 55555
- 666666
- 7777777

### Hint: can you nest for loops?

<details>

<summary> Solution 11.1 </summary>

```
n = 7
for num in range(1, n + 1):
    for n in range(num):
        print(num, end=" ")

    print(" ")
```

</details>

### Extra: Make it dynamic:

<details>

<summary> Solution 11.2 </summary>

```
n = int(input("Enter a number: "))
for num in range(1, n + 1):
    for n in range(num):
        print(num, end=" ")

    print(" ")
```

</details>