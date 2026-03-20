# verify

A one-stop shop for the verification thread across the research program centered on the Logical Bayesian Network (LBN) and the result that transformers are Bayesian networks.

## The Central Question

Why do we need symbolic extraction from large language models at all?

The answer is verification. Knowledge that lives in transformer weights cannot be verified. You cannot inspect a weight matrix and ask "is this true?" or "does this follow from these premises?" Verification requires symbolic form — named nodes, explicit rules, inspectable derivations.

## The Four Threads

The research program has assembled the pieces to make verification possible:

**1. The Logical Language**
A typed predicate language — entities, predicates with labeled roles, quantified Horn clauses, negation — sufficient for expressing any proposition expressible in natural language. The target symbolic form for extraction.

**2. The Parser**
A typed slot grammar that deterministically compiles natural language into the logical language, with LLM-assisted disambiguation. Symbolic extraction is not just theoretical — the pipeline exists.

**3. Transformers are Bayesian Networks**
Every sigmoid transformer with any weights implements weighted belief propagation on its implicit factor graph. The knowledge is in there. It is in weight form. The question is how to get it into symbolic form.

**4. The Finite Alphabet and No-Hallucination Theorems**
The BP transformer operates over exactly 2n² routing classes — the concept space is finite and countable. And once grounded in symbolic form, hallucination is structurally impossible: there is no mechanism to produce a conclusion without a derivation.

## Structure

    context/       -- the core concepts and arguments
    literature/    -- connections to prior work
    connections/   -- how the threads relate to each other and to the broader program

## Repos and Papers

- `shannon` — the transformers are Bayesian networks paper
- `godel` — finite alphabet theorem, no-hallucination, AND/OR decompositions
- `sigmoid-transformer-lean` — every sigmoid transformer is a Bayesian network (Lean)
- `transformer-bp-lean` — transformer implements BP (Lean)
- `hard-bp-lean` — BP exact on trees (Lean)
- `world` — the logical language, parser, and inference engine
- Coppola 2024 — The Quantified Boolean Bayesian Network
- Coppola 2026a — Statistical Parsing for Logical Information Retrieval
- Coppola 2026b — The Universal Language: A Characteristica Universalis for AI