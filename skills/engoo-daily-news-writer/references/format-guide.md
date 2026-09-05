# Format guide

Shared craft for every level: how a vocabulary item is built, how a source article is cut down, and what the discussion questions ask. Word counts, exercise sequences, and level-specific markup live in the level files instead.

## Vocabulary items

### Part of speech

Label with one of `(noun)`, `(verb)`, `(adjective)`, `(adverb)`, `(phrase)`, `(idiom)`, `(phrasal verb)`.

### IPA pronunciation

Vowels: `/æ/` cat, `/eɪ/` face, `/ɪ/` sit, `/iː/` see, `/ɒ/` or `/ɑː/` hot, `/əʊ/` or `/oʊ/` go, `/ʌ/` cup, `/uː/` food, `/ə/` the schwa in about.

Consonants: `/θ/` think, `/ð/` this, `/ʃ/` ship, `/ʒ/` vision, `/ŋ/` sing, `/tʃ/` church, `/dʒ/` judge.

Stress: `ˈ` before the primary syllable, `ˌ` before a secondary one — `ˌprəˌnʌnsiˈeɪʃən`.

### Definitions

Write in full sentence fragments — "To [action]…" for a verb, "A [category] that…" for a noun — using words simpler than the one being defined, and give the meaning the article uses when the word has several.

> Poor: "An innovation is an innovation."
> Better: "A new idea, method, or product."

> Poor: "Significant means significant."
> Better: "Important or noticeable; having a major effect."

### Example sentences

Put the word in a natural context that hints at the meaning, keep the grammar simpler than the word itself, vary the openings rather than starting each with "The [word] is…", and bold the target with `<b>` tags.

For "innovation (noun)": "The smartphone was a major <b>innovation</b> that changed how people communicate."

For "significant (adjective)": "There was a <b>significant</b> increase in sales after the new product launch."

## Adapting the article

**Split long sentences.** Break embedded clauses apart and prefer the active voice.

> Original: "The scientist, who had been working on the project for over a decade, finally made a discovery that would change the field forever."
> Adapted: "The scientist worked on the project for over ten years. She finally made an important discovery. It changed the field forever."

**Swap advanced words down** — except the ones carrying the story, which belong in the vocabulary list instead. Explain or drop idioms.

> Original: "The implementation of the new policy was met with apprehension."
> Adapted: "People were worried when the new policy started."

**Keep** the main facts and events, key quotes (simplified if needed), essential context, and the author's purpose and tone. **Drop** inessential background, statistical nuance, extra examples where one will do, and cultural references that would need a paragraph of their own.

## Discussion

Two or three questions checking comprehension, then two or three asking the student's own view:

- "What is the main idea of the article?"
- "According to the article, why/how/what…?"
- "What problem does the article describe? What solution does it suggest?"
- "What is your opinion about [topic]?"
- "Have you ever [experienced something related]? Describe your experience."
- "How common is [topic] in your country?"

The template wraps these in its own `<ol>`, so `{{DISCUSSION_QUESTIONS}}` takes bare `<li>` elements.

## Further discussion

Five questions that use the article as a starting point and then leave it — drawn from these patterns, and ideally spread across several of them:

1. **Opinion and values** — "Do you agree that [statement]? Why or why not?" · "How do your values influence your view on [topic]?"
2. **Future and implications** — "How might [topic] change in the future?" · "What effect could [development] have on society?"
3. **Cultural and social** — "How is [topic] viewed in your culture?" · "Do different generations see [topic] differently? Why?"
4. **Hypothetical** — "If you could change one thing about [topic], what would it be?" · "What would happen if [scenario]?"
5. **Quote** — "What do you think [person] meant by '[quote]'?" · "Can you think of an example from your own life that illustrates it?"

Unlike Discussion, this placeholder holds a whole section:

```html
<section id="further-discussion">
    <h2>Further Discussion</h2>
    <ul class="further-discussion">
        <li>Do you agree that street food defines a city? Why or why not?</li>
        <li>How might the way people eat breakfast change in the next twenty years?</li>
    </ul>
</section>
```
