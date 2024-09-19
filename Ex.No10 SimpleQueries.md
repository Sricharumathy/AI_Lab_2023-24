# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE:19/09/2024                                                                         
### REGISTER NUMBER :212222060279 
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.

### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
likes(john, X) :- food(X).
food(apple).
food(chicken).
eats(sue, Y) :- eats(bill, Y).
eats(bill, peanuts).
```
### Output:
![Screenshot 2024-09-19 092513](https://github.com/user-attachments/assets/8f129ec3-8984-423e-ba07-e3909d10a722)

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
have_fun_course(bk301).
likes(steve, X) :- easy(X).
easy(X) :- have_fun_course(X)
```
### Output:
![Screenshot 2024-09-19 092734](https://github.com/user-attachments/assets/4694195c-21bd-4f6f-9f6e-d9d34904e0d5)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
hostile(nano).
american(west).
missile(missile1).
sells(west, missile1, nano).
criminal(X) :- american(X), sells(X, Y, Z), missile(Y), hostile(Z)
```
### Output:
![Screenshot 2024-09-19 092959](https://github.com/user-attachments/assets/d810ee73-fa40-4860-aea0-68871bbd9bf5)

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
