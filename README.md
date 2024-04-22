# Standard Programs Implemented in Machine CODE

## Overview
This repository contains implementations of various standard programs using machine language code. Each program is designed to perform a specific computation or operation, ranging from basic arithmetic operations to more complex algorithms.



1. **16-Bit No Addition**: Program to perform addition of two 16-bit numbers.
```
 LHLD C050H
XCHG C050H
LHLD C052H
DAD D
MVI C,00H
JNC LOOP
LOOP:  SHLD C054H
MOV A,C
STA C056H
 ```
2. **1's Complement of 8-Bit Number**: Program to find the 1's complement of an 8-bit binary number.
```
LDA C050H
CMA
STA C051H
HLT
3. **Multiplication of 8-Bit Numbers**: Program to multiply two 8-bit numbers.
LXI H,C050H
MOV B,M
MVI A,00H
MVI D,00H
INX H
MOV C,M
LOOP2: ADD B
JNC LOOP
INR D
LOOP: DCR C
JNZ LOOP2
STA  C052H
MOV A,D
STA C053H
```
4. **Division of 8-Bit Number**: Program to perform division of an 8-bit number.
```
LXI H,C050H
MOV B,M
INX H
MOV C,M
MVI D,00H
MOV A,B
LOOP: SUB C
INR D
CMP A,C
JNC LOOP
STA C052H
HLT
```
5. **De-Morgan's Theorem**: Program to implement De-Morgan's theorem.
```
LXI H,C050
MOV B,M
INX H
MOV C,M
MOV A,B
ORA C
CMA 
STA C052H
MOV A,B
CMA
MOV D,A
MOV C,A
CMA 
ANA D
STA C053H
HLT
```
6. **Total Number of Odd and Even Numbers in Lookup Table**: Program to count the total number of odd and even numbers in a lookup table.
```
LXI H,C050H
MOV C,M
MVI B,00H
MVI D,00H
LOOP: INX H
MOV A,M
RAR
JC LOOP
INR B
JMP LOOP3
LOOP: INR D
LOOP3: DCR C
JNZ LOOP2

```
7. **Binary to Grey Code Conversion**: Program to convert binary numbers to Grey code.
```
LDA C050H
MOV B,A
RAR 
XRA B
STA C051H
HLT
```
8. **Grey Code to Binary Conversion**: Program to convert Grey code to binary numbers.
```
LXI H,C050H
MOV C,M
LXI D,C100H
INX H
LOOP: MOV A,M
MOV B,A
RAR
XRA B
STA D
INR D
JNZ LOOP
HLT
```
9. **Fibonacci Series using 8085 Code**: Program to generate Fibonacci series using 8085 assembly language.
```
LDA D000H
MOV D,A
MVI B,00H
MVI C,00H
MVI A,00H
LOOP: MOV M,A
ADD C
MOV B,C
MOV C,A
MOV A,B
INX H
OCR D
JNZ LOOP
HLT
```
10. **BCD to Hex Conversion**: Program to convert Binary Coded Decimal (BCD) numbers to hexadecimal.
```
LDA D050H
MOV B,A
ANI 0FH
MOV C,A
MOV A,B
ANI F0H
RRC
RRC
RRC
RRC
MOV D,A
MVI E,0AH
XRA A
LOOP: ADD D
DCR E
JNZ LOOP
ADD C
STA C050H
HLT
```
11. **Square Root of Number**: Program to find the square root of a number.
```
LDA C050H
MVI D,01H
MVI E,01H
LOOP: SUB D
JNZ LOOP
INR D
INR D
INR E
JMP LOOP1
LOOP1: MOV A,E
STA C051H
HLT
```
## Usage
Each program is accompanied by its corresponding machine language code. Users can download or clone the repository to access the source code for each program. Detailed instructions on how to assemble, run, and test each program may be provided within the respective program files or in the repository's README.

