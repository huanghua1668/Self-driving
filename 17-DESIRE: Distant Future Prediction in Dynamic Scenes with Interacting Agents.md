Future prediction can be inherently ambiguous and has uncertainties as multiple plausible scenarios can be explained under the same past situation (e.g., a vehicle heading toward an intersection can make different turns). Thus, learning a deterministic function f that directly maps {X,I} to Y will under-represent potential prediction space and easily over-fit to training data. Moreover, a naively trained network with a simple loss will produce predictions that average out all possible outcomes.

We introduce a Deep Stochastic IOC1 RNN Encoderdecoder framework, DESIRE, for the task of future predictions of multiple interacting agents in dynamic scenes.

predicts future locations of objects in multiple scenes by 1) accounting for the multi-modal nature of the future prediction (i.e., given the same context, future may vary), 2) foreseeing the potential future outcomes and make a strategic prediction based on that, and 3) reasoning not only from the past motion history, but also from the scene context as well as the interactions among the agents.

deterministic, or do not fully account for interactions, semantic context or long-term future rewards.

key traits of DESIRE are its ability to simultaneously: (a) generate diverse hypotheses to reflect a distribution over plausible futures, (b) reason about interactions between multiple dynamic objects and the scene context, (c) rank and refine hypotheses with consideration of long-term future rewards 

conditional variational auto-encoder (CVAE) framework [41] to learn a sampling model that, given observations of past trajectories, produces a diverse set of prediction hypotheses to capture the multimodality of the space of plausible futures. The CVAE introduces a latent variable to account for the ambiguity of the future, which is combined with a recurrent neural network (RNN) encoding of past trajectories, to generate hypotheses using another RNN.
CVAE is a generative model that can learn the distribution P(Yi|Xi) of the output Yi conditioned on the input Xi by introducing a stochastic latent variable zi. Essentially, a CVAE introduces stochastic latent variables zi that are learned to encode a diverse set of predictions Yi given input Xi, making it suitable for modeling one-to-many mapping.

features enables easy incorporation of multiple cues arising from past motions, scene context and interactions between multiple agents.

Since direct optimization of continuous and high dimensional Y is not feasible, we design our method to first sample a diverse set of future predictions and assign a probabilistic score to each of the samples to approximate P(Y|X; I). 
