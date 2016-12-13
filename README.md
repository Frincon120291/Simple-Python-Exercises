# Simple-Python-Exercises
Exercises 1 -46


# Ex. 39 A Guessing Game 

import random

ranNum = random.randrange(1,40)

tooLow = "Guess is too low"
tooHigh = "Guess is too high"
count = 0

name = raw_input("Hello!What is your name?\n")
print("Well %s, I am thinking of a number "+
 "between 1 and 40.")% name
guess = int(raw_input("Take a guess:\n" )) # changes input
# to a int rather than string

while guess != ranNum: # continues until guessed correctly
    if guess > ranNum:
        print (tooHigh)
        guess = int(raw_input("Take a new guess:\n" ))

    else:
        print(tooLow)
        guess = int(raw_input("Take a new guess:\n" ))
    count +=1
if guess == ranNum: # only true if guess is right
    count +=1
    count = str(count)
    print ("Good Job " + name +"! You guessed my number"
    + " in " + count + " guesses!")



# Ex. 40 An anagram Game


import random

correct ="Correct!"
GivenWord = " Color word Anagram:"

with open("colors.txt") as color_file:
    words = color_file.read().split()
    color = random.choice(words)


letters = list(color) # makes the letters of the word into a list
random.shuffle(letters)# shuffles letters
shuffled = ''.join(letters) # rejoins letters to make anagram
guess = raw_input("Guess the Color word: "+shuffled+"\n")


while guess != color :# true until guessed correctly
    guess = raw_input("Guess the Color word:\n")

if guess == color :
    print(correct)
