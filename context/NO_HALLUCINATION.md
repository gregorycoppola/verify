# The No-Hallucination Theorem

From the `shannon` paper, Corollary 1.3, formally verified in Lean 4:

    A transformer with BP weights, run for T >= diameter(G) passes over a
    grounded tree-structured knowledge base, computes exact Bayesian posterior
    beliefs at every node. No empirical assumptions required.

## What Hallucination Is

Within the LBN framework, hallucination has a precise technical definition:

    An agent hallucinates at node j if it outputs belief b(j) != P_true(j)

where P_true(j) is the true marginal posterior given the knowledge base and
observed evidence.

## Why It Cannot Happen on Grounded Trees

A transformer with BP weights running over a fully grounded tree-structured
factor graph cannot hallucinate because:

1. Every token's routing key corresponds to a specific concept in the factor graph
2. Every computation step has a verifiable correct answer
3. The BP weights are the unique weights that produce exact posteriors

The uniqueness result closes the circle: exact posteriors force BP weights,
and BP weights on grounded trees produce exact posteriors.

## What Hallucination Requires

Hallucination requires at least one of:

- Wrong weights
- Wrong routing
- Absence of grounding

On a grounded tree with BP weights, none of these conditions holds.

An ungrounded language model has no declared domain, therefore no fact of the
matter about whether its outputs are correct. Hallucination in that setting is
not occasional failure. It is the structural consequence of operating without
a grounded concept space.