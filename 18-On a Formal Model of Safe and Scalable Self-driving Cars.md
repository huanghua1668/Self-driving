Mobileye paper on Responsibility-Sensitive Safety (RSS)

propose a white-box, interpretable, mathematical model for safety assurance, which we call Responsibility-Sensitive Safety (RSS).  we introduce a model called “Responsibility Sensitive Safety” (RSS) which formalizes an interpretation of “Duty of Care” from Tort law.

a multi-agent system interacts with its environment and thus cannot be validated offline

developing a system through data invariably suffers from lack of transparency, interpretability, and explainability of the actions being taken

RSS is a rigorous mathematical model formalizing an interpretation of the law which is applicable to self-driving cars. RSS is designed to achieve three goals: first, the __interpretation of the law should be sound__ in the sense that it complies with how humans interpret the law. While we are at it we would like also to prove “utopia” — meaning that if all agents follow RSS’s interpretation then there will be zero accidents. Second, the __interpretation should lead to a useful driving policy__, meaning __it will lead to an agile driving policy rather than an overly-defensive driving__ which inevitably would confuse other human drivers and will block traffic and in turn limit the scalability of system deployment; third, the __interpretation should be efficiently verifiable__ in the sense that we can rigorously prove that the self-driving car implements correctly the interpretation of the law. 

second contribution evolves around the __introduction of a “semantic” language__ that consists of units, measurements, and action space, and specification as to how they are incorporated into Planning, Sensing and Actuation of the autonomous vehicles. language of human driving policy is about longitudinal and lateral goals. show that in a reinforcement learning setting we can define the Q function3 over actions defined over a semantic space in which the number of trajectories to be inspected at any given time is bounded by 104 regardless of the time horizon used for Planning. 

__Planning, commonly referred to as driving policy__, is where decisions are made about what strategic (i.e. change lanes) and tactical (i.e. overtake the blue car) decisions to take. Acting is the issuance of the decision (translated into mathematical trajectories and velocities) to the various actuators within the vehicle to perform the driving decision.

A disengagement is roughly defined as a situation where a human safety driver had to intervene in the operation of the AV because it made an unsafe decision that was going to lead to an accident. 

it is impossible to achieve absolute safety

Traffic laws are well defined until one encounters the elusive directive, common in Tort law, called the Duty of Care. The Duty of Care states that an individual should exercise “reasonable care” while performing acts that could harm others. 

If the driver must take into account the extreme worst case about the actions of other road users then driving becomes impossible. Hence, the __human driver makes some “reasonable” assumptions about the worst case scenarios of other road-users. We refer to the assumptions being made as an “interpretation” of the Duty of Care law__.

5 “common sense” rules:
1. Do not hit someone from behind.
2. Do not cut-in recklessly.
3. Right-of-way is given, not taken.
4. Be careful of areas with limited visibility
5. If you can avoid an accident without causing another one, you must do it.

let st be some representation of the road, and the positions, velocities, and accelerations, of the ego vehicle as well as other road users. Let at be a lateral and longitudinal acceleration command. 

we are using a function approximation for Q, and since there is noise in measuring the state st, it is likely that our approximation to the Q value is noisy. This yields a very small signal-to-noise ratio, which leads to an extremely slow learning, especially for stochastic learning algorithms which are heavily used for the neural networks approximation class.

the instructions are of semantic nature — “follow the car in front of you” or “quickly overtake that car on your left”. We formalize a semantic language for such instructions, and use them as a semantic action space. We then define the Q function over the semantic action space. We show that a semantic action can have a very long time horizon, which allows us to estimate Q(s; a) without planning for many future semantic actions. 

__define our semantic action space__. The main idea is to __define lateral and longitudinal goals, as well as the aggressiveness level of achieving them__. Lateral goals are desired positions in lane coordinate system. Longitudinal goals are of three types. The first is relative position and speed w.r.t. other vehicles, The second is a speed target,  The third is a speed constraint at a certain position. The aggressiveness of achieving the goal is a maximal (in absolute value) acceleration/deceleration to achieve the goal. __With the goal and aggressivness defined, we have a closed form formula to implement the goal, using kinematic calculations__. The only remaining part is to determine the combination between the lateral and longitudinal goals. variable time required for fulfilling these semantic actions is not the same as the frequency of the decision making process.

For each choice of a meta-action, we construct a geometrical trajectory (s1; a1),..., (sT ; aT ) that represents an implementation of the meta-action, as. To do so we of course need to know how other agents will react to our actions, but for now we are still relying on (the non-realistic) assumption that st+1 = f(st; at) for some known deterministic function f. 

While we do take into account some reactions of other agents to our actions (for example, we assume that if we will perform a safe cut-in, then the car behind us will adjust its speed so as not to hit us from behind), __it is not realistic to assume that we model all of the dynamics of other agents. The solution to this problem is to re-apply our decision making at a high frequency, and by doing this, we constantly adapt our policy to the parts of the environment that are beyond our modeling__. In a sense, one can __think of this as a Markovization of the world at every step__. This is a common technique that tends to work very good in practice as long as the balance between modeling error and frequency of planning is adequate.
