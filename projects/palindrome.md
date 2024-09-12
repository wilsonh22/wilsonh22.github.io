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


Here is the full source code for the Palindrome checker:

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
