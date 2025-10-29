# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE:12/09/25                                                                            
### REGISTER NUMBER :212222065003 
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
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
likes(john,X):-
	food(X).
eats(bill,X):-
	eats(sue,X).
eats(Y,X):-
	food(X).
eats(bill,peanuts).
food(apple).
food(chicken).
food(peanuts).

### Output:
<img width="1177" height="871" alt="377592626-910bdd4e-85c1-4c35-8df2-7a36cbd8c270" src="https://github.com/user-attachments/assets/e4d89d2a-1c5d-4a8f-a565-4ac31e5daf4c" />

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
likes(steve,X):-
     easycourse(X).
hard(sciencecourse).
easycourse(X):-
          course(X,dept(havefun)).
course(bk301,dept(havefun)).

### Output:
<img width="1190" height="367" alt="377592897-0504728c-efc0-4353-aa13-8f734a15e884" src="https://github.com/user-attachments/assets/03dd55ca-dd73-4426-a75e-4a981a6ddb25" />

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
criminal(X):-
	american(X),
	weapon(Y),
	hostile(Z),
	sells(X,Y,Z).
weapon(Y):-
    missile(Y).
hostile(Z):-
    enemy(Z,X).

sells(west,Y,nano):-
	missile(Y),
	owns(nano,Y).

missile(m).
owns(nano,m).
enemy(nano,america).
american(west).
### Output:
<img width="1183" height="411" alt="377593133-1d40a9b1-651a-4f6b-9b60-20d7b648f04f" src="https://github.com/user-attachments/assets/c6148f10-b855-4174-a509-d6bc997fa4d3" />

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
