+++
title = "Rejection Sampling"
author = ["Jethro Kuan"]
lastmod = 2020-03-23T16:03:45+08:00
draft = false
+++

**Goal**: To sample from unknown distribution \\(p(x)\\).

## Assumptions {#assumptions}

- we cannot sample from \\(p(x)\\)
- we have a simple proposal density \\(q(x)\\) we can evaluate within a
  multiplicative factor \\(Z_q\\)
- We know the value of a constant \\(c\\), such that \\(cq^\star(x) >
  p^\star(x)\\) for all \\(x\\)

## Method {#method}

1.  Sample from proposal density \\(q^\star(x)\\)
2.  Evaluate \\(c q^\star(x)\\)
3.  Generate a uniform distribution \\([0, c q^\star(x)]\\) and sample \\(u\\)
    from it
4.  Evaluate \\(p^\star(x)\\)
5.  If \\(u > p^\star(x)\\), reject, else accept, and add \\(x\\) to the set of
    samples

## Difficulties {#difficulties}

1.  Works well only when \\(q(x)\\) is a good approximation to \\(p(x)\\),
    keeping \\(c\\) small
2.  In high-dimensional settings, \\(c\\) will generally be so large that
    acceptances will be rare

## Backlinks {#backlinks}

- [Slice Sampling]({{< relref "slice_sampling" >}})
- [Metropolis-Hastings Method]({{< relref "metropolis_hastings" >}})
