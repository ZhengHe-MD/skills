---
name: engoo-daily-news-writer
description: Turn a news article into an Engoo Daily News lesson — vocabulary, a level-adapted article, and discussion questions for ESL levels 4-9. Use when given an article or URL to convert into lesson material, or asked to find an article and build the lesson from it.
---

# Engoo daily news writer

Build one printable Engoo Daily News lesson from one web article. The difficulty level decides everything downstream — how long the article runs and how it sounds, which words become vocabulary, and which exercises the lesson carries — so settle the level before drafting a word.

## 1. Get the article and the level

Fetch a supplied URL with the bundled script (`pip install beautifulsoup4 requests` if the imports fail):

```bash
python3 scripts/fetch_article.py <url> [output.json]
```

It prints JSON to stdout when given no output file: `title`, `description`, `word_count`, and `content` — an array of `{"type": "p"|"h2", "text": ...}` capped at roughly 600 words, with navigation and ads already dropped.

Asked to find an article instead, ask which topics interest the user — technology, health, culture, business, science, sports — and draw candidates from sources already pitched at learners: BBC Learning English, Simple English Wikipedia, News in Levels, Breaking News English. Judge each on reading difficulty and on how much a student could actually say about it.

Ask for the level when the user hasn't named one:

- **Level 4** — ~210 words, very simple and conversational
- **Levels 5-6** — 250-300 words, informative but accessible
- **Levels 7-8** — 310-350 words, journalistic, complex sentences
- **Level 9** — ~350 words, academic and formal

Finish with the article text in hand, its source name, author, and URL recorded for attribution, and one level number.

## 2. Read the structure for that level

Each band runs a different sequence of exercises and carries different level-specific HTML. Read its file before drafting:

- **Level 4** — [level-4.md](references/level-4.md)
- **Levels 5-6** — [level-5-6.md](references/level-5-6.md)
- **Levels 7-9** — [level-7-9.md](references/level-7-9.md)

Every band shares the vocabulary block, the adapted article, and the Discussion section. [format-guide.md](references/format-guide.md) holds their anatomy — part-of-speech labels, IPA symbols, definition and example-sentence standards, simplification techniques, and the question patterns to draw on.

## 3. Write the vocabulary

Pick exactly 6 words from the article at the level's own difficulty; each level file names the kind of word to look for. Every item carries the word, its part of speech, IPA pronunciation, a definition written at or below the level, and an example sentence with the target word bolded:

```html
<div class="vocabulary-item">
    <div class="vocabulary-word">word <span class="part-of-speech">(noun)</span></div>
    <div class="vocabulary-pronunciation">/ˌprəˌnʌnsiˈeɪʃən/</div>
    <div class="vocabulary-definition">Simple definition suitable for ESL learners.</div>
    <div class="vocabulary-example">Example sentence using the <b>word</b> in context.</div>
</div>
```

Define the sense the article actually uses, in words simpler than the one being defined. Finish with 6 items, each carrying all five parts and a bolded target word in its example.

## 4. Adapt the article

Rewrite the source to the level's word count and tone under a fresh news-style headline. Keep the core story, the key facts, and quotes worth keeping; drop background detail, statistical nuance, and repeated examples. Run 4-7 paragraphs of 2-4 sentences each.

Preserve the original perspective: a first-person source stays first-person, a third-person source stays third-person. Converting between them rewrites who is speaking, which is a change of fact rather than of difficulty.

Finish with the adapted article inside the level's word count and every vocabulary word appearing in it.

## 5. Write the exercises

Follow the sequence in the level file, using its HTML for the sections only that band carries. Discussion is five questions at every level: two or three checking comprehension of the article, the rest asking the student's own opinion or experience. Further Discussion, where the band carries it, is five broader questions that leave the article behind.

Finish with every section the level file lists drafted, and none it omits.

## 6. Fill the template

Read [template.html](assets/template.html) and replace every placeholder:

| Placeholder | Content |
| --- | --- |
| `{{TITLE}}` | The new headline — appears twice, page title and header |
| `{{DATE}}` | Today, as "February 22, 2026" |
| `{{DIFFICULTY}}` | The level, as "Level 6" |
| `{{SOURCE_URL}}` `{{SOURCE_NAME}}` `{{SOURCE_AUTHOR}}` | Attribution for the original; use the source name as author when there is no byline |
| `{{VOCABULARY_ITEMS}}` | The six `vocabulary-item` divs |
| `{{ARTICLE_CONTENT}}` | The adapted paragraphs, each wrapped in `<p>` |
| `{{DISCUSSION_QUESTIONS}}` | Five `<li>` elements only — the template supplies the surrounding `<ol>` |
| `{{FILL_IN_BLANKS_SECTION}}` `{{QUESTIONS_SECTION}}` `{{WOULD_YOU_RATHER_SECTION}}` `{{FURTHER_DISCUSSION_SECTION}}` | Whole `<section>` elements from the level file, or an empty string for a section this band omits |

## 7. Deliver

Write the HTML to the location the user asks for, defaulting to the working directory under a slug of the headline. Confirm `grep -o '{{[A-Z_]*}}' <file>` returns nothing before handing it over.

Report the headline and source, the level, the adapted word count, and the sections the lesson contains, then offer to adjust any of them.
