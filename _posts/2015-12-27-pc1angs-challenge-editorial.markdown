---
layout: post
title:  "pc1ang's Challenge Editorial"
date:   2015-12-27 00:57:00 +0700
categories: blog
excerpt_separator: <!--more-->
---

### [Medan][medan]

This problem can be solved with [Lowest Common Ancestor][lca]. First, create a tree `T` from the graph. Let:

* `dist(u)` be the distance of node `u` from the root of `T`,
* `lca(u,v)` be the lowest common ancestor of node `u` and `v`,
* `E` be the unused edge which is not in the tree.

<!--more-->

We can compute the distance between node `u` and `v` in the tree with the information above. Let `f(u,v)` be the distance of node `u` and `v` in the tree. Then, `f(u,v)=dist(u)+dist(v)-2*dist(lca(u,v))`.

Of course, it is obvious that the answer for each query `u v` is not simply `f(u,v)`. The correct answer for each query is `min(f(u,v), f(u,E.u)+E.length+f(E.v,v), f(v,E.u)+E.length+f(E.v,u))`.

Complexity: `O(Q lg N)`

No one solve this problem. <br />
My solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge/challenges/medan/submissions/code/4389543)

Alternatively, Prabowo solve this problem with [Heavy-Light Decomposition][hld] (rather overkill). This [link](https://www.hackerrank.com/contests/pc1angs-challenge/challenges/medan/submissions/code/4389553) is his solution.

---

### [Ice Cave][ice-cave]

This problem can be solved with optimized BFS. For each direction in every "smooth ice" grid, we can _**precompute**_ how far Dyan slides toward that direction. This optimization allows the solution to pass some killer testcases. Hence, the complexity is reduced from `O(N^3)` to `O(N^2)`.

First solver: [Dian Bakti][dbakti7] <br />
My solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge/challenges/ice-cave/submissions/code/4404636)

---

### [Love String][love-string]

This is the easiest problem in the contest. Let:

* `L[i]` be the number of character `'L'` from position `1..i` (1-based index), and
* `E[i]` be the number of character `'E'` from position `i..N`.

For each `S[i] == 'O'` and `S[j] == 'V'`, where `i < j`, we can compute the number of combinations of the word `'LOVE'` as `L[i] * E[j]`. Output the sum of the number of combinations.

Complexity: `O(|S|^2)`

First solver: [Eric Leonardo][ericleo] <br />
My solution: [link](https://www.hackerrank.com/contests/pc1angs-challenge/challenges/love-string/submissions/code/4389979)

Alternatively, you may solve this with _**Dynamic Programming**_ approach which reduces the complexity to `O(|S|)`.

[lca]: https://en.wikipedia.org/wiki/Lowest_common_ancestor
[medan]: https://www.hackerrank.com/contests/pc1angs-challenge/challenges/medan
[ice-cave]: https://www.hackerrank.com/contests/pc1angs-challenge/challenges/ice-cave
[love-string]: https://www.hackerrank.com/contests/pc1angs-challenge/challenges/love-string
[dbakti7]: https://www.hackerrank.com/dbakti7
[hld]: http://blog.anudeep2011.com/heavy-light-decomposition/
[ericleo]: https://www.hackerrank.com/ericleo
