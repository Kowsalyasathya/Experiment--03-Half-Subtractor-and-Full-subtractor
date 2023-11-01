# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware :
PCs, Cyclone II , USB flasher
## Software 
Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

STEP 1: Use module project name(input,output) to start the Verilog programmming.

STEP 2: Assign inputs and outputs using the word input and output respectively.

STEP 3: Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

STEP 4: Use each output to represnt onre for differnce and the other for borrow.

STEP 5: End the verilog program using keyword endmodule.

## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Kowsalya M
RegisterNumber:  212222230069
*/
## Half subtractor:
```
module exp4(a,b,diff,borr);
input a,b;
output diff,borr;
assign diff = (a^b);
assign borr = ((~a)&b);
endmodule
```
## Full subtractor:
```
module fullsubtractor(a,b,bin,diff,borr);
input a,b,bin;
output diff,borr;
assign diff=(a^b^bin);
assign borr=(~a&(b)|(b&bin)|((~a)&bin));
endmodule
```
## Output:
## Truthtable
### Half subtractor:
![266759907-4019897b-f35b-432a-91c2-fcc00129cc33](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/fd774c59-7eb9-4dc3-986d-9b3591c7e86a)
### Full subtractor:
![266759910-e4dfc8b4-d27d-4ac3-807c-745b46d51346](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/78ea19c1-0630-45bc-bb36-7a653daa07f9)
ion
##  RTL realizat
### Half subtractor:
![266759547-e044ab92-b89c-4899-8603-e54c264da946](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/f0f92d5d-1009-49b4-86ff-1f3bc32c9052)
ram 
### Full subtractor:
![266759554-6bc51f4e-77cc-4c1e-9416-0fb1f098cca1](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/7f584410-bb7d-4cc1-84c6-36ed2049daf3)
## Timing diag:
 ### Half subtractor:

![266759564-3967461a-b0b7-4ae4-8435-e8f63afb672b](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/7018a70f-5853-4d50-90b3-2e83b6848120)
### Full subtractor:
![266759574-b0a4a510-5d54-43cc-94ea-fe8748967a79](https://github.com/Kowsalyasathya/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118671457/bbc7f5cd-e885-476a-b502-6f718b0ad7e8)
## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
