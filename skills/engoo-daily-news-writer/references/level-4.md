# Level 4 — Intermediate

**Article:** ~210 words. Very simple, conversational, and direct — short single-clause sentences, simple present and past tense, everyday words, no idioms or phrasal verbs. Subheadings and bullet points are welcome where they make the page easier to scan.

**Vocabulary:** high-frequency everyday words — concrete nouns and common verbs.

**Sequence:** Vocabulary → Fill in the Blanks → Article → Questions → Would You Rather? → Discussion.

Level 4 carries no Further Discussion; leave `{{FURTHER_DISCUSSION_SECTION}}` empty. Keep the Discussion questions themselves short and plainly worded.

## `{{FILL_IN_BLANKS_SECTION}}`

Six sentences, one per vocabulary word, each blank written as `______`. Put the words in new contexts rather than reusing their example sentences, and list the word pool in a different order from the sentences.

```html
<section id="fill-in-blanks">
    <h2>Fill in the Blanks</h2>
    <p class="fill-blanks-intro">Fill in the blanks to complete the sentences. Use the words from Exercise 1.</p>
    <ol class="questions-list">
        <li>Next, add the sesame ______ to the pan.</li>
        <li>The fruit has a ______ taste, similar to limes.</li>
    </ol>
    <p class="word-pool"><strong>Words:</strong> word1, word2, word3, word4, word5, word6</p>
</section>
```

## `{{QUESTIONS_SECTION}}` — True/False

Three to five statements, each settled by the article alone, mixing true ones and false ones.

```html
<section id="questions">
    <h2>Questions</h2>
    <ol class="questions-list">
        <li>Shikuwasa taste like limes. A. True B. False</li>
        <li>The fruit is only grown in summer. A. True B. False</li>
    </ol>
</section>
```

## `{{WOULD_YOU_RATHER_SECTION}}`

Three either/or questions on the article's theme, each offering two concrete options a student can pick between without needing more facts.

```html
<section id="would-you-rather">
    <h2>Would You Rather?</h2>
    <p class="wyr-intro">Tell your tutor which of the two options you prefer, and why.</p>
    <ol class="questions-list">
        <li>Which breakfast would you rather have? <span class="wyr-options">pancakes / eggs Benedict</span></li>
        <li>Which fruit would you rather try? <span class="wyr-options">durian / dragon fruit</span></li>
        <li>Where would you rather travel? <span class="wyr-options">Tokyo / Paris</span></li>
    </ol>
</section>
```
