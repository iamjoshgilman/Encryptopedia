---
creation date: August 17th 2023
last modified date: August 17th 2023
aliases: []
tags: #📖
---

Primary Categories: [[ASU-CSE110]] | [[000 - Global Index]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[CSE-110 What is an Algorithm and Flowchart]]  

___
## Algorithms

### Definition
- An algorithm is a list of instructions that, when followed, solves a problem.

### Basic Elements of a Structured Algorithm
1. **Sequence**: Instructions are executed in a specific, sequential order.
2. **Decision**: Based on conditions, different subsets of instructions are executed.
3. **Iteration (Loops)**: A set of instructions is repeated as long as a certain condition is met.

### Composition of Complex Algorithms
- **Stacking**: Sequentially listing algorithmic elements.
![[Pasted image 20230817200042.png]]

- **Nesting**: Embedding one element within another, allowing for increased complexity.
![[Pasted image 20230817200102.png]]

## Pseudocode

### Definition
- Pseudocode is an informal, high-level description of an algorithm intended for human readability.

### Features
1. Lacks the strict syntax and grammar rules of programming languages.
2. Sits between a natural language (e.g., English) and formal programming languages (e.g., Python, Java).
3. Aims for clarity, simplicity, and understandability.
4. Can be translated into any programming language by a proficient programmer.

### Purpose
- Helps in breaking down the algorithm design from its implementation.
- Allows programmers to focus on the algorithm's logic without getting bogged down by the specific syntax of a programming language.

### Example
```java
Repeat Until all cards are sorted in correct order
    Pick two cards at random
    If card on the left is greater than card on the right then
        Swap the positions of these two cards
End
```

## Flowcharts

### Definition
- A flowchart is a graphical representation of an algorithm that uses simple symbols to make a process easier to understand and visualize.

### Advantages
1. Visual representation makes it easier to follow and understand the flow of an algorithm.
2. Explicitly shows the sequence of steps in the algorithm.
3. Useful for algorithm design and analysis due to its visual nature.

### Symbols 
- Different geometric shapes represent different types of instructions or decisions in the algorithm.
![[Pasted image 20230817200220.png]]

Here is a representation of Euclid's algorithm in pseudocode.

```java
Input a
Input b

Repeat Until a is equal to b
    If a is greater than b then
        subtract b from a
    Otherwise
        subtract a from b
Output a
```

![[Pasted image 20230817200248.png]]
### Pseudocode vs. Flowcharts
- **Flowcharts**: Ideal for visualizing, designing, and understanding algorithms.
- **Pseudocode**: Closer to actual code, making it easier to translate into a programming language.

## Conclusion
Both pseudocode and flowcharts are essential tools in computer science and programming. They each offer unique strengths that can be leveraged depending on the stage of algorithm development and the specific needs of the developer. By understanding and using both, a computer scientist can design, communicate, and implement algorithms more effectively.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 17th 2023 (07:04 pm) 
Last Modified Date: August 17th 2023 (07:04 pm)
