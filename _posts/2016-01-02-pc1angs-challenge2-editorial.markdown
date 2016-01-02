---
layout: post
title:  "pc1ang's Challenge #2 Editorial"
date:   2016-01-2 23:59:00 +0700
categories: blog
excerpt_separator: <!--more-->
---

### [Artillery][artillery]

This is [Maximum Cardinality Bipartite Matching][MCBM] problem. Create a bipartite graph `G` that connects each artillery with tanks that are within its firing range. Then, run BPM using DFS on each artillery.

Complexity: `O(N * M)` <br />
My solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/artillery/submissions/code/4407517)<br />
First solver: [ericleo][ericleo]

---

### [Constellation][constellation]

Let `S` be the set of all geometry lines that pass through every pair of stars. We need to choose a subset `T` of parallel lines from `S` which has the maximum `|T|`.

We can first create an array of geometry lines from all pair of stars. The triplet $$ (A, B, C) $$ for each line $$ Ax + By + C = 0 $$ is as follow:

$$ dx = x_i - x_j; \ dy = y_i - y_j $$

$$ A = dy; \ B = -dx; \ C = -x_i * dy + y_i * dx $$

The tricky part is that two identical lines may have different triplet $$ (A, B, C) $$. Be sure to simplify every triplet to $$ (A / k, B / k, C / k) $$, where $$ k = gcd(A, B, C) $$. Also, a line with triplet $$ (A, B, C) $$ is identical with another line with triplet $$ (-A, -B, -C) $$.

When you have generate all triplets from each pair of stars, sort them and remove duplicates. Then, you should be able to search the maximum number of parallel lines that can be formed.

Complexity: `O(N^2 lg N)` <br />
Prabowo's solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/constellation/submissions/code/4407607) <br />
No first solver

---

### [Soda Drink][soda-drink]

Easiest problem in the contest. Just binary search the answer, but look out for $$ k = 1 $$ (most people missed this).

Complexity: $$ O( T \ log_kN) $$<br />
My solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/soda-drink/submissions/code/4406528)<br />
First solver: [kenrick95][kenrick95]

[artillery]: https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/artillery
[MCBM]: https://en.wikipedia.org/wiki/Matching_%28graph_theory%29
[hopcroft]: https://en.wikipedia.org/wiki/Hopcroft%E2%80%93Karp_algorithm
[constellation]: https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/constellation
[ericleo]: https://www.hackerrank.com/ericleo
[soda-drink]: https://www.hackerrank.com/contests/pc1angs-challenge-2/challenges/soda-drink
[kenrick95]: https://www.hackerrank.com/kenrick95
