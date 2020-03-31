method is applied to predict the lane change trajectory of a target car in dense traffic areas.

the generation of a safe and efficient interactive trajectory requires the autonomous driving car to correctly understand human drivers’ behaviors or intentions and then make a prediction of the human-driven cars’ trajectories. 

difficulties of trajectory estimation are: 1) modeling the mutual interactions among surrounding cars; 2) predicting the continuous trajectories based on the interactions; 3) there are not enough data in complex driving scenarios and interactions for traditional deep learning methods. 

lane-changing behavior into Stanford Junior’s global path planner, which is an instance of dynamic programming (DP). In fact, the problem is formulated as optimizing a variant Bellman equation, which implicitly follows the MDP framework and value iteration. Each action is assigned a penalty cost. 

meta induction architecture takes a set of demonstration examples and an additional observation as the inputs, i.e., D = (X1, Y1), ..., (Xn, Yn) and X ˆ, and then it outputs the corresponding estimate Y ˆ . The size of D can be as
small as 1 ∼ 5.

trajectory of each car in the group is recorded from 10 seconds before to 10 seconds after the target car (Veh-s) crossing the lane-marking.
