---
permalink: /thesis/
title: "Thesis"
author_profile: true
redirect_from: 
  - /defense/
  - /thesis.html
---

# Ishan Durugkar's Thesis

## Estimation and Control of Visitation Distributions for Reinforcement Learning

### Thesis Committee:

Peter Stone (Advisor), Scott Niekum, Qiang Liu, Philipp Krähenbühl, Marc Bellemare (external)

### Abstract
    
In sequential decision making tasks an agent needs to make decisions and interact with the world in order to maximize its long-term expected utility. These tasks are complex since the agent's actions determine not just the immediate utility but also its future data stream. The distribution of this data -- the state, state-action, or transition visitation distribution -- can be considered a \emph{signature} of the agent's policy.
This thesis investigates novel techniques for incorporating the estimation and control of the state and state-action distribution induced by the policy into RL algorithms.
The main hypothesis is that these techniques improve the effectiveness of RL algorithms.

This hypothesis is tested in four main settings.
First, when dealing with sim-to-real transfer, this dissertation introduces and analyzes a method that adjusts the simulator such that the state-action visitation distribution in the simulator is similar to that in the real world for the same agent behavior.
Second, when the task itself can be specified as a target distribution, the dissertation examines whether the Wasserstein distance can be used to learn a reward function that guides the agent's state visitation distribution towards this target.
Third, it investigates whether estimating the data distribution improves the accuracy of the algorithm that evaluates the agent's behavior with a fixed batch of data.
Fourth, it investigates whether providing a target distribution derived from demonstrations of a coordinated team can be used by agents in a multi-agent environment to learn to coordinate.
In addition to these main contributions, this thesis also lays out additional directions where the estimation and control of distributions could enhance RL algorithms.
All methods in the thesis are fully implemented, and are analyzed both theoretically and empirically.

### Thesis Document

The thesis will be published by the University of Texas library in a few months. In the meantime, contact me at `ishand _at_ cs _dot_ utexas _dot_ edu` and I can mail you a copy of my thesis.

### Thesis Defense

You can access the slides of my thesis defense [here](cs.utexas.edu/~ishand/Ishan_Durugkar_Defense_Presentation.pdf)


