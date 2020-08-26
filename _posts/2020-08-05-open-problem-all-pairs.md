---
layout: post
title: "Open Problem: Private All-Pairs Distances"
comments: true
authors: audramcmillan
timestamp: 14:00:00 -0400
categories: [Open Problems]
---

**Background:** Suppose we are interested in computing the distance between two vertices in a graph. Under edge or node differential privacy, this problem is not promising because the removal of a single edge can make distances change from 1 to \\(n − 1\\) or can even disconnect the graph. However, a different setting that makes sense to consider is that of a weighted graph \\((G, w)\\) whose topology \\(G = (V, E)\\) is publicly known but edge weight function \\(w : E \to \mathbb{R}^+\\) must be kept private. (For instance, consider transit times on a road network. The topology of the road network may be publicly available as a map, but the edge weights corresponding to transit times may be based on private GPS locations of individual cars.)

Suppose that two weight functions \\(w\\) and \\(w'\\) of the same graph \\(G\\) are considered to be neighbors if they differ by at most 1 in \\(\ell^1\\) norm. Then the length of any fixed path is sensitivity-one, so the distance between any pair of vertices is also sensitivity-one and can be released privately via the Laplace mechanism. But what if we want to release all \\(\Theta(n^2)\\) distances between all pairs of vertices in \\(G\\)? We can do this with accuracy roughly \\(O(n \log n )/\varepsilon\\) by adding noise to each edge, or roughly \\(O(n \sqrt{\log(1/\delta)}/\varepsilon)\\) using composition theorems. Both of these are roughly \\(n/\varepsilon\\). But is this linear dependence on \\(n\\) inherent, or is it possible to release all-pairs distances with error sublinear in \\(n\\)?

This setting and question were considered in [[S16](https://arxiv.org/abs/1511.04631)].

**Problem 1:** Let \\(G\\) be an arbitrary public graph, and \\(w : E \to \mathbb{R}^+\\) be an edge weight function. Can we release approximate all-pairs distances in \\((G, w)\\) with accuracy sublinear in \\(n\\) while preserving the privacy of the edge weight function, where two weight functions \\(w, w'\\) are neighbors if \\(\\\|w − w'\\\|_1 \le 1\\)? Or can we show that any private algorithm must have error \\(\Omega(n)\\)? A weaker (but nontrivial) lower bound would also be nice.

**Reward:** A bar of chocolate.

**Other related work:** [[S16](https://arxiv.org/abs/1511.04631)] provided algorithms with better error for two special cases, trees and graphs of a priori bounded weight. For trees, it is possible to release all-pairs distances with error roughly \\(O(\log^{1.5} n)/\varepsilon\\), while for arbitrary graphs with edge weights restricted to the interval \\([0,M]\\), it is possible to release all-pairs distances with error roughly \\(O( \sqrt{nM\varepsilon^{-1}\log(1/\delta)})\\)

_Submitted by [Adam Sealfon](http://www.mit.edu/~asealfon/) on April 9, 2019._
