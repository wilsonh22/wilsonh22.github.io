---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
title: "Palindrome"
date: 2023
published: true
labels:
  - Java
summary: "My class assignment was to create a function that would check if a word is a palindrome."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

Micromouse is an event where small robot “mice” solve a 16 x 16 maze.  Events are held worldwide.  The maze is made up of a 16 by 16 gird of cells, each 180 mm square with walls 50 mm high.  The mice are completely autonomous robots that must find their way from a predetermined starting position to the central area of the maze unaided.  The mouse will need to keep track of where it is, discover walls as it explores, map out the maze and detect when it has reached the center.  having reached the center, the mouse will typically perform additional searches of the maze until it has found the most optimal route from the start to the center.  Once the most optimal route has been determined, the mouse will run that route in the shortest possible time.

For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

Here is some code that illustrates how we read values from the line sensors:

```cpp
public class Palindrome {

	// Method to check whether a String is a palindrome
	private static boolean isPalindrome(StackInterface<Character> stack, String input) {

		// Loop through each character of 'input, and if Character.isLetter(), push onto stack
		for(int i = 0; i < input.length(); i++) {
			Character c = input.charAt(i);  // <--- Get the value of 'input' at index 'i'
			if(Character.isLetter(c))
				stack.push(c);
		}


		// Loop through each character of 'input' again
		// If Character.isLetter(), pop() from the stack, compare characters after converting
		// each one with Character.toUpperCase()
		// If they DO NOT match, return false
		for(int i = 0; i < input.length(); i++) {
			Character c = input.charAt(i);
			if(Character.isLetter(c)) {
				Character d = stack.pop();
				if(Character.toUpperCase(c) != Character.toUpperCase(d))
					return false;
			}
		}

		// If succesfully looped through all characters and they all match, return true
		return true;
	}

	public static void main(String[] args) {

		// Randomly choose what type of stack to use for testing

		// [STEP 1]: Declare a StackInterface object
		StackInterface<Character> stack = null;

		// [STEP 2]: Generate a random integer between 0-2 inclusive
		int stackType = (int) (Math.random()*3); // <----- Initialize this with a random integer 0-2 inclusive

		// [STEP 3]: Depending on value of random integer, initialize 'stack' to appropriate
		// stack type (0 = ArrayStack, 1 = LinkedStack, 2 = JavaStandardLibraryStack)
		switch(stackType) {
		case(0): stack = new ArrayStack<>(); System.out.println("Created ArrayStack!"); break;
		case(1): stack = new LinkedStack<>(); System.out.println("Created LinkedStack!"); break;
		case(2): stack = new JavaStandardLibraryStack<>(); System.out.println("Created JavaStandardLibraryStack!"); break;
		}

		// Loop to test all command-line arguments
		for(String argument : args) {
			switch(stackType) {
			case(0): stack = new ArrayStack<>(); break;
			case(1): stack = new LinkedStack<>(); break;
			case(2): stack = new JavaStandardLibraryStack<>(); break;
			}

			// Test all 'argument' values and print result
			try {
				System.out.println("Testing: " + argument);
				System.out.println("Result: " + isPalindrome(stack, argument));
			} catch(FullStackException e) {
				System.out.println("FullStackException encountered. 'stack' should be an ArrayStack.");
			}
			System.out.println();
		}



		// If no command-line arguments are given, use default test
		if(args.length == 0) {

			// Use default test arguments
			String[] inputs = {"radar", "racecar", "Was it a car or a cat I saw?", 
					"radars", "cat", "palindrome"};

			// Test all elements of inputs with isPalindrome()
			for(String input : inputs) {
				switch(stackType) {
				case(0): stack = new ArrayStack<>(); break;
				case(1): stack = new LinkedStack<>(); break;
				case(2): stack = new JavaStandardLibraryStack<>(); break;
				}

				try {
					System.out.println("Testing: " + input);
					System.out.println("Result: " + isPalindrome(stack, input));
				} catch(FullStackException e) {
					System.out.println("FullStackException encountered. 'stack' should be an ArrayStack.");
				}
				System.out.println();
			}
		}

	}

}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
