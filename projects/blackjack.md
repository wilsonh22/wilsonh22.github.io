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

M

For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

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
