# **Sum of 5 Numbers Using 8086 Assembly Language**

## **AIM**

To write and execute an Assembly Language Program in 8086 to calculate the **sum of 5 numbers stored sequentially in memory** and **store the result in another memory location**.

---

## **APPARATUS REQUIRED**

* Personal Computer with MASM (Microsoft Macro Assembler) or EMU8086 Software

---

## **ALGORITHM**

1. Start the program.  
2. Initialize the **data segment** register (DS) to point to the code segment.  
3. Load the starting memory address of the 5 numbers into **SI** register.  
4. Initialize **CX = 05H** to use it as a counter for 5 numbers.  
5. Clear **AL** register to store the running sum.  
6. Add each byte (number) to **AL** using a loop.  
7. Increment **SI** to point to the next memory location.  
8. After all 5 numbers are added, store the final sum in the next memory location.  
9. Stop the program.

---

## **FLOWCHART**

```plaintext
        ┌────────────────────┐
        │     Start          │
        └───────┬────────────┘
                │
                ▼
        ┌────────────────────┐
        │ Initialize SI=2000H│
        │ CX=05H, AL=00H     │
        └───────┬────────────┘
                │
                ▼
        ┌────────────────────┐
        │ Add [SI] to AL     │
        │ Increment SI       │
        │ Decrement CX       │
        └───────┬────────────┘
                │
       ┌────────▼────────┐
       │ CX = 0 ?        │
       └──────┬──────────┘
              │No
              ▼
        ┌──────────────┐
        │ Repeat Loop  │
        └──────┬───────┘
              │Yes
              ▼
        ┌────────────────────┐
        │ Store AL → [SI]    │
        │ End Program        │
        └────────────────────┘
```
#### Program
```
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H

MOV SI,2000H
MOV CX,05H
MOV AL,00H
MOV AH,00H

L1:
ADD AL,[SI]
INC SI
LOOP L1

MOV [SI],AL
MOV AH,4CH
INT 21H

CODE ENDS
END
```
#### MEMORY LOCATION

| MEMORY LOCATION (INPUT) | VALUE (HEX) | DESCRIPTION      |
| ----------------------- | ----------- | ---------------- |
| 2000H                   | 01H         | Number 1         |
| 2001H                   | 02H         | Number 2         |
| 2002H                   | 03H         | Number 3         |
| 2003H                   | 04H         | Number 4         |
| 2004H                   | 05H         | Number 5         |
| **2005H**               | **0FH**     | **Sum (Result)** |

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="632" height="427" alt="image" src="https://github.com/user-attachments/assets/85f13739-9ce1-4098-8cd1-bff2a127fc8c" />

<img width="637" height="422" alt="image" src="https://github.com/user-attachments/assets/0732e2c0-615c-4451-be1c-7e822fddf4b3" />

## RESULT
Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
