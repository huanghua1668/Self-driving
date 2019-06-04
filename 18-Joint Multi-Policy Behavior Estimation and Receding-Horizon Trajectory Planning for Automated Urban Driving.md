__state__\
ego: $\bm{z}^0={x,y,\theta, \delta, v}$, in which $\delta$ is teering angle, obstacle  $\bm{z}^i={x,y,\theta, v, g}$, in which $g$ is true intention, state is the joint state of ego and obstacles\
__action__\
$a={u^\delta, u^a}$, in which $u^\delta$ is steering speed, and $u^a$ is throttle\
__transition__\
trajectories of vehicle $i$ for time horizon $[0, m]$ is $\pi_i(g_j)=\{s_0^i, s_1^i,..., s_m^i\}$, in which $s=\{x, y\}$ is vehicle position. For vehicle $i\in\{1,...,n\}$ define all possible motion policies(under all motion intentions) by $\pi_i={\pi_i(g_1),...,\pi_i(g_l)}$, and their relative weights or likelihood by $p^i=[p_1^i,...,p_l^i]$.


The method leverages Partially Observable Markov Decision Processes to estimate the behavior of other traffic participants given the planned trajectory for the ego-vehicle, and Receding-Horizon Control for generating safe trajectories for the ego-vehicle. To achieve safe navigation we introduce chance constraints over multiple motion policies in the recedinghorizon planner. These constraints account for uncertainty over the behavior of other traffic participants.

Challenges lie in the uncertain motion of other traffic participants and the difficulty of predicting and accounting for their intentions and interactions with the intelligent vehicle.

a) how to model the interaction between the ego-vehicle and other traffic participants, and b) how to incorporate the uncertainty of motion intentions into the motion planning framework.

The approach leverages the strength of online Partially Observable Markov Decision Processes (POMDP) for behavior prediction and nonlinear receding horizon control, or Model Predictive Control (MPC), for trajectory planning. The estimator predicts the future speed actions of the obstacle vehicles under multiple motion intentions in the form of policies, while taking into account the planned trajectory of the ego-vehicle. Then, we formulate a nonlinear optimization problem to generate a safe trajectory for the ego-vehicle. The planned trajectory takes into account the predicted behaviors of the obstacle vehicles and the uncertainty over multiple motion hypotheses represented as chance constraints in the receding horizon framework.

 for instance the case of merging into a high-density lane of slow moving traffic. If cooperation is not modeled, it may occur that all forward paths are deemed unsafe by the planner and the vehicle freezes in place, unable to make progress. Yet, a human driver is typically able to pull in by cooperating with other traffic participants. 
 
rely on the state-of-the-art POMDP solver DESPOT [14] to compute predictions over the motion policies of other vehicles and extend the receding horizon planner of [4] to account for multiple policies and their uncertainty in the planning process for an autonomous vehicle.
