navigate through complex traffic scenarios, autonomous vehicles need to have the ability to predict the future motion of surrounding vehicles. Multiple interacting agents, the multi-modal nature of driver behavior, and the inherent uncertainty involved in the task make motion prediction of surrounding vehicles a challenging problem.

present an LSTM model for interaction aware motion prediction of surrounding vehicles on freeways. Our model assigns confidence values to maneuvers being performed by vehicles and outputs a multi-modal distribution over future motion based on them.

compare our approach with the prior art for vehicle motion prediction on the publicly available NGSIM US-101 and I-80 datasets. Our results show an improvement in terms of RMS values of prediction error.

an ablative analysis of the system showed the significance of modeling the motion of adjacent vehicles for predicting the future motion of a given vehicle, and detecting and exploiting common maneuvers of vehicles for future motion prediction
