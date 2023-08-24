---
creation date: August 8th 2023
last modified date: August 8th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Languages]] | [[000 - Global Index]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Java]]  

### Basic Hello World

```java
public class HelloWorld{

	public static void main(String []args){
		//this is a comment
		System.out.println("Hello World");
	}
}
```

### Creating a variable: Type name = value;

- int | Any whole number, including negative
- double | Anything with decimal, even 2.0
- String | Can be anything, think words and sentences
- char | Can be a single letter or number
- Boolean | Typical true or false

### Data Types

#### Primitive Data Types
- Int
- Long
- Short
- Float
- Double
- Boolean
- Char

#### Non-Primitive Data Types (Objects)

- String
- Array

### If Statements

```java
public class HelloWorld{

	public static void main(String []args){
		//this is a comment
		int x = 3;
		if(x == 3)
		{
			system.out.println("x is 3");
		}
		else if (x > 3)
		{
			system.out.println("x is greater than 3");
		}
		else
		{
			System.out.println("Hello World");
		}
	}
}
```


### Switch Statements

- "More efficient" way of doing an `if statement` when there is many if and else statements needed
- `break` is used as the "fall through" or as an "if"
- Default is not required

```java
import java.util.Scanner;
public class HelloWorld{

	public static void main(String []args){
		Scanner scanny = new Scanner(system.in);
		String input;
		int number;
		System.out.println("Please enter a letter a, b, or c\n");
		input = scanny.next();
		
		switch(input)
		{
		case "a":
			number = 0;
			break;
		case "b":
			number = 1;
			break;
		case "c";
			number = 3;
			break;
		default:
			number = -1;
		}	
	}
}
```

### Loops

#### For loop

- for ( `initialization` ; `condition` ; `iteration` ){ }
- Declare the initialize starting value, give stopping condition, change the value

```java
public class HelloWorld{

	public static void main(String []args){
		for(int i = 0; i < 5; i++)
		{
			System.out.println("Hello World " + i +"\n");
		}
	}
}
```

- Will iterate `Hello World 0` through `Hello World 4` (Because it starts counting at 0, why it wont hit 5)

#### While Loop

- while ( `condition`) { }

```java
public class HelloWorld{

	public static void main(String []args){
		int i = o;
		while(i < 5){
			System.out println("Hello World " + i + "\n");
			i++; //Don't forget to increment value
		}
	}
}
```

#### Do-While Loop

- do { `Code to execute` } while ( `Condition` )

```java
public class HelloWorld{

	public static void main(String []args){
		int i = 0
		do{
			System.out.println("Hello World " + i + "\n");
			i++;
		}while(i < 5);
	}
}
```

- Since the condition is at the bottom, the loop will always run at least once.

#### How to pick the "right" loop

- <u>For Loops</u> : When you know the exact number of times you need to run the loop
	- <u>Example</u> : Wanting to print somethin exactly 7 times
- <u>While Loops</u> : When you don't know the the exact number of times but know the stopping condition
	- <u>Example</u> : Print something while user input is **Yes**, stop once it is **No**.
- <u>Do While Loops</u> : When you for sure want to run through the code at least once before checking the condition
	- <u>Example</u> : Main Menus

### User Input

#### Scanner

- Most commonly used method for input

1. Import Scanner Library
2. Create a Scanner object
	1. next( ) or nextLine( ) | strings
	2. nextInt( ) | ints
	3. nextDouble( ) | doubles
3. Close the Scanner object

- Scanner interrupts the code - improper input can cause program crash

```java
import java.util.Scanner; //1
public class HelloWorld{

	public static void main(String []args){

		Scanner scanny = new Scanner(System.in); //2

		System.out.println("Please enter an integer: ");
		int num = scanny.nextInt(); //3
		System.out.println("You entered the integer: " + num + "\n");

		System.out.println("please enter a decimal: ");
		double dubl = scanny.nextDouble(); //3
		System.out.println("You entered the deimal: " + dubl + "\n");

		System.out.println("Please enter a string: ");
		String str = scanny.next(); //3
		System.out.println("You entered the string: " + str + "\n");

		scanny.close(); //4
	}
}
```

### Array

- Object that contains a fixed number of values of a single type
 


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 8th 2023 (08:20 pm) 
Last Modified Date: August 8th 2023 (08:20 pm)
