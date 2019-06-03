Among tactical behavior planning tasks are decision making, whether lane changes are beneficial and possible, if a vehicle should execute some cooperative driving behavior, or particular maneuvers in intersection handling. 

Whether a lane change is possible depends on the relative distances, velocities and accelerations of other vehicles around the ego vehicle. Whether a lane change is beneficial depends on the road network, the mission and the behavior of other vehicles around the ego vehicle.

Framework: A measurement model to account for uncertainties in the __transformation of measurements into state estimates__, a planning core to address the behavior planning and decision making and a situation prediction model and a reward model to support the planning core in its behavior planning.

Action= {Initiate/AbortLc, Δ𝑠, .Δ𝑠 }

__measurement model is to translate observations about the driving situation into an aggregated belief on the system’s state__. Observations entail value-discrete (e.g., number of lanes) and value-continuous aspects (e.g., distance to a front vehicle). Some aspects of the system state are observable (e.g., how long the indicator has been switched on already), and hidden. Hidden state variables may contain information, whether a lane change seems possible or beneficial in the current situation, which gap is the best to head to, etc.

three different stages within the measurement model. The leftmost part of the image depicts a visualization of the context model as an abstract scene description of the vehicle itself and its environment. The next part visualizes a situation representation of lane change relevant information. A dynamic Bayesian network is used to obtain beliefs for the distributions of hidden state variables. The rightmost part of figure 4 depicts the dynamic Bayesian network

lane changes, the __four high-level hidden state variables__ are, whether a lane change is possible and beneficial to the left and right respectively:\
Lane Change Possible Estimation: we have to consider if it is possible due to the dynamic traffic situation, due to the infrastructure, due to ability induced skill restrictions and due to the system’s current skill-level induced skill restrictions.\
Lane Change Beneficial Estimation: we need to evaluate the dynamic traffic situation for relative velocity gains on neighbor lanes and if a lane change is beneficial due to infrastructure related information\
Gap Quality Assessment: High traffic densities necessitate to adjust the automated vehicle towards a cost-optimal gap. \
Calculating and Propagating Uncertainties: Among the key challenges for tactical lane change behavior planning is the inherent uncertainty from any kind of environment perception modules. State estimates from perception modules come along with an uncertainty already. Based on this, hidden state variable estimates are calculated by the dynamic Bayesian network. 

 tree-based policy evaluation: Based on a current belief b0 at a time step t0 several actions u(i) 2 U can be executed and result in a reward r(b0; u(i)). 
 
some driver might be inattentive, gradually approaches and finally crashes into the automated vehicle without reacting at all

tree simplification: some actions can be ruled out because of not being allowed (changing lanes without indicating, given belief b0 represents normal driving). it is possible to prune the tree even further by ruling out actions would result in unreasonable policies. E.g., if a lane change was decided it will be an unreasonable policy to abort a lane change and reinitiate a second lane change in two consecutive time steps. This helps to reduce the tree complexity a lot. Every path to a fringe node at end of the planning horizon at time step t0 + T will be a possible -to a certain degree- reasonable policy. 

actions U:  contains the 13 discrete action alternatives of DoLc, FinishLc, PrepareLc, IndicateLc and AbortLc to the left and right and action alternatives for NormalDriving, AbortLcIndication and AbortLcPreparation

Situation prediction model: bel(xt+τ ) = p(bel(xt); ut). situation prediction as a whole constitutes of the prediction of several aspects of that situation. Among them are simple dynamic models for the prediction of object movements, behavior models to imitate the interaction between vehicles and simplified models to predict the ego behavior. 

intelligent driver model: It is based on predicting a longitudinal acceleration and by this calculating new longitudinal velocity and position of each object based on its environment. For the lateral prediction, we assume that vehicles will maintain their lateral offset towards their lanes. 

Current Limitations: The denser the traffic is, the more likely is the automated vehicle to not finding a sufficiently large gap, or to abort an already initiated lane change due to false object detections or track-to-lane associations. Also very challenging is the gap adjustment. Another limitation are currently highway interchanges and on- and off-ramps.
