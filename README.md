# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
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



Write the detailed procedure here 


## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: P.SYAM TEJ
RegisterNumber:  212221240056
```
### HALF SUBTRACTOR
```
module sam(A,B,Difference,Borrow);
input A,B;
output Difference, Borrow;
wire x;
xor (Difference,A,B);
not (x,A);
and (Borrow,x,B);
endmodule
```
### FULL SUBTRACTOR
```
module sam2(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```
## Output:
### HALF SUBTRACTOR
## Truthtable

<img width="1228" alt="Screenshot 2022-09-24 at 10 01 47 PM" src="https://user-images.githubusercontent.com/93427224/192109064-b9086628-86d9-4633-89ac-59e77a306afd.png">


##  RTL realization

![2 1](https://user-images.githubusercontent.com/93427224/192097197-06f53fce-6c18-4e33-94aa-18f105c7ab40.png)

## Timing diagram 

![1](https://user-images.githubusercontent.com/93427224/192097206-61ed6139-74c1-476d-8572-48e30a38df34.png)

### FULL SUBTRACTOR
## Truthtable

<img width="493" alt="halftruth" src="https://user-images.githubusercontent.com/93427224/192108990-025b9d15-1cb8-41c5-bb2b-1863f3f69e20.png">

##  RTL realization

![3](https://user-images.githubusercontent.com/93427224/192098276-9a6f4afb-5681-4247-a39b-144a9adb2545.png)


## Timing diagram 

![3 1](https://user-images.githubusercontent.com/93427224/192098314-1ac8da55-b444-4a19-b434-174c9ae1998f.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
