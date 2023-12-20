## Date :
## Ex No:04- Experiment--Half-Subtractor-and-Full-subtractor
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
```python
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: SANJAY M
RegisterNumber:  23013084
```

## Half Subtractor:
```python
module half_sub(a,b,difference,borrow);
input a,b;
output difference,borrow;
wire x;
xor (difference,a,b);
not (x,a);
and (borrow,x,b);
endmodule
```

## Full Subtractor:
```python
module Full_sub(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
wire p;
assign difference=((a^b)^bin);
not (p,a);
assign borrow=((p&b)|(p&bin)|(b&bin));
endmodule
```

## Output:

## Truthtable:
## Half subtractor:
![Screenshot 2023-12-20 085703](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/af0d30f5-5adf-45d2-857c-630b2a68709f)
## Full subtractor:
![Screenshot 2023-12-20 085651](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/6099de9a-053d-446e-a140-367882bc7b3b)




##  RTL realization:
## Half sub:
![Screenshot 2023-12-20 085624](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/ee8b616a-9e93-4fe6-9c58-0af65d46aa84)

## Full sub:
![Screenshot 2023-12-20 085633](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/092cec1d-4774-40c2-ba50-0ea79645af8e)



## Timing diagram :
## Half sub:
![Screenshot 2023-12-20 085712](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/715d8e2e-f2b9-42b6-9f26-fe8f2910bdf9)

## Full sub:
![Screenshot 2023-12-20 085703 - Copy](https://github.com/sanjayofficial2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/148048602/ceda26d5-5c33-4423-84fb-3b1751a929cf)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
