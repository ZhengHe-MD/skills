# skills

Personal collection of Claude Code skills, distributed via `npx skills add ZhengHe-MD/skills`. Currently home to one skill in progress: `too-ai`, which removes AI 味儿 from written text in any language.

## Language

**AI 味儿**:
Text that is grammatically correct but reads as machine-generated rather than something a real person would write — a defect of word choice, sentence rhythm, and rhetorical structure, not of factual accuracy. Applies both to translated text and to natively-generated text (e.g. a from-scratch summary with no source text ever existed), in any language — not Chinese-specific, despite the term's origin (see [[0007-generalize-to-all-languages]]).
_Avoid_: 翻译腔 alone (too narrow — that term names only literal-translation artifacts; AI 味儿 also covers native generation with no source text), "machine translation quality" (implies accuracy/BLEU-style correctness, which isn't the axis this skill fixes — accuracy is assumed, naturalness isn't)

**too-ai**:
This repo's first skill. Removes AI 味儿 from already-written text in any language (hand-written or agent-generated) — no source text to translate, nothing lost, only the templated/robotic register removed. Explicitly invoked only, no auto-fire (see [[0001-explicit-invocation-only]]).
_Avoid_: "polish" — the name this skill went by during design (see [[0003-dual-mode-distill-and-differentiate]], superseded). Dropped for connoting literary elevation, the opposite of the accessible register this skill targets. "Translate" — a separate, not-yet-built skill for source-language-to-target-language conversion that will depend on `too-ai` rather than duplicate it (see [[0006-split-too-ai-and-translate]]); the two are not modes of one skill.

**Style exemplar**:
A specific, real, well-known person whose established writing reputation is used as a compact style target instead of an enumerated rule list — the model's own training-data familiarity with that person's work does the heavy lifting. `too-ai` keeps one per language, as a short extensible list — Richard Feynman for English, 阮一峰 (Ruan Yifeng) for Chinese — each chosen for a reputation built on accessibility, not literary or scholarly merit. See [[0005-style-exemplar-ruanyifeng]].
_Avoid_: "voice reference" — that term was already used and rejected (see [[0004-taste-is-the-default-not-a-parameter]]) for a runtime-configurable pointer to a user's own writing; a style exemplar is fixed into the skill's own default, not configurable.
