system drives very defensively. In dense traffic, especially during lane merging, this assumption can lead to long waiting times or driver interventions. Therefore, current research for trajectory planning is focusing on how to plan in such interactive and uncertain scenarios

predict the egovehicle with some default behavior. 

the behavior of the traffic participants is highly correlated among each other

As longitudinal action, we use the vehicle s’ acceleration s ¨ and for the lateral action we use the lateral velocity d˙. By s ¨ as a longitudinal action, we explicitly model the cars’ restrictions in velocity change, and restrict our state space. By using d˙ as a lateral action, we model the direct reaction of cars to steering. 

also implemented a multitimestep variant of the fully connected network. For this, the features of the last t timesteps are concatenated and the network is trained on them.

we assume that the motion of the cars depend on several hidden variables, so called latents.We augment the standard feed forward model above with an additional, low-dimensional layer. The output of this layer is a probability distribution. 
