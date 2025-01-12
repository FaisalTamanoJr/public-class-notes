---
title: Introduction to Digital Electronics
draft: false
tags: [LOGDSGN]
date: 2025-01-12, 17:32
---

## Sources

1. Logic circuits part 1 (Lecture Slides)
2. Logic circuits part 2 (Lecture Slides)

## Digital Signals

- In contrast to an analog signal, a *digital signal*, theoretically, can only have an output limited to two different values. For example, it can only have a voltage of either 5V or 0V, whereas an example analog signal can have voltage multiple values ranging between 5 and 0.
- Three common ways to refer to the two states of digital signals:
	- high and low
	- true and false
	- logic 1 and logic 0

## Computers

- The computer is a perfect example of the application of digital signals: they are powerful machines with signals consisting of only two states, a high state and a low one.
- As a result of being digital, the computer language is restricted to 2 characters.

## Number System

- The number system is helpful for understanding 2 character languages, like the ones used in computers.
- The *radix* or *base* indicate the number of possible unique characters of a particular number language.
	- The most popular one is the base 10—which has 10 unique characters: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.
- Arithmetic operations require that the numbers possess the same base; otherwise, it is invalid.

> [!NOTE] Number System Names Based on their Radix
>
> | Name                  | Base/Radix | Symbols             |
> | --------------------- | ---------- | ------------------- |
> | Binary/Dyadic         | 2          | 0,1                 |
> | Tertiary/Ternary      | 3          | 0,1,2               |
> | Quarternary/Quatenary | 4          | 0,1,2,3             |
> | Quinary/Quintary      | 5          | 0,1,2,3,4           |
> | Senary                | 6          | 0,1,2,3,4,5         |
> | Septary/Septenary     | 7          | 0,1,2,3,4,5,6       |
> | Octal/Octenary        | 8          | 0,1,2,3,4,5,6,7     |
> | Nonary                | 9          | 0,1,2,3,4,5,6,7,8   |
> | Decimal               | 10         | 0,1,2,3,4,5,6,7,8,9 |
> | Undenary              | 11         | 0 to 9, A           |
> | Duodecimal/Duodenary  | 12         | 0 to 9, A to B      |
> | Tredenary             | 13         | 0 to 9, A to C      |
> | Quartuodenary         | 14         | 0 to 9, A to D      |
> | Quindenary            | 15         | 0 to 9, A to E      |
> | Hexadecimal           | 16         | 0 to 9, A to F      |
> | Vicenary/Vigesimal    | 20         |                     |
> | Sexagesimal           | 60         |                     |

### Binary

- In binary, 4 *bits* is equivalent to 1 *nibble*.
- On the other hand, 8 *bits* is equivalent to 1 *byte*

### Converting to Base 10

To translate a base r number to base 10, each digit should be multiplied by the corresponding power of r. Afterwards, get the sum of the resulting products.

### Converting from Base 10 to Base R

1. Divide the number into two parts: the integer component and the fractional component.
2. Convert the integer component into base r
	1. Divide it by r.
	2. Record the quotient and the remainder.
	3. Divide the last recorded quotient by r.
	4. Repeat Step 2 and 3 until you obtain a quotient of 0.
	5. The converted integer component consists of the recorded remainder values; the order should be from the latest to the oldest recorded value.
3. Convert the fractional component into base r
	1. Multiply it by r.
	2. Separately record the integer of the product and the fraction of the product.
	3. Multiply the product’s last recorded fraction by r.
	4. Repeat Step 2 and 3 until your product’s last recorded fraction is 0.
	5. The converted fractional component consists of the recorded product’s integer values; the order should be from the oldest to the latest recorded value.

### Converting from Base R1 to Base R2

1. Convert base R1 number to base 10
2. Convert the resulting base 10 number to base R2

> [!TIP] TIP: Converting from Octal to Binary
> Each octal digit is equal to 3 binary bits.
>
> In this regard, converting from **binary bits to octal** will begin with grouping the binary bits into 3 digits (starting from the decimal point). Leading 0s may be added to the integer component, while trailing 0s may be added to the fractional component. Lastly, convert each group in a similar way to converting from a binary number to decimal.
>
> Converting from **binary to hexadecimal** is similar to converting a binary number into octal, except that you group the binary bits into 4 digits, and that values from 10-15 are represented as A to F.
