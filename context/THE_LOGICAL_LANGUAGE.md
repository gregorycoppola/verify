# The Logical Language

The target symbolic form for extraction is the typed predicate language
developed across the trilogy of papers (Coppola 2024, 2026a, 2026b).

## The Language

- **Entities** — atomic objects with types: `socrates : e`, `france : country`
- **Predicates with labeled roles** — `trust{agent: e, patient: e}`
- **Quantified Horn clauses** — `always [x:e]: man(theme: x) -> mortal(theme: x)`
- **Negation** — NEG factors enforcing P(x) + P(¬x) = 1
- **Three tiers of expressiveness** following Prawitz (1965):
    - Tier 1: first-order quantification over entities
    - Tier 2: propositions as arguments (modality, propositional attitudes)
    - Tier 3: predicate quantification via lambda abstraction

## Why This Language

Every independent attempt to formalize reasoning converges on this structure —
Aristotle, Panini, Leibniz, Frege, Gentzen, Prawitz, Montague. When every
civilization that attempts to formalize reasoning arrives at the same structure,
the structure is a feature of reasoning itself.

The language is also minimal: three primitives (entities, predicates, rules)
and the inference rules of natural deduction. Remove any piece and you lose
expressiveness. Add anything and you gain complexity without coverage.

## The Connection to Verification

The logical language is the characteristica universalis — the universal formal
language that makes "is this correct?" a well-defined question. Without it,
there is no grounding. Without grounding, verification is undefined.

Once knowledge is expressed in this language, the calculus ratiocinator —
belief propagation over the factor graph — checks it mechanically.