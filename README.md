# CASIA: Reinforcement Learning 2021

---
An introduction about Observable, model-free, single agent, gradient-based and non-hierarchical RL algorithms.

This course combines UCL's(D. Silver), UC Berkley's lectures.

## Outline
<img src='imgs/drl.png' width='600'>

## Summary

1. class intro:
    1. RL vs. ML
    1. RL history:
        1. MDP: basic frame, lect2
        1. DP: model-based solution, lect3
        1. Model-based prediction / control
        1. Model-free prediction
        1. Model-free control
        1. Functional approximator
        1. Policy gradient
        1. invRL
        1. DeepRL
    1. Basic concepts: state, action, model, policy, reward, return, value
    1. Classification: target-based, learning-based, model-based
2. Markov Decision Process
    1. Markov property $\rightarrow <S, P> \rightarrow <S, P, R, \gamma> \rightarrow <S,P,R,\gamma, A>$
    1. Example: Students taking class.
    1. Example: Swapping Robot.
    1. Policy, State Value(V), Action-State Value(Q)
    1. Bellman Expectation:
        * Linear equation: analytic solution
        * DP: BFS
        * MC: DFS
        * TD: half-DFS
    1. Optimal Principle: theoretical principle
        * Bellman Optimal Equation: `target`.
3. Dynamic Programming: Due to Optimal Principle, **Model-based**
   1. Value Iteration: basic idea, limit theorem
   2. Policy Iteration: evaluation + improvement
   3. Generalized Policy Iteration: one improvement, multi-evaluation.
4. Model-free prediction learning: learn to compute one $Q$ or $V$
   1. Monte Carlo: high var, unbiased
      1. incremental MC with fixed update stepsize
   2. Temporal Difference: low var, biased, TD target, TD error
   3. batch learning of MC and TD
   4. DP vs MC vs TD: bias-var tradeoff, partial vs complete traj, markov property
      1. DP is BFS, bootstrap
      2. MC is DFS, sampling
      3. TD is partial DFS, sampling, bootstrap
   5. $TD(n) \rightarrow TD(\lambda)$: change TD target from one step to mean multi-step reward.
   6. Eligibility traces: **not quite understand** backtrace makes $TD(\lambda)$ online
5. Model-free control learning: learn to compute optimal $Q$ or $V$
    1. online learning: not require complete trajactory.
    2. $\epsilon-greedy$ + GLIE
    3. MC control
    4. Sarsa: on-policy TD control
    5. Importance sampling:
       1. off-policy vs on-policy
       2. principle: importance sampling
       3. off-policy MC, off-policy TD
    6. Q-Learning: off-policy TD control
    7. Double Q Learning:
       1. Why? Jeson Ineq
       2. Solution? One Q for evaluation, one Q for promotion
6. Value gradient: value function approximator
   1. why? large-scale RL
   2. approximator type
   3. DP by approximator
   4. Prediction Learning by approximator:
      1. LMS value iteration: linear programming only
      2. SGD value iteration
   5. Control learning = prediction learning + $\epsilon-greedy$
7. Policy gradient

## Refs

1. GLIE Monte Carlo Control learning
2. Temporal Difference: Richard Sutton
3. Sarsa: Rummery online q-learning using connectionist systems
4. Q Learning: Chris Watkins
5. Double Q Learning: H van Hasselt