---
layout: project
type: project
image: img/Screenshot Bjack.png
title: "BlackJack"
date: 2024-08-02
labels:
  - Python
summary: "Developed BlackJack card game in python"
---
The goal of this project was to test my skills as a programmer by using concepts I have learned in my classes and to put htem into one program. Blackjack required loops, classes, if statements, etc. Creating this program help to refresh concepts and to practice developing code from scratch. Building from scratch helped me to build a process to go through that would help me as a developer to create better code effiecently.

I worked on this project on my own with no contributors. I only was rsponsible for creating a draw function the would add cards to an array, creatin a fucntionality that tranforms royals (J, Q, K, A) in to proper numbers, and terst for all errors to write runable code. This took a lot of drawing and mapping the function to figure out and understand what exactly I was tring to code.
**What is BlackJack?**

BlakcJack is a card game where you as a player play against the dealer to try to out score the dealer. The best hand possible in the game is 21 which "BlackJack" and you win, but go over 21 or have less points than the dealer then you lose. In the images below will show you examples of a good hand, a bad hand/bust, and a BlackJack.

<div class="text-center p-4">
 <img src="https://www.kjartan.co.uk/games/pix/cards/stand%20or%20bust.jpg" jsaction="" class="sFlh5c FyHeAf iPVvYb" style="max-width: 506px; height: 190px; margin: 0px; width: 506px;" alt="How to play Blackjack" jsname="kn3ccd">
<img src="https://i1.wp.com/oneidacasino.net/wp-content/uploads/2020/03/Blackjack.png?strip=all" jsaction="" class="sFlh5c FyHeAf iPVvYb" style="max-width: 506px; height: 190px; margin: 0px; width: 200px;" alt="What Are Cards Worth In Blackjack - India 2023" jsname="kn3ccd">
</div>



Here is some code that illustrates how we I account for special cards J, Q, K, and A:

```cpp
byte ADCRead(byte ch)
{
   #Calculate values
def Total(turn):
    total = 0 #starting value of the game
    special = ['J','Q','K']
    for card in turn:
        if card in range(1,11): #checks the value to ensure that its none of the special
            total += card #adds value of the card to total
        else if card in special: #J Q or K values
            total += 10
        else: #Ace functionality has problems 
            if total >= 11:
                total += 1
            else:
                total += 11
    return total
}
```
In this snipped of I created a function that takes in J, Q, and K and replace them with the value of 10 by creating and adding them to an array called special. The ace as a little different from the J, Q, and K. A is considered either 1 or 11, so to account for the Ace functionality can be called for both 1 and 11. By using if and else if we cover the J, Q, and K leaving the else to be directly account for the Ace. This was the part of my code that I had the hardest time coding and figuring out the idea of. This coding experience taught me to draw and test my thoughts through trial and errors until I found the solution.
