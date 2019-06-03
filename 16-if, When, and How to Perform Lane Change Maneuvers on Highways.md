mandatory, discretionary, and anticipatory lane change decisions 

automatically determine if, when, and how to perform a lane change maneuver, is essential. This paper thereby presents a low-complexity lane change maneuver algorithm which determines whether a lane change maneuver is desirable, and if so, selects an appropriate inter-vehicle traffic gap and time instance to perform the maneuver, and calculates the corresponding longitudinal and lateral control trajectory. 

The decision regarding whether a lane change maneuver is desirable is achieved by means of an utility function which weights several decision-criteria against one another.\
The decision regarding which inter-vehicle traffic gap and time instance to perform the maneuver is achieved by approximating the intersection between the vehicle’s reachable set and the safe lane change region of a certain inter-vehicle traffic gap [5].\
The decision regarding the feasibility and execution of the maneuver is formulated as an optimal control trajectory planning problem in the Model Predictive Control (MPC)

Methods for determining whether a lane change maneuver is desirable and selecting an inter-vehicle traffic gap and time instance to perform the maneuver: utility-based approaches e.g. [9] where the more advanced also accounts for uncertainties in e.g. sensor measurement and motion prediction of the surrounding vehicles

future work in incorporating a dynamic prediction model of the traffic environment which includes prediction uncertainty and sensor noise
