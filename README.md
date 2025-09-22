# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
LDA 4200H

MOV B, A

LDA 4210H

ADD B

STA 4300H

JC STORE_CARRY

HLT

STORE_CARRY: MVI A, 01H

STA 4301H

HLT

### Output:
<img width="1888" height="1035" alt="ADDITION" src="https://github.com/user-attachments/assets/3948f624-6297-4237-8f99-6eb83cdc8290" />

<img width="1881" height="991" alt="ADDITION (2)" src="https://github.com/user-attachments/assets/8aeb7727-4942-4cdb-874e-d70e5a8e4b46" />

### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
LDA 4200H

MOV B,A

LDA 4201H

ADD B

STA 4300H

JC STORE_CARRY

HLT

STORE_CARRY:MVI A,01H

STA 4301H

HLT
### Output:
<img width="1869" height="985" alt="SUB" src="https://github.com/user-attachments/assets/91100162-2869-467e-a4c7-067a1794d4da" />

<img width="1868" height="963" alt="SUB (2)" src="https://github.com/user-attachments/assets/7d84cb68-472b-48ca-9be8-12565a60b6a6" />

### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
LDA 4200H

MOV C,A

LDA 4201H

MOV B,A

MVI A,00H

LOOP:ADD C

DCR B

JNZ LOOP

STA 4300H

HLT

### Output:
<img width="1883" height="990" alt="MUL" src="https://github.com/user-attachments/assets/270055d6-f2b9-44a0-97a4-2989af06d35f" />

<img width="1878" height="982" alt="MUL (2)" src="https://github.com/user-attachments/assets/3bc4652b-f4c5-4207-b8c3-4a614523d713" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
LDA 4200H

MOV C,A

LDA 4201H

MOV B,A

MVI A,00H

LOOP:ADD C

CMP B

JC END

SUB B

MOV C,A

INR D

JMP LOOP

END: MOV A,D

STA 4300H

MOV A,C

STA 4301H

HLT
### Output:
![WhatsApp Image 2025-08-25 at 10 41 34_fa15bef3](https://github.com/user-attachments/assets/aaf5d0af-6f49-4004-a2e6-1769b895958f)

![WhatsApp Image 2025-08-25 at 10 41 43_b6cc73de](https://github.com/user-attachments/assets/cbd7fd9b-4a9c-404d-ae7f-1f15aa69849a)
## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

