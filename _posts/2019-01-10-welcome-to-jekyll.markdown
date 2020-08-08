---
layout: post
title:  "Notes on TRPO"
date:   2019-01-10 07:15:05 +0800
categories: jekyll update
---

# Overview

I think the most important contribution of this paper is it proposed a policy gradient method using the constrained distance between two policies as the region for optimization instead of using a constrained ratio of combination of the old and new policy. This allows policy gradient methods to be applicable with neural networks, where a precise ratio of combination of two policies cannot be obtained easily.

Another crucial contribution is the unified framework to describe most of the policy optimization methods so that they can be just viewed as variants of the TRPO.

Three categories on Reinforcement learning:
1. Policy Iteration
2. Policy gradient
3. Derivative-free


