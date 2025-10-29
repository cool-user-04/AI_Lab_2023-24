# Ex.No: 11  Planning –  Block World Problem 
### DATE: 10/09/2025                                                                           
### REGISTER NUMBER : 212222065003
### AIM: 
To find the sequence of plan for Block word problem using PDDL  
###  Algorithm:
Step 1 :  Start the program <br>
Step 2 : Create a domain for Block world Problem <br>
Step 3 :  Create a domain by specifying predicates clear, on table, on, arm-empty, holding. <br>
Step 4 : Specify the actions pickup, putdown, stack and un-stack in Block world problem <br>
Step 5 :  In pickup action, Robot arm pick the block on table. Precondition is Block is on table and no other block on specified block and arm-hand empty.<br>
Step 6:  In putdown action, Robot arm place the block on table. Precondition is robot-arm holding the block.<br>
Step 7 : In un-stack action, Robot arm pick the block on some block. Precondition is Block is on another block and no other block on specified block and arm-hand empty.<br>
Step 8 : In stack action, Robot arm place the block on under block. Precondition is Block holded by robot arm and no other block on under block.<br>
Step 9 : Define a problem for block world problem.<br> 
Step 10 : Obtain the plan for given problem.<br> 
     
### Program:
 (define (domain blocksworld)
 (:requirements :strips :equality)
 (:predicates (clear ?x)
 (on-table ?x)
 (arm-empty)
 (holding ?x)
 (on ?x ?y))
 (:action pickup
 :parameters (?ob)
 :precondition (and (clear ?ob) (on-table ?ob) (arm-empty))
 :effect (and (holding ?ob) (not (clear ?ob)) (not (on-table ?ob))
 (not (arm-empty))))
 (:action putdown
 :parameters (?ob)
 :precondition (and (holding ?ob))
 :effect (and (clear ?ob) (arm-empty) (on-table ?ob)
 (not (holding ?ob))))
 (:action stack
 :parameters (?ob ?underob)
 :precondition (and (clear ?underob) (holding ?ob))
 :effect (and (arm-empty) (clear ?ob) (on ?ob ?underob)
 (not (clear ?underob)) (not (holding ?ob))))
 (:action unstack
 :parameters (?ob ?underob)
 :precondition (and (on ?ob ?underob) (clear ?ob) (arm-empty))
 :effect (and (holding ?ob) (clear ?underob)
 (not (on ?ob ?underob)) (not (clear ?ob)) (not (arm-empty)))))








### Input 
Problem 1:
 (define (problem pb1)
 (:domain blocksworld)
 (:objects a b)
 (:init (on-table a) (on-table b) (clear a) (clear b) (arm-empty))
 (:goal (and (on a b))))
 Problem 2:
 (define(problem pb3)
 (:domain blocksworld)
 (:objects a b c)
 (:init (on-table a) (on-table b) (on-table c)
 (clear a) (clear b) (clear c) (arm-empty))
 (:goal (and (on a b) (on b c))))

### Output/Plan:
PLAN-1
<img width="527" height="675" alt="494224859-6369665d-6815-46f5-90ca-6669ca7706ab" src="https://github.com/user-attachments/assets/a2fe8f3e-3f34-4489-8cb2-2647e15af9b6" />

PLAN-2
<img width="490" height="646" alt="494224952-a05990c7-beed-42f1-8435-f60c5488f321" src="https://github.com/user-attachments/assets/c221d7dc-5142-4065-a54e-cc75094342a6" />

### Result:
Thus the plan was found for the initial and goal state of block world problem.
