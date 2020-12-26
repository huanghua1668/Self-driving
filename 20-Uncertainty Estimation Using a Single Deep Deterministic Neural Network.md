Our approach, deterministic uncertainty quantification (DUQ), builds upon ideas of RBF networks.

We scale training in these with a novel loss function and centroid updating scheme and match the accuracy of softmax models. By enforcing detectability of changes in the input using a gradient penalty, we are able to reliably detect out of distribution data.

Deep Ensembles is uncertain only along the decision boundary, and certain elsewhere.

DUQ consists of a deep model and a set of feature vectors corresponding to the different classes (centroids). A prediction is made by computing a kernel function, a distance function, between the feature vector computed by the model and the centroids. 

we need to enforce that DUQ is sensitive to changes in the input, such that we can reliably detect out of distribution data and avoid mapping out of distribution data to in distribution feature representations— an effect we call feature collapse. The upper bound of this sensitivity can be quantified by the Lipschitz constant of the model. We are interested in models for which this sensitivity is not too low, but also not too high, because that could hurt generalisation and optimisation. DUQ achieves this result by regularising the Jacobian with respect to the input

The uncertainty for DUQ is quantified as the distance to the closest centroid (max over the kernel distances), the uncertainty for Deep Ensembles is computed as the predictive entropy of the average output
