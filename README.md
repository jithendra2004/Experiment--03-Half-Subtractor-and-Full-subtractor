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
~~~
1.Use module projname(input,output) to start the Verilog programmming.
2.Assign inputs and outputs using the word input and output respectively.
3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4.Use each output to represnt onre for differnce and the other for borrow.
5.End the verilog program using keyword endmodule.

~~~

Write the detailed procedure here 


## Program:
~~~ /*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: v.A.jithendra
RegisterNumber: 212221230043
*/
~~~

~~~
## HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

## FULL SUBTRACTOR

module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
~~~


## Output:
## Half Subtractor:
### Logic Symbol

![1 1](https://user-images.githubusercontent.com/94226297/167161872-3f1e89fd-3c31-4d8e-8130-d002854557e5.png)


### Truthtable
![1 2](https://user-images.githubusercontent.com/94226297/167161887-f0590beb-3f4e-43ed-8a68-8c072a46fb81.png)


### RTL realization
![Screenshot 2022-05-05 203043](https://user-images.githubusercontent.com/94226297/167161958-c52de9a1-1112-4a5d-a186-82b3b75e693f.png)


### Timing diagram
![halfsubtract  timming  111111111](https://user-images.githubusercontent.com/94226297/167163137-a13566eb-098a-4c1f-a7ed-431aa5eb2380.png)


## Full Subtractor:

### Logic Symbol
![2 1](https://user-images.githubusercontent.com/94226297/167161998-721ba8eb-348f-411e-9586-f3c3469d7a50.png)

### Truthtable
![2 2](https://user-images.githubusercontent.com/94226297/167162027-0c5225fb-1400-4d6a-9f16-18bbf6789916.png)



### RTL realization
![2 3](https://user-images.githubusercontent.com/94226297/167162234-059a0c8f-d56a-4fc0-91bb-a7ec60c6e099.png)


### Timing diagram
![2 4](https://user-images.githubusercontent.com/94226297/167162260-72639663-b15b-4b94-8276-40f1c29b297e.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
