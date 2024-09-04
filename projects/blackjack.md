---
layout: project
type: project
image: img/Screenshot Bjack.png
title: "BlackJack"
date: 2024-08-02
labels:
  - Python
summary: "I developed the BlackJack card game in python"
---
The goal of this project was to test my skills as a programmer by using concepts I have learned in my classes and to put htem into one program. Blackjack required loops, classes, if statements, etc. Creating this program help to refresh concepts and to practice developing code from scratch. Building from scratch helped me to build a process to go through that would help me as a developer to create better code effiecently.

**What is BlackJack?**

BlakcJack is a card game where you as a player play against the dealer to try to out score the dealer. The best hand possible in the game is 21 which "BlackJack" and you win, but go over 21 or have less points than the dealer then you lose. Here are some pictures of some hands in BlackJack to give an example

<div class="text-center p-4">
 <img src="https://www.kjartan.co.uk/games/pix/cards/stand%20or%20bust.jpg" jsaction="" class="sFlh5c FyHeAf iPVvYb" style="max-width: 506px; height: 190px; margin: 0px; width: 506px;" alt="How to play Blackjack" jsname="kn3ccd">
<img src="https://i1.wp.com/oneidacasino.net/wp-content/uploads/2020/03/Blackjack.png?strip=all" jsaction="" class="sFlh5c FyHeAf iPVvYb" style="max-width: 360px; height: 190px; margin: 0px; width: 90px;" alt="What Are Cards Worth In Blackjack - India 2023" jsname="kn3ccd">
</div>


Here is some code that illustrates how we read values from the line sensors:

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
