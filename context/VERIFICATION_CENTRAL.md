# The Central Verification Argument

The core argument is simple: knowledge in transformer weights cannot be verified.

You cannot inspect a weight matrix and ask "is this true?" You cannot ask "does
this follow from these premises?" You cannot ask "is this consistent with what
we already know?" The weight form is opaque to verification by construction —
it is a continuous high-dimensional object with no named parts.

Verification requires:

1. **Named nodes** — discrete symbols with logical identities
2. **Explicit rules** — inspectable derivations, not matrix multiplications
3. **A grounding** — a declared knowledge base against which outputs can be checked

Without all three, "is this output correct?" is not a well-defined question.
Hallucination is not a bug in this setting. It is the structural consequence of
operating without a grounded concept space.

The research program provides all three:

- The logical language supplies named nodes and explicit rules
- The parser compiles natural language into that language
- The grounding is the declared knowledge base of the LBN

Once all three are in place, verification is mechanical. The calculus either
derives the conclusion or it does not. There is no middle ground.