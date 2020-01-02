define intent as a combination of discrete high level behaviors as well as continuous trajectories describing future motion. The intention of an actor can be seen as the sequence of actions it will take in order to achieve an objective.

One of the fundamental difficulties is that self driving vehicles have to share the roads with human drivers, which can perform maneuvers that are difficult to predict.

Human drivers understand intention by exploiting the actors’ past motion as well as prior knowledge about the scene (e.g. the location of lanes, direction of driving). 

Inspired by how humans perform this task, we design a network that exploits motion and prior knowledge about the road topology in the form of maps containing semantic elements such as lanes, intersections and traffic lights.

To address the high imbalance in the intention distribution, we downsample the dominant classes (keep lane, stopping/stopped and parked by 95%. We found this strategy to work better than re-weighting the loss by the inverse frequency in the training set. Note that we do not discard those examples for detection and trajectory regression.

extract several handcrafted features including base features such as velocity, acceleration, number of lanes to the curb and the median and headway distance to preceding vehicle, at the current time step; history features containing such information for previous time steps; traffic features containing up to six neighbours base features and rule features such as whether the car can turn left/right from its lane.
