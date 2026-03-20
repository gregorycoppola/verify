# The Finite Alphabet Theorem

The concept space of the BP transformer is finite and countable.

This is what makes verification possible. If the concept space were infinite
or continuous, you could not enumerate the concepts, name them, or check
whether a given output corresponds to a known concept. Finiteness is the
precondition for verification.

## The Result

From `godel/BPTokenFiniteness.lean`, formally verified in Lean 4:

    theorem routing_classes_finite (n : Nat) :
        Fintype.card (RoutingKey n) = 2 * n * n

For a factor graph with n nodes, the BP transformer attention mechanism
operates over exactly 2n² distinct routing classes.

A routing class is defined by the triple (nodeType, ownIndex, neighborIndex).
Two tokens with the same routing key receive identical attention patterns
regardless of their continuous parameters — belief values, factor table entries.

The routing key is meaning. The continuous dimensions are magnitude.

## The Binarization Assumption

The 2n² count assumes the pairwise BP transformer — the form where each
factor node connects exactly two variable nodes. This is without loss of
generality: any k-ary factor graph binarizes exactly via the AND and OR
decomposition theorems in `godel/ANDDecomposition.lean` and
`godel/ORDecomposition.lean`.

The 2n² count applies to the binarized graph. Since binarization is exact
and lossless, this covers the general case.

## The General FSM Result

A separate result in `godel/FiniteStateSpace.lean` says:

    Any FSM with n states can distinguish at most n^n input behaviors.

This is a general statement about any finite verifier — nothing specific
to transformers. The n here is the number of verifier states, not the
number of factor graph nodes. These are different theorems with different
n's. Both are correct. Both support the general theme that verifiable
inference requires a finite concept space.

## What This Means for Verification

Once the concept space is finite, concepts can be named. Once named, outputs
can be checked against a declared knowledge base. Once checkable, verification
is mechanical. The finite alphabet theorem is what closes the gap between
"transformers are Bayesian networks" and "we can verify what a transformer
is doing."