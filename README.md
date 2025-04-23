# DEVELOPED BY:M.GAJALAKSHMI
# REGISTER NUMBER:212224100016

# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

![image](https://github.com/user-attachments/assets/49604ca9-012f-48a5-aa17-bfa5119bd36b)


**Procedure**
1.Type the program in Quartus software.
 2.Compile and run the program.
 3.Generate the RTL schematic and save the logic diagram.
 4.Create nodes for inputs and outputs to generate the timing diagram.
 5.For different input combinations generate the timing diagram


**Program:**

full adder
```
module fadd(a, b, c, sum, carry);
input a, b, c;
output sum, carry;
wire w1, w2, w3;
assign sum = a ^ b ^ c;
assign w1 = a & b;
assign w2 = b & c;
assign w3 = c & a;
assign carry = w1 | w2 | w3;
endmodule
```
full subtractor
```
module fsub(a, b, bin, diff, borrow);
input a, b, bin;
output diff, borrow;
wire w1, w2, w3, w4;
xor g1(diff, a, b, bin);
not g2(w1, a);
and g3(w2, w1, bin);
and g4(w3, w1, b);
and g5(w4, b, bin);
or g6(borrow, w2, w3, w4);
endmodule
```





**RTL Schematic**



![image](https://github.com/user-attachments/assets/00340450-d530-484f-b114-71f7f07806e0)


![image](https://github.com/user-attachments/assets/e7a2138e-effa-43f2-af16-6c2010725824)



**Output Timing Waveform**


![image](https://github.com/user-attachments/assets/78d2e65e-a002-46b5-b265-00704e4e367f)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



