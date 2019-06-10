Automated lane changing functions built on rule-based models may perform well under pre-defined operating conditions, but they may be prone to failure when unexpected situations are encountered. 

Around 10 percent of all freeway crashes are caused by lane change maneuvers

automated lane changing maneuvers has been extensively conducted and the work can broadly be divided into two functional categories: a decision-making module and a control execution module [3]. A decisionmaking module can be viewed as a strategic or tactical level function which issues a lane change command based on a planned route (e.g. exit the highway from an off-ramp forward) or a desired driving condition (e.g. drive at high speed by passing a slow vehicle in front). When a lane change command is given, the ego vehicle (i.e. lane changing vehicle) performs operational control to coordinate the longitudinal and lateral movements for a safe, smooth and efficient lane change maneuver.

lane changing maneuver, it is a typical time sequential problem where the completion of the task involves a sequence of actions, and the performance of the current action has an impact on the ultimate goal of the task (e.g. a successful lane change). Such kind of problems are quite suitable to be solved by machine learning techniques, particularly by Reinforcement Learning (RL). 

Traditional approaches for addressing the autonomous lane changing problem primarily depend on pre-defined rules and explicitly designed models. Most of these approaches introduce a virtual lane change trajectory or a series of way points for the ego vehicle to follow when a lane change process is initiated.

 A common limitation in these approaches is the lack of flexibility in the planned trajectories under dynamic situations and diverse driving styles. Moreover, though it might work relatively well in predefined situations or within the model limits, it is far from adequate in handling situations that are out of the defined scope. This is also a clear limitation in the current time-receding optimization methods such as Model Predicted Control (MPC) as the optimization criteria may be too complex to be explicitly formulated for all scenarios, and such methods always involves the predictions of future trajectories. 
 
when a vehicle reveals its intention of a lane change by turning on the turning signal, the lag vehicle on the target lane may cooperatively decelerate or change its path to yield, or it may adversarially accelerate just to deter the vehicle from cutting into its course of motion. Consequently, it is not trivial to model the environment explicitly with all possible future situations. 

leverage a well-developed car-following model, Intelligent Driver Model (IDM), to build the longitudinal controller. The lateral control is to be learned by RL with the consideration that most of those previously proposed lateral control models are far too theoretical or empirical to be applied on an autonomous vehicle.

a gap-selection module working in parallell with the two controllers. After the vehicle get a lane change command, the gap selection module will check the availability of a safety gap formed by a leader vehicle and a follower vehicle on the target lane based on all the information of surrounding vehicles. If gap is adequate enough to accommodate the speed difference under allowable maximum acceleration/deceleration and to ensure a minimum safety distance under current speed, it is considered as an acceptable gap, and then the lane change controllers will be initiated.

the gap selection module is still working as a safety guard during the whole lane changing process to check whether the gap is still acceptable at each time step. If not, the decision-making module will issue a command to alter or abort the maneuver, and the control execution module will reposition in the original lane. In this way, the longitudinal controller takes the surrounding driving environment into account to ensure longitudinal safety, whereas the lateral controller directs the vehicle to intelligently merge into any accepted gap.

the lateral control in a lane changing process is of crucial importance since a slightly fallacious shift in steering may result in the vehicle drifting out of the lane or a significant disturbance of surrounding vehicles. 

