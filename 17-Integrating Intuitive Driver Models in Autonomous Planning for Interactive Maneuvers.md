To guarantee smooth integration and maintain the nuanced social interactions on the road, a shared mental model must be developed. This means that the behaviors of humandriven vehicles and their typical interactions in collaborative maneuvers must be modeled and understood in an accurate and precise manner. Then, by integrating such models into autonomous planning, we can develop control frameworks that mimic this shared understanding. We present a driver modeling framework that estimates an empirical reachable set to capture typical lane changing behaviors. This method can predict driver behaviors with up to 90% accuracy and cumulative errors less than 1 m. Leveraging this driver model in an optimization-based trajectory planning framework, we can generate trajectories that are similar to those performed by humans. 

Using a model that captures the boundaries of likely trajectories and integrating this in a trajectory planning algorithm, we aim to assist the integration of autonomy into society. The resulting framework automatically generates human-like paths, matching typical human interaction metrics in cooperative maneuvers.

Introducing a driver modeling framework that can be utilized in collaborative maneuvers that captures the non-deterministic behaviors of humans.

Analyzing typical human driving interactions with respect to these predictions during lane changes.

Implementing an optimization-based planning framework that use these findings to mimic human driving interactions to ease integration.

100-Car Naturalistic Driving Study: The study mainly focused on crashes and near-crashes of vehicles during lane change maneuvers– essentially the failure of cooperative maneuvers. The key results found that incidents were primarily due to inadequate awareness of the environment. In particular, the authors emphasized the complex competing objectives of maintaining awareness of the forward and rear roadway versus monitoring the adjacent lane in executing the lane change maneuver.

by incorporating improved human models into lane changing frameworks, we can improve the robustness of automated vehicle cooperative maneuvers under heavy traffic

human behaviors are often peculiar and irrational, they generally do not satisfy the Markov property or align with knownparametric distributions. 

there is a great deal of work remaining in modeling cooperative behavior of drivers to capture the wide variety of driving behaviors under various conditions. 

present a method that leverages a nonparametric driver model that can readily be adapted to many scenarios for the purposes of collaborative planning. We utilize a large dataset for an empirical method to capture interaction in lane changing maneuvers in an online fashion. This planning framework aims to mimic the interactions and collaborative behaviors that humans exhibit on the road. 

__Driver Modeling Algorithm__\
developed a robust set prediction that puts bounds on the trajectory space the vehicle might inhabit in the future T seconds, that relies on data-driven hybrid systems approach.

In essence, given some dataset, this identifies the representative set by rejecting outliers to find the most precise subset that satisfies some probability threshold.

__Predicting Driver Interactions.__\
D = {X^A, X^B, E}: where X A is a collection of trajectories (as in Eq. 2) associated with sA actions lane change executions, X B is a collection of trajectories associated with with sB actions allowing merges, and E is the set of features that describe the state of the environment (including vehicles C and D) at each lane change.For each lane change sample, suppose we can estimate the current state of the environment at time t = 0, ei ∈ Rm, which is a vector where each element represents one of the observable states or features of all the vehicles in the network previously described at the beginning of the trajectory samples.\
given the current scenario el, we would like to identify the subset of similar scenarios in our environment library E, and then predict the lane change merging behaviors from our dataset X^B(S), and finally calculate $\Delta(X^B(S), α)$ to predict the likely behavior from vehicle B(see Fig 3). Finally get about 500 samples of lane changes.


By mimicking the human behaviors, the resulting autonomous control scheme more closely shares a mental model with other drivers on the road. Not only does this ensure predictability and understanding [9], but also helps to smooth the integration of autonomous vehicles, as the control policy is similar to the human policy that collected data and built the driver model. 
