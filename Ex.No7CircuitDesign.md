# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE:  12.9.2024                                                                        
### REGISTER NUMBER : 212222060279
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.
### Program:
```
and(0,0,0).
and(0,1,0).
and(1,1,1).
and(1,0,0).
or(0,0,0).
or(0,1,1).
or(1,0,1).
or(1,1,1).
xor(0,0,0).
xor(0,1,1).
xor(1,0,1).
xor(1,1,0).
not(0,1).
not(1,0).
half_adder(A, B, Sum, Carry) :-
    Sum is (A + B) mod 2,
    Carry is (A + B) // 2.

half_subtractor(A, B, Difference, Borrow) :-
    Difference is (A - B) mod 2,
    Borrow is (A - B) // 2.

full_adder(A, B, CarryIn, Sum, CarryOut) :-
    TempSum is (A + B + CarryIn) mod 2,
    CarryOut is (A + B + CarryIn) // 2,
    Sum is TempSum.

full_subtractor(A, B, BorrowIn, Difference, BorrowOut) :-
    TempDiff is (A - B - BorrowIn) mod 2,
    BorrowOut is (A - B - BorrowIn) // 2,
    Difference is TempDiff.

```
### Output:
![image](https://github.com/user-attachments/assets/80f583e7-cc04-48dc-a9a0-84f5347c9374)
![image](https://github.com/user-attachments/assets/ce906095-1862-417f-bf15-a27d4fe5fb60)
![image](https://github.com/user-attachments/assets/1e13d15d-a83e-45dc-80df-9752ba3b6181)
![image](https://github.com/user-attachments/assets/95164e89-fd2f-43a6-b15c-fbf69ef9af25)


### Result:
Thus the truth table of circuit verified sucessfully.
