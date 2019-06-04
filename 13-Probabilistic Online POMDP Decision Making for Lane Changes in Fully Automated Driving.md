apply an online Partially Observable Markov Decision Process (POMDP) to accommodate inevitable sensor noise to be faced in urban traffic scenarios. 

we propose a two step algorithm to keep the complexity of the POMDP low enough for real-time decision making while driving.

Whether __a lane change is possible depends on__ the relative distances, velocities and accelerations of other vehicles around the ego vehicle.\ 
Whether __a lane change is beneficial depends on__ the road network and the behavior of other vehicles around the ego vehicle. 

Solving POMDPs by approximations\
tactical decisions for driving in urban environments need to be taken fast (<100ms)\
calculate a best possible strategy iteratively to incorporate new measurements. \
apply an online decision making algorithm [19], [20], [21] to avoid the complexity of computing a sophisticated, long-term policy by planning online only for the current belief state bel(xt). This is typically done by a look ahead search in the belief state space to explore only those belief states that are actually reachable from the state right now.

use a variant of Paquet et al. [20] real-time belief space search (RTBSS) approach. we use a blind policy (BP) [22], [23] to obtain a lower bound for V ∗(x) and the QMDP algorithm [24] to obtain an upper bound for V ∗(x). A blind policy is a policy, where the same action is always executed regardless of the belief state.  Our bld policy for initiating/aborting a lane change will only
initiate/abort one lane change; only the drive ahead-policy is
a regular blind policy.
