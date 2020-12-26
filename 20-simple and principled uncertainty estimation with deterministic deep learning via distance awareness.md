we first identify input distance awareness, i.e., the model’s ability to quantify the distance of a testing example from the training data in the input space, as a necessary condition for a DNN to achieve high-quality (i.e., minimax optimal) uncertainty estimation.

We then propose Spectral-normalized Neural Gaussian Process (SNGP), a simple method that improves the distance-awareness ability of modern DNNs, by adding a weight normalization step during training and replacing the output layer. 

to apply them to high-dimensional data, it is usually necessary to perform some form of feature extraction or dimensionality reduction, e.g., using a DNN. This can destroy the ”distance aware” property

We show that this provides bounds on ||h(x)−h(x')|| relative to ||x− x'||, where x and x' are two inputs, and h(x) is a deep feature extractor. 

a deep learning model logit(x) = g◦h(x) is commonly composed of a hidden mapping h : X -> H that maps the input x into a hidden representation space h(x) \in H , and an output layer g that maps h(x) to the label space.

From the mathematical point of view, this is equivalent to requiring h to satisfy the bi-Lipschitz condition 

Combined together, the bi-Lipschitz condition essentially encourages h to be an approximately isometric mapping, thereby ensuring that the learned representation h(x) has a robust and meaningful correspondence with the semantic properties of the input data x. Although not stated explicitly, learning an approximately isometric and geometry-preserving mapping is a common goal in machine learning.

(1) making the output layer distance aware and (2) making the hidden layers distance preserving

we enforce the aforementioned Lipschitz constraint on gl’s by applying the spectral normalization (SN) on the weight matrices
