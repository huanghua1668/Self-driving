the energy scores better distinguish in- and out-of-distribution samples than the traditional approach using the softmax scores. Unlike softmax confidence scores, energy scores are theoretically aligned with the probability density of the inputs and are less susceptible to the overconfidence issue.

propose an energy-bounded learning objective to fine-tune the network. The learning process shapes the energy surface to assign low energy values to the indistribution data and higher energy values to OOD training data. Specifically, we regularize the energy using two square hinge loss terms, which explicitly create the energy gap between in- and out-of-distribution training data. 

In practice, we choose the threshold using in-distribution data so that a high fraction of inputs are correctly classified by the OOD detector G(x).
