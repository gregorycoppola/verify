# Transformers Are Bayesian Networks

From the `shannon` paper, Theorem 1.1, formally verified in Lean 4:

    For any sigmoid transformer weights W, there exists an implicit factor
    graph G(W) such that one forward pass implements one round of weighted
    belief propagation on G(W).

## What This Means for Verification

Every trained LLM is already performing weighted belief propagation on an
implicit factor graph defined by its learned weights. The knowledge is in
there. It is just in weight form rather than symbolic form.

The difference between a standard LLM and a grounded QBBN transformer is
not architectural. Both are Bayesian networks. The difference is grounding:

- **Grounded:** the factor graph is explicit and verifiable. Every output has
  a declared correct answer. Hallucination is structurally impossible.
- **Ungrounded:** the factor graph is implicit, defined by learned weights.
  There is no declared world to be correct against.

## The Uniqueness Result

Theorem 1.4 of the `shannon` paper:

    A sigmoid transformer that computes exact Bayesian posteriors for all
    inputs necessarily has BP weights.

There is no other path through the sigmoid architecture to exact posteriors.
If you want verification, you need BP weights. If you have BP weights and a
grounded tree, you have verification.

## The Implication

The knowledge learned by gradient descent on language data corresponds to
factor potentials in an implicit Bayesian network. Symbolic extraction is the
process of making that implicit factor graph explicit — giving its nodes
logical names and its factors explicit rules.