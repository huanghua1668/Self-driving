Multiple Futures Predictor (MFP), is a sequential probabilistic latent variable generative model that learns directly from multi-agent trajectory data. 

Motion prediction needs to model the inherently certain future which often contains multiple potential outcomes, due to multiagent interactions and the latent goals of others. 

Agents’ states do not evolve independently from one another, but rather they interact with each other. 

ability to measure uncertainty by computing probability over likely future trajectories of all agents in closed-form (as opposed to Monte Carlo sampling) is of practical importance.

algorithms are either deterministic, not multimodal, or do not fully capture both past and future interactions.

multimodality means that for a given X, there could be multiple distinctive modes that results in significant probability distribution over different sequences of Y.

For multimodality, we introduce a set of stochastic latent variables zn ∼ Multinoulli(K), one per agent, where zn can take on K discrete values. The intuition here is that zn would learn to represent intentions (left/right/straight) and/or behavior modes (aggressive/conservative). A key feature of the MFP is that zn is only sampled once at time t, and must be consistent for the next T time steps. Compared to sampling zn at every timestep, this leads to a tractability and more realistic intention/goal modeling
