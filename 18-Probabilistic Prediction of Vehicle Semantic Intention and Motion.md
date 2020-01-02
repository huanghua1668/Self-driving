some drivers have poor driving habits such as changing lanes without using turn signals, which adds difficulties for prediction. Moreover, human drivers might easily overlook dangerous situations due to limited concentration.

proposed to use semantics to represent the driver intention, which is defined as the intent to enter each insertion area. These areas can be the available gaps between any two vehicles on the road or can be the lane entrances/exits.

Variational Gaussian Mixture Model (VGMM) was proposed for probabilistic long-term motion prediction 

We assign a Gaussian Mixture Model (GMM) to each insertion area and multiple GMMs will be involved in one driving scenario. Each Gaussian mixture models the probability distribution of a certain type of motion for the predicted vehicle.

A threshold of 0.3 for classification was chosen for making the best tradeoff between a high TPR and a low FPR.
