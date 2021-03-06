Analyzing the surrounding vehicles’ mutual effects from their trajectories. 2) Estimating the proper lane change start point and end point according to the analysis of surrounding vehicles. We propose a learning-based approach to understand surrounding traffic and make decisions for a safe lane change

Takes past trajectories of all related surrounding cars as input to capture mutual interactions and output continuous values to represent behaviors
 
the proposed approach is able to generate feasible and human-like lane-change behavior (represented by start and end points) in multi-car environments.

complex scenarios, such as intersections, ramp-merging and lane changes, which involve negotiations, intention understanding and social behaviors among traffic participants.

understanding intentions by a collection of related traffic participants’ past trajectories; and generating a proper start point and an end point for lane changing.

We extracted 543 lane changing scenarios from the US-101 and I-80 data. At most five surrounding cars and six trajectories are considered: five from surrounding cars and one from the host car itself

450 groups of trajectories are randomly selected as training sets, and the remaining 93 groups are used for testing. To concentrate on the recent past, training trajectories are pruned and only retain the last 30 steps (3 seconds) before the host vehicle starts the lane-change 

Highlighted segments are used for prediction, and are the only input of the proposed method. The segments consist of all traffic participants’ trajectories in a 3-second time window. 
