
**BY: V Rishon Anand**

**Reg no: 212224240135**

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
**Full Subtractor**

![Screenshot 2025-03-24 194955](https://github.com/user-attachments/assets/d6a8f9ad-489f-42a2-8c11-835f64cce0ac)

**Full Adder**

![Screenshot 2025-03-24 195016](https://github.com/user-attachments/assets/a10c4f05-cd54-4098-92aa-bcdfeee0e42c)

**Procedure**
Step 1: Type the program in Quartus software.
Step 2: Compile and run the program.
Step 3: Generate the RTL schematic and save the logic diagram.
Step 4: Create nodes for inputs and outputs to generate the timing diagram.
Step 5: For different input combinations generate the timing diagram.


**Program:**

**Full Adder**
```
   module full_adder (A, B, Cin, Sum, Carry); 
   input A, B, Cin;
   output Sum, Carry;

   wire AxorB, AB, BCin, ACin;

   xor (AxorB, A, B);           
   xor (Sum, AxorB, Cin);       

   and (AB, A, B);              
   and (BCin, B, Cin);          
   and (ACin, A, Cin);          
   or (Carry, AB, BCin, ACin);  
   endmodule
```
   **Full Subtractor**
```
  
  module full_subtractor (A, B, Bin, Diff, Borrow);
  input A, B, Bin;
  output Diff, Borrow;

  wire AxorB, A_not, A_not_and_B, A_not_and_Bin, B_and_Bin;

  xor (AxorB, A, B);               
  xor (Diff, AxorB, Bin);          

  not (A_not, A);                
  and (A_not_and_B, A_not, B);     
  and (A_not_and_Bin, A_not, Bin); 
  and (B_and_Bin, B, Bin);         
  or (Borrow, A_not_and_B, A_not_and_Bin, B_and_Bin); 
  endmodule
```

**RTL Schematic**

**Full Adder**

![Screenshot 2025-03-24 191756](https://github.com/user-attachments/assets/c4ee73bc-be52-4108-b2de-dbd5d75c95bd)

**Full Subtractor**

![Screenshot 2025-03-24 193617](https://github.com/user-attachments/assets/1f94574b-c59e-41f5-ab0f-cfb0b87e01f9)

**Output Timing Waveform**

**Full Adder**

![Screenshot 2025-03-24 192340](https://github.com/user-attachments/assets/d4865cb5-26a1-400a-a47d-309852ac43d0)

**Full Subtractor**

![Screenshot 2025-03-24 194452](https://github.com/user-attachments/assets/f83614cf-3a2f-4765-b53e-37280b34588f)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



