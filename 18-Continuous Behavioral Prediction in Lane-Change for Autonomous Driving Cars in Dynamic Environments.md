method serves as a predictive engine which provides trajectory estimations. The estimated trajectory then helps the motion planner to make a desired path in dynamic environments. The trajectory estimation is based on an interactive model that captures mutual influences among all surrounding cars. The model is optimized from real training data.

The behavior estimation of a surrounding car serves as prior knowledge which helps the trajectory planner generate a path to perform properly with the other vehicles.

method predicts the continuous lanechange trajectory of a target car by modeling the interaction of all its surrounding vehicles’ trajectories

Lane changes require the car to interact suitably and socially appropriately with surrounding vehicles. There are two aspects of social behavior: 1) Correctly understanding human drivers’ behaviors or intentions; 2) Reacting properly, similarly to humans

estimate when and how the target car (Veh-s) will make the lane change, and then plan a proper trajectory to react. If there is a predictive engine which gives surrounding vehicles’ future movement (the red dashed lines), trajectory planners can generate the corresponding path to perform safely. The difficulties of the trajectory estimation are: 1) modeling the mutual interactions among surrounding cars; and 2) predicting the continuous trajectories based on the interactions.

The analysis of the interaction and the future movement is based on a short period of observations of all surrounding cars’ movements. The method works as a regression that projects the current observations to produce the estimations. The interactions among cars are captured inside the regression, which is learned from training data.

Segments of trajectories from all participants before the host car starts turning towards the target lane are transformed to B-spline form β. Two seconds of historical trajectories are used for input. The prediction is the future trajectory in the next 2s after obtaining the historical observations.
