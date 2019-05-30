planning methods that provide safe and systemcompliant performance in complex, cluttered environments while modeling the uncertain interaction with other traffic participants are required.

In this survey, we emphasize recent approaches for integrated perception and planning and for behavior-aware planning, many of which rely on machine learning. This raises the question of verification and safety

Motion Planning for Autonomous Vehicles
most traditional methods to compute safe trajectories for autonomous vehicles are based on one of three lines of thought. The third is constrained optimization and receding-horizon control, which have been applied mostly to path following but now can also compute collision-free trajectories to avoid other traffic participants

autonomous vehicles will also be subject to a large set of rules. These rules impose constraints on the motion planner, which should always be satisfied. However, under some circumstances (e.g., overtaking an illegally parked vehicle), they need to be violated. the question of which rules shall be violated arises. If traffic rules are encoded in the cost function, traditional motion planning methods can be employed to find the path or trajectory of lowest cost.

BEHAVIOR-AWARE MOTION PLANNING
__Most approaches use a state machine to switch between predefined behaviors__. These rule-based approaches lack the ability to generalize to unknown situations and deal with uncertainties. Automated driving with humanlike driving behavior requires interactive and cooperative decision-making. __Other motorists’ intentions need to be deduced and integrated into a planning framework that allows for reasonable cooperative decision-making__ without the need of intervehicle communication. While autonomous vehicles need to be able to deduce the intentions of other human traffic participants, they also need to enable others to reasonably infer the autonomous vehicle’s intention. This results in interdependencies and interactions based on the seen and shown behavior without the need for explicit communication.

by modeling the anticipated future information to reduce the uncertainty that is associated with future belief states. 

Wei et al. (95) planned for two vehicles to execute a set of possible high-level policies in a Markov decision process. A search for the best policy is performed by forward simulating to find the most likely traffic scenario and then executing the corresponding policy from the set of available policies for the ego vehicle. Every policy is then scored against the ego vehicle’s cost function, and the best policy is executed. The authors associated social behavior with a simple Bayes model: Other vehicles are more likely to yield if decelerating and less likely to yield if accelerating. 

Partially Observable Markov Decision Processes
problem is often formulated as a partially observable Markov decision process (POMDP), where the intentions and replanning procedures of the other agents are not directly observable and are encoded in hidden variables

solving the most general POMDP is intractable in real-time applications, approximate POMDP solutions to simplified problem formulations are employed to avoid the complexity of computing a sophisticated, long-term policy

A reference vehicle behavior corresponding to the road context is defined, and the other vehicle’s reaction is inferred by observing the deviation from the reference behavior. A discretization of the other vehicle’s intentions (i.e., a hidden variable) allows the approach to infer other vehicles’ intentions, such as giving way or acting aggressively.
