---
creation date: August 15th 2023
last modified date: August 15th 2023
aliases: []
tags: #㊙️
---

[[02 - Foundations]]
Search Tag: #㊙️  

# [[03 - Logic and Truth Tables]]  

## Definitions:

1. **Logic**: The branch of philosophy dealing with the study of reasoning, especially the structure of propositions and the nature of truth and inference.
2. **Truth Table**: A table that shows all possible truth values for a given logical expression.
### The Language of Logic

There are still a few important terms that you don't know so in this section we will go over them.
- #### Tautology
	- A tautology is an assertion or formula which is always true no matter the inputs. If you craft a logical statement that no matter the inputs is always true then this is a tautology.
	- Another way of saying this would be if you have a logical statement where the truth table for it always produces only true results then this is a tautology.
- #### Contradiction
	- A contradiction is the opposite of a tautology. This is where all the results of a logical statement are always false no matter the inputs. If your truth table only produces false results then you have crafted a contradiction.
- #### Contingency
	- A contingency is essentially anything that isn't a tautology or contradiction. In other words a logical statement where the outcomes could be true or false **contingent** on the inputs.

## Basic Logical Operators:

- A Boolean statement - one which can only be true or false is known as a **proposition**. For example: Tomorrow is Friday. This can either be true or false and is therefore a **proposition**.

### 1. Logical AND (⋅ or ∧)

- **Symbol**: ∧ or ⋅
- **Definition**: Returns true only if both operands are true.
- An AND is considered to be a **connective**. A connective is used to connect two or more **propositions**. The AND **connective** specifically is called a **conjunction**.
- **Truth Table**:

| A | B | A ∧ B |
|---|---|------|
| T | T |   T  |
| T | F |   F  |
| F | T |   F  |
| F | F |   F  |

```java
string1 = "demo"
string2 = "demo"
int1 = 42
int2 = 33

if (string1 == string2 && int1 == int2):
  dostuff()
```

This is a logical AND. `string1 == string2` is a comparison, and the result will be true if they are both the same, and false if they are not. In this case, it is true.

`int1 == int2` is another comparison and the result will be true if they are both the same and false if they are not. In this case, it is false.

The result we have is:

`True AND False = False`

Therefore, our `dostuff()` function is never called, because the condition has not been met.

---
## 2. Logical OR (∨)

- **Symbol**: ∨
- **Definition**: Returns true if at least one operand is true.
- As you already know an OR is a type of **connective** and the OR **connective** itself is known as a **disjunction**.
- **Truth Table**:

| A | B | A ∨ B |
|---|---|------|
| T | T |   T  |
| T | F |   T  |
| F | T |   T  |
| F | F |   F  |

```java
string1 = "demo"
string2 = "demo"

int1 = 42
int2 = 33

if (string1 == string2 || int1 == int2):
  dostuff()
```

`string1` does equal `string2`, so the result is true. `int1` does not equal `int2`, so the result is false, so that works out as:

`True OR False = True`

In this case, our `dostuff()` function will run, because the condition has been met.

---
## 3. Logical NOT (¬ or !)

- **Symbol**: ¬ or !
- **Definition**: Returns the opposite of the operand.
- As you already know a NOT is a type of **connective** and the NOT **connective** itself is known as a **negation**.
- **Truth Table**:

| A | ¬A  |
|---|----|
| T |  F |
| F |  T |

```java
string1 = "demo"
string2 = "demo"

if !(string1 == string2):
  dostuff()
```

Does `string1` equal `string2`? Yes, so the result is true. The NOT causes that to become false, so `dostuff()` will not run because the condition hasn't been met.

You could also see not written like so:

`if (string1 != string2):`

In English, this is: "if string1 does NOT equal string2".

---
## 4. Logical NAND (⊼)

- **Symbol**: ⊼
- **Definition**: Returns true unless both operands are true.
- As you already know a NAND is a type of **connective** and the NAND **connective** itself is known as an **alternative denial**.
- **Truth Table**:

| A | B | A ⊼ B |
|---|---|------|
| T | T |   F  |
| T | F |   T  |
| F | T |   T  |
| F | F |   T  |

```java
string1 = "demo"
string2 = "demo"

int1 = 42
int2 = 33

if !(string1 == string2 && int1 == int2):
  dostuff()
```

Does `string1` equal `string2`? Yes, so it's true. Does `int1` equal `int2`? No, so it's false. So far we have:

`!(True AND False)`

True AND false is false, so we now have:

`!(False) = True`

So our `dostuff()` function is going to run because the condition has been met.

---
## 5. Logical NOR (⊽)

- **Symbol**: ⊽
- **Definition**: Returns true only if both operands are false.
- As you already know a NOR is a type of **connective** and the NOR **connective** itself is known as a **joint denial**.
- **Truth Table**:

| A | B | A ⊽ B |
|---|---|------|
| T | T |   F  |
| T | F |   F  |
| F | T |   F  |
| F | F |   T  |

```java
string1 = "demo"
string2 = "demo"

int1 = 42
int2 = 33

if !(string1 == string2 || int1 == int2):
  dostuff()
```

Does `string1` equal `string2`? Yes, so it is true. Does `int1` equal `int2`? No, so it is false. We now have:

`!(True OR False)`

True OR false is true (remember, with OR just one of the inputs being true makes it true). We now have:

`!(True) = False`

So our `dostuff()` function is not going to run because the condition has not been met.

---
### 6. Logical XOR (⊕)

- **Symbol**: ⊕
- The XOR gate stands for Exclusive-OR
- **Definition**: Returns true if exactly one operand is true.
- As you already know a XOR is a type of **connective** and the XOR **connective** itself is known as an **exclusive disjunction**.
- **Truth Table**:

|_A_|_B_|_A XOR B_|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

Notice when A and B are both true, then the output is false? This is the difference between XOR and OR. Remember, XOR is exclusive, it doesn't like both inputs being true. Unlike the others, you won't see this one a lot in conditionals, but you will see it a LOT in cryptography.

XOR is really cool, in that:

A XOR B = C  
A XOR C = B  
B XOR C = A

Take a look:

|1|1|0|0|
|---|---|---|---|
|0|1|0|1|
|1|0|0|1|

So 1100 XOR 0101 = 1001

If you treat 1100 as your data, and 0101 as your encryption key, then 1001 is your encrypted data.

If you have your encrypted data, you can XOR it with your key to get your decrypted data back:

|1|0|0|1|
|---|---|---|---|
|0|1|0|1|
|1|1|0|0|

1001 XOR 0101 = 1100

1100 was our initial piece of data. This is a very basic form of encryption on its own. It isn't a very strong form of encryption, but it is used in a lot of cryptographic algorithms as part of the process, including AES which is the current industry standard.


---

## Key Points to Remember:

- **Logical AND** and **Logical OR** are the most basic and frequently used logic operators.
- **Logical NOT** simply inverts the truth value.
- **Logical NAND** and **Logical NOR** are negations of AND and OR, respectively.
- **Logical XOR** is often referred to as the "exclusive or" because it only returns true when its operands are distinct.

## Practice:

1. Create complex logical expressions using the basic operators and verify their truth tables.
2. Identify real-world scenarios where these logical operators might apply (e.g., access control systems).


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 15th 2023 (08:14 pm) 
Last Modified Date: August 15th 2023 (08:14 pm)
