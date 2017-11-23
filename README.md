# multi-armed-bandit

_by Victor I. Afolabi_


## Table of contents

- [Markov Decision Process (MDP)](#markov-decision-process-mdp)
  * state
  * action
  * reward
  * transition function
  * policy
  * the bellmans equation

- [Model-Based Reinforcement Learning](#model-based-reinforcement-learning)
  * [value iteration](#value-iteration)
  * [policy iteration](#policy-iteration)

___

## Markov Decision Process (MDP)

**state `(s)`:** Every possible position the reinforcement learning agent could be in at any given time.

**Action `(a)`:** What an agent can do in an environment or agent's interaction with the environment.

**Reward `(r)`:** What the agent gets for either performing an action `R(a)`. It could also be represented as performing an action `a` in a given state `s` denoted by `R(s,a)` or performing an action in a state and ending up in another state `s´` denoted by `R(s´|s,a)`

**Transition function `T(s,a,s´)` or `P(s´|s,a)`:** The probability that the agent is in a state `s`, performs an action `a` and ends up in another state `s´` (which could be the same state i.e `s≈s´`)

**Policy (π):** The is the solution to the MDP i.e. it is a function that takes in a state & returns an action `π(s)->a`

**The Bellmans Equation:**

$$ Q(s,a) = r + \gamma max_a(Q(s', a')) $$

___
## Model-Based Reinforcement Learning

Navigating the OpenAI's FrozenLake environment using two model-based reinforcement leaerning techniques:

- Value Iteration &
- Policy Iteration

## Value Iteration

Value iteration is ...

Pseudocode:

```
choose initial estimate of optimal value function
repeat until change in values is sufficently small {
  for each state {
    calculate the maximum expected value of
    neighboring state for each possible action
    use maximal value of the list to update estimate of optimal value function
  } each state
} convergence
```

- Value iteration computes the optimal state value function by iteratively improving the estimate of `V(s)`
- The algorithm initializes `V(s)` to arbitrary random values.
- It repeatedly updates `Q(s,a)` & `V(s)` values until they converge.
- Value iteration is guaranteed to converge to optimal values.

___

## Policy Iteration

Policy iteration is ...

Pseudocode:

```
choose initial policy & value function
repeat until policy is stable {
  1. Policy evaluation:
  repeat until change in values is sufficiently small {
    for each state {
      calculate the value of neighboring states
      when taking actions according to current policy.
      update estimate of optimal value function.
    } each state
  } converge
  2. Policy improvement:
  New policy according to Bellmans Equation,
  assuming V^* ≈ current V^π
} policy
```

___
