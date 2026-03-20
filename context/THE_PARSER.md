# The Parser

From Coppola (2026a), `Statistical Parsing for Logical Information Retrieval`.

Symbolic extraction is not just theoretical. A complete pipeline exists from
natural language to logical form.

## The Architecture

    LLM preprocesses -> grammar parses -> LLM reranks -> LBN infers

## The Grammar

A typed slot grammar that deterministically compiles disambiguated natural
language into the logical language. Key properties:

- 33/33 sentences parsed with zero ambiguity
- 20 ground facts and 13 universally quantified rules produced
- Deterministic: same input always produces same logical form
- Zero ambiguity: type-driven dispatch eliminates multiple parses

## LLM-Assisted Disambiguation

LLMs cannot produce exact structured parses directly (12.4% UAS) but can
reliably perform the preprocessing tasks that eliminate ambiguity:

- PP attachment disambiguation: 95% accuracy vs 50% for Stanford parser
- POS tagging: 91% accuracy
- Parse critique when directed to specific constructions: 95% accuracy

The grammar handles structure. The LLM handles ambiguity. Neither alone
is sufficient. Together they cover open-domain text.

## The Implication for Verification

The parser is the bridge between the unverifiable (natural language, LLM
output) and the verifiable (logical forms, factor graphs, derivations).

Once text passes through the parser into the logical language, every claim
is typed, every rule is explicit, every derivation is inspectable. The
verification machinery can run.