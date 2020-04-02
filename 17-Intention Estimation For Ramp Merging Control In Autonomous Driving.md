behaving cooperatively and naturally

learning-based method to efficiently estimate other vehicles’ intentions and interact with them in ramp merging scenarios, without over-the-air communication between vehicles. The intention estimate is generated from a Probabilistic Graphical Model (PGM) which organizes historical data and latent intentions and determines predictions

Normally, a human driver will implicitly “negotiate” with one or more drivers on a ramp, estimate their intentions, and then make decisions to successfully cooperate with them to pass the ramp merging point. 

goal of our method is to estimate whether or not the merging car intends to yield to the host car, and then safely react to it.

lack of historical data leads to instability in estimated intention, which results in oscillation or delayed reaction to the autonomous vehicle. 

human drivers estimate intentions of other cars by their current and immediately previous state and by considering the driving environment.  The __most important part of our method is understanding the causeeffect relationship among previous states and intention__. 

current state affects intention, thus speed changes. estimate the intention node once the car has observed enough information (speeds and times-to-arrival). 

human intention does not oscillate as fast as the program’s update rate. Therefore, one intention node will affect the next n speed nodes. The speeds in the last n cycles can provide movement information of the car, and thus refine the intention estimate. Physically, given intention, those speeds form a Markov Chain, which means that every speed node is affected only by its parent node (the vehicle’s previous speed).

Host vehicles are paired with merging vehicles that are close to and temporally overlapped with the host. There were 354 host-merge vehicle pairs in the dataset. We use 1/3 of the total dataset for training, and the remaining 2/3 for real-data testing.

If “Not Yield”, the merging car will be set as the target for the distance keeping model 

each speed has specific transition probabilities under different intention. Those transition probabilities are not necessarily Gaussian or of other parametric forms

reacting to merging vehicles

There are 354 pairs of merging-host pairs in US-101, and 452 pairs in I-80 

The host car uses PGM for intention estimation and ACC for distance keeping [12], and we apply real trajectories to the merging cars. In a given test, the merge car replays a real trajectory from the dataset, and the host vehicle’s start position and speed are also taken from the dataset. We then run our proposed PGM method to estimate intention of the merging car and apply the LQR control model.
The merging car replays the log in the dataset

PGM makes the correct decision that the merging car will reach the merging point first and not yield to the host car. Thus PGM sets the merging car as the following target, which makes the orange curve (PGM) diverge from the purple curve (human driving host car ground-truth) In sum, PGM is more conservative than the human driver, makes more space between the two cars, and performs similarly to human drivers at the early stage of merging.
