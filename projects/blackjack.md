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
  <a data-ved="2ahUKEwi5juL31KiIAxXYh-4BHTU1CEIQjRx6BAgAEBg" rel="noopener" target="_blank" href="https://www.google.com/url?sa=i&amp;url=https%3A%2F%2Fsimple.wikibooks.org%2Fwiki%2FCard_Games%2FBlackjack&amp;psig=AOvVaw1IySqHBKwH64XANKQUDcrn&amp;ust=1725517821634000&amp;source=images&amp;cd=vfe&amp;opi=89978449&amp;ved=2ahUKEwi5juL31KiIAxXYh-4BHTU1CEIQjRx6BAgAEBg" jsaction="focus:trigger.HTIQtd;mousedown:trigger.HTIQtd;touchstart:trigger.HTIQtd;;" class="YsLeY" role="link" tabindex="0" aria-label="Visit Wikibooks" rlhc="1"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/79/Blackjack.jpg/220px-Blackjack.jpg" jsaction="" class="sFlh5c FyHeAf iPVvYb" style="max-width: 220px; height: 269px; margin: 0px; width: 220px;" alt="Card Games/Blackjack - Wikibooks" jsname="kn3ccd"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThIjuXqmoVRFIEH8g3dls1Fk2qbqfT8JFIvfWuLVjMBuPr3HwOUZZXFt7a8p-pplirj0g&amp;usqp=CAU" class="sFlh5c FyHeAf" alt="Card Games/Blackjack - Wikibooks" jsname="JuXqh" style="max-width: 220px; position: absolute; visibility: hidden;" data-atf="true" data-iml="889.1000000238419"><span class="UWuvyf">220 × 269</span></a>
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
