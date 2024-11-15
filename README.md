# Pacman-AI
This project contains code related to value iteration, Q-learning, and analysis in a reinforcement learning environment, specifically for Pacman AI. It includes three main components:

* valueIterationAgents.py: Implements value iteration algorithms, including value iteration, asynchronous value iteration, and prioritized sweeping value iteration for a Markov decision process (MDP).
* qlearningAgents.py: Implements Q-learning algorithms, including standard Q-learning and approximate Q-learning with feature extraction.
* analysis.py: Contains parameters for specific reinforcement learning scenarios, used to tune the behavior of the agents.
  
Components Breakdown

1. valueIterationAgents.py
* ValueIterationAgent: This agent performs value iteration over a Markov decision process (MDP), updating its value function over a specified number of iterations. The value of a state is computed using the Bellman equation, and the best action is chosen based on the computed values.
* AsynchronousValueIterationAgent: A variant of value iteration where the agent updates the value of one state at a time, cycling through the states in the MDP.
* PrioritizedSweepingValueIterationAgent: This variant of value iteration prioritizes updates to states that are most likely to affect the values of other states, improving efficiency.

Key Functions:
* runValueIteration(): The main function that iteratively updates the values of states based on the current policy.
* getValue(): Returns the value of a state.
* computeQValueFromValues(): Calculates the Q-value (expected utility) for a state-action pair based on the current value function.
* computeActionFromValues(): Returns the best action for a state based on the current value function.

2. qlearningAgents.py
* QLearningAgent: Implements Q-learning, an off-policy reinforcement learning algorithm where an agent learns an action-value function (Q-values). The agent updates its Q-values based on experiences during training, adjusting for the reward received and the best possible future state.
* PacmanQAgent: A subclass of QLearningAgent with Pacman-specific parameters.
* ApproximateQAgent: A variant of QLearningAgent that uses function approximation, applying feature extraction to estimate Q-values.

Key Functions:
* getQValue(): Returns the Q-value of a state-action pair.
* computeValueFromQValues(): Returns the maximum Q-value over all legal actions for a state.
* getAction(): Chooses an action based on the epsilon-greedy strategy (random action with probability epsilon, otherwise the best policy action).
* update(): Updates the Q-value based on the observed reward and the maximum Q-value for the next state.

3. analysis.py
* question2(): Returns parameters for a specific scenario where the agent is less sensitive to noise (fear of cliff is reduced).
* question3a(): Adjusts parameters to encourage the agent to prefer closer exits and riskier behavior near cliffs.


Dependencies:

* MDP (Markov Decision Process): The project assumes you have an MDP environment where the agent operates. This environment provides the necessary methods for querying states, actions, and rewards.
* ReinforcementAgent: The base class from which QLearningAgent and its variants inherit.

The analysis.py file helps adjust parameters such as the discount factor and noise, which influence how the agent behaves during learning. This is useful for testing different environments and fine-tuning the agent's policy.
