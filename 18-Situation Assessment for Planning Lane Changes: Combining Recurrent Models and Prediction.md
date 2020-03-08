In this work we propose a situation assessment algorithm for classifying driving situations with respect to their suitability for lane changing. 

Over 90% of occurring accidents are attributed to human errors [3], of all accidents around 18% happen during the execution of a lane change

evaluating a situation with respect to its suitability for a lane change 

As evaluation metric we use the average accuracy acc =acc p+acc n2 , where acc p and acc n are the fractions of correctly classified frames with lt = 1 and lt = 0, respectively

Bidirectional RNNs use information from future time steps. For training this is feasible, but not for an online implementation. Thus we include a prediction component in the network. Here we use the IDM.

Experiments showed best performance when converting the inputs into an occupancy grid and embedding this before feeding it to the LSTM. The grid is partitioned into four parts - same lane before EGO; same lane behind EGO; target lane before EGO; target lane behind EGO. Each part describes 100 meters of road and is discretized into boxes representing 10 meters each.

look for actual occurring lane changes and this way learn from the behavior of the human drivers. A lane change maneuver begins once a vehicle moves towards the lane boundary without oscillations and with a certain speed (0.213 m/s), and terminates when the vehicle crosses the lane boundary, in accordance with the definition in Nie et al.
negative samples are not as well defined or easily spottable, as the drivers’ interior motives are not observable: existing works thus assume that before the execution of a lane change the driver takes a certain period of time TN to analyze the situation, assessing it as not suited for the lane change until eventually a suited situation occurs. All points in TN are labeled with lt = 0.
In a) the situation several seconds before the lane change, i.e. in TN , looks very similar, thus we deem this example unsuited. In scenario b) the situation changed significantly, thus this example has a higher chance of having a useful label.

we augment our data to make the distribution look more random and diverse by adding prolonged sequences, starting and ending at random time points and occasionally containing only positive or negative labels.

Automatic Labeling
For each data frame t we examine all data frames f i up to 3 seconds in the future and evaluate the observed time gaps in the target lane. The idea behind this labeling method is that a situation is deemed suitable for a lane change, if a lane change can be executed while all participants can continue driving close to their original speed, i.e. no hard acceleration or braking is necessary.  it uses information about future states, which are not available in an online application.

inobservability of the drivers’ intentions and are able to manually model more aggressive or passive drivers by changing the minimum time gaps

in dense traffic situations fixed time gaps are sometimes not applicable in practice - in order to manage a lane change, a driver might have to aggressively push into a gap and expect other drivers to react.
