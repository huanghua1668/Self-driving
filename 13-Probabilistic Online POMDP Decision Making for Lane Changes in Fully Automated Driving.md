
__state__\
does not consider any direct state transitions from a lane change left toward a lane change right state., POMDP model only need to have eight states:\
X=[\pm LcPos, \pm LcInProg, \pm LcBen]\
__action__\
three actions have been modeled, regular driving (straight) ahead, initiating a lane change to the neighbor lane (InitiateLC) and aborting a lane change \
__eward__\
elements of the reward matrix are set to...\
__transition__\
state transition matrix for p(x0jx; u) was initialized such that state transitions roughly fit with observed state transitions in real world driving scenarios. For the status quo the state transition matrices were set by using expert knowledge. 
__evalation__\
first step we used Virtual Test Drive (VTD)1 for a purely virtual simulation of the lane change decision situation against perfect noise free data.\
Second step we implemented the algorithms in our research vehicle 

apply an online Partially Observable Markov Decision Process (POMDP) to accommodate inevitable sensor noise to be faced in urban traffic scenarios. 

we propose a two step algorithm to keep the complexity of the POMDP low enough for real-time decision making while driving.

Whether __a lane change is possible depends on__ the relative distances, velocities and accelerations of other vehicles around the ego vehicle.\ 
Whether __a lane change is beneficial depends on__ the road network and the behavior of other vehicles around the ego vehicle. 

__Solving POMDPs by approximations__\
tactical decisions for driving in urban environments need to be taken fast (<100ms)\
calculate a best possible strategy iteratively to incorporate new measurements. \
apply an online decision making algorithm to avoid the complexity of computing a sophisticated, long-term policy by planning online only for the current belief state bel(xt). This is typically done by a look ahead search in the belief state space to explore only those belief states that are actually reachable from the state right now.

use a variant of Paquet et al. [20] real-time belief space search (RTBSS) approach. we use a blind policy (BP) [22], [23] to obtain a lower bound for V ∗(x) and the QMDP algorithm [24] to obtain an upper bound for V ∗(x). A blind policy is a policy, where the same action is always executed regardless of the belief state.  Our blind policy for initiating/aborting a lane change will only initiate/abort one lane change; only the drive ahead-policy is a regular blind policy. After calculating a lower and upper bound for a specific belief state, Branch-and-Bound tree search is executed on the so called policy tree. goal is to find that particular action that will result in the highest expected overall reward for the current belief state b0. 

__Modeling__\
To get line change possibility and beneficiality: signal processing networks consider relative distances, relative velocities and time to collisions with objects around the automated vehicle.\

