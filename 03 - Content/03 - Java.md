---
creation date: August 8th 2023
last modified date: August 8th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Languages]] | [[000 - Cybersecurity Materials]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Java]]  

### Basic Hello World

```java
public class HelloWorld{

	public static void main(string []args){
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

```java
public class HelloWorld{

	public static void main(String []args){
		for(int i = 0; i < 5; i++)
		{
			System.ou
		}
	}
}
```














___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 8th 2023 (08:20 pm) 
Last Modified Date: August 8th 2023 (08:20 pm)
