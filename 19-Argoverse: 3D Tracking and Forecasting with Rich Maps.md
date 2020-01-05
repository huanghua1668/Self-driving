Motion forecasting experiments ranging in complexity from classical methods (k-NN) to LSTMs demonstrate that using detailed “vector maps” with lane-level information substantially reduces prediction error.

Spatial context and social interactions can influence the future path of pedestrians and cars.

For social context, we use minimum distance to the objects in front, in back, and the number of neighbors. Such heuristics are meant to capture the social interaction between vehicles. 

Predicting the future is difficult. Often, there are several plausible future actions for a given observation. In the case of autonomous vehicles, it is important to predict many plausible outcomes and not simply the most likely outcome. While some prior works have evaluated forecasting in a deterministic, unimodal way, we believe a better approach is to follow the evaluation methods of DESIRE [19] and Social GAN [11] and encourage algorithms to output multiple predictions
