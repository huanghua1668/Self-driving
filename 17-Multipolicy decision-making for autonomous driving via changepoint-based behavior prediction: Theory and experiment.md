__state__\
a state x_t^v is a tuple of the pose, velocity, and acceleration\
__obervation__\
a tuple including the observed poses and velocities of nearby vehicles and an occupancy grid of static obstacles.
__action__\
tuple of controls for steering, throttle, brake, shifter, and turn signals.\
__transition__\
driver model: D(x, z ,a)=p(a|x, z)

__POMDP simplification__\
approach is made tractable by considering only a finite set of a priori known policies (as illustrated in Fig. 1). Each policy is designed to capture a different high-level behavior, such as following a lane, changing lanes, or turning at an intersection.

an integrated inference and decision-making approach for autonomous driving that models vehicle behavior for both our vehicle and nearby vehicles as a discrete set of closed-loop policies. Each policy captures a distinct high-level behavior and intention, such as driving along a lane or turning at an intersection. We first employ Bayesian changepoint detection on the observed history of nearby cars to estimate the distribution over potential policies that each nearby car might be executing. We then sample policy assignments from these distributions to obtain high-likelihood actions for each participating vehicle, and perform closed-loop forward simulation to predict the outcome for each sampled policy assignment. After evaluating these predicted outcomes, we execute the policy with the maximum expected reward value. 

two interleaved stages: behavioral prediction and policy selection. First, we leverage Bayesian changepoint detection to estimate the policy that a given vehicle was executing at each point in its history of actions, and then inferring the likelihood of each potential intention of the vehicle. \
Next, using the inferred distribution over policies for other vehicles, we select a policy to execute by sampling over policy assignments to the egovehicle and traffic vehicles and simulating forward to evaluate the outcomes of each policy decision. The reward function for a policy choice combines multiple user-defined metrics, and the final policy for the egovehicle maximizes the reward over all the sampled outcomes. 

we propose a statistical test based on changepoint detection to identify anomalous behavior of other vehicles, such as driving in the wrong direction or swerving out of lane. 

our system is able to anticipate and exploit coupled interactions with other vehicles, allowing us to avoid overly-conservative decisions.

