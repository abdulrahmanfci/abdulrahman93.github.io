---
title: 'Using reinforcement learning agent in optimzing stock market execution costs'
date: 2021-07-30
permalink: /posts/2021/07/trade-execution-1/
tags:
  - reinforcement learning
  - machine learning
  - finance
  - trade execution
  - optimization
---

<br> <br>
This post is based on the paper "Optimizing stock market execution costs using reinforcement learning" [link](http://abdulrahman93.github.io/files/Optimizing-stock-Ahmed.pdf).

Introduction
======

What is trade execution?
------

Trade execution is the completing of a purchase (or a sale) of previously specified amount on a fixed time horizon. For example, consider you asked your broker to buy 1000 shares by the end of the week; the broker can buy them all today or part today and part next day. At the end, the broker has a lot of options but the broker constrained with buying exactly 1000 shares and also that by the end of the week the 1000 shares must have been bought.

What is reinforcement learning?
------

Reinforcement learning is the branch of machine learning that concerned with learning the agent by reward. Mainly there are three branches for machine learning: supervised learning, unsupervised learning, and reinforcement learning. Supervised learning defines a label and penalizes the model for not choosing the correct label, while in unsupervised learning the concern is to discover the hidden relations and patterns. On the other hand, reinforcement learning trains the agent by a reward value (signal) which the agent can infer from it after a number of steps what is a good or a bad move. For example, if a RL agent trained to buy a share, and the reward was the negative amount of money spend on buying that share the agent will learn after a number of steps that buying the share at lower price is much better (in reward term) than buying the share at higher price. That is if the price is 50 US dollars and the agent will buy 1000 shares then losing 50000 US dollars is better than losing 58000 US dollars.
<br><br>

How can reinforcement learning help in this?
======

<br><br>



What is the technique used to solve this problem?
------

test test
The state will be defined using three variables: price, quantity, and timing. Price is the share price at time t, quantity is the amount agent holds at current time step t it could be either (0,500,1000), and timing which will be either 0 or 1 to indicate agent decision is in the first or second half of the fixed time horizon. The action will be 3 choices: buy nothing (or buy 0 shares), buy 500 shares, or buy 1000 shares. The reward will be multiplication of seized quantity times current price except in three cases:
-	Terminal states where agent already bought the required 1000 shares where the reward will be large positive value.
-	States where agent already bought 500 shares the reward to buy 1000 shares will be big negative value to discourage agent to choose the action of buying 1000 shares while having 500 shares. Where this will exceed our goal to buy 1000 shares.
-	States where the agent is in timing 1 as indicator for late buying, all rewards will be subtracted from a predefined amount to discourage lateness.

<br><br>

What are the results for the model?
======

<br><br>
<br><br>
If you still interested and need more details please check our [paper](http://abdulrahman93.github.io/files/Optimizing-stock-Ahmed.pdf).
