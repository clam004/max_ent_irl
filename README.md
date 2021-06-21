# Maximum Entropy Inverse Reinforcement Learning

Intuitive notes and tutorial for inverse reinforcement learning using the principle of maximum entropy

# What is the Objective Function in MaxEntIRL?

Maximizing the entropy of the distribution over paths subject to the feature constraints from observed data implies that we maximize the likelihood of the observed data under the maximum entropy (exponential family) distribution.

The Product of Probabilites vs The Log Sum of Probabilities

<img src="https://render.githubusercontent.com/render/math?math=\log \left(\prod_i P(x_i)\right) = \sum_i \log \left( P(x_i)\right)">


the logarithm is a monotonic transformation that preserves the locations of the extrema, in particular, the estimated parameters in maximum-likelihood are identical for the original and the log-transformed formulation, while also morenumerically stable and symbolically easier to differentiate than the former since the sum rule is easier than the product rule for differentiation

Find the Reward Parameters that maximize the likelihood of the expert trajectories, theta_star

<img src="https://render.githubusercontent.com/render/math?math=\theta^{*} = \underset{\theta}{\arg\max} \underset{demonstrations}\prod[P(trajectories|\theta)] = \underset{\theta}{\arg\max} \underset{demonstrations}\sum log[P(trajectories|\theta)] = \underset{\theta}{\arg\max} L(\theta)">

The gradient for this Loss function L is

<img src="https://render.githubusercontent.com/render/math?math=\nabla L(\theta) = f_{expert} - \underset{trajectories}\sum P(trajectory|\theta)f_{learner} = f_{expert} - \underset{states}\sum D_{s} f_{s}">
