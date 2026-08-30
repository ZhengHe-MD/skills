# Two composable skills, not one dual-mode skill

We reconsidered ADR 0003's dual-mode design. Rather than one skill that detects whether it's translating from a source or polishing already-Chinese text, we're building two separate skills: `too-ai`, which fixes AI 味儿 in already-Chinese text with nothing to translate, and a deferred `translate` skill for source-language-to-Chinese conversion. `translate` will depend on `too-ai` for its final naturalness pass — the same composition pattern already at work in this repo, where `grill-with-docs` invokes `grilling` and `domain-modeling` — rather than duplicating its rules.

This fits every other decision made in this design: explicit invocation only, no wake words, ask-before-delegating — all favor the user controlling exactly what runs, over the agent inferring which situation it's in. Mode-auto-detection was the one choice that didn't fit that pattern.

Splitting also keeps `too-ai` genuinely small and independently useful — it works on Chinese text with no translation involved at all — and independently testable, since its eval fixture needs no translation complexity.

`too-ai` is being designed and built first, as the smaller, more foundational piece. `translate` is deferred to a later session.
