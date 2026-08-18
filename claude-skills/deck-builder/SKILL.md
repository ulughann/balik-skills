---
name: deck-builder
description: Turn any text — an article, song lyrics, a menu, subtitles, a photo of a sign — into a clean vocabulary card list ready to add to the balïk word bank. Use when the user shares target-language material and wants the useful words extracted as word–meaning cards.
---

# Deck Builder

You mine real material for vocabulary and hand back a clean card list the learner can type into balïk.

## Input

Any target-language material: pasted text, a URL's content they paste, lyrics, a photo of a menu or sign. Optionally their existing word list — if given, **exclude words they already have** (this is the single most valuable thing this skill does; always ask for it if not provided: "paste your current words if you want me to skip what you know").

## Extraction rules

1. **Lemmatize.** Card fronts are dictionary forms: Uzbek verbs as `-moq` infinitives, nouns unsuffixed; Chinese words as written. Note the inflected form from the text in the note column when it's instructive.
2. **Split morphology, don't card it away.** For Uzbek, when a text form is stem+suffixes, the card is the stem; genuinely productive suffixes the learner will meet everywhere (`-lar`, `-da`, `-ga`, `-ni`) may get their **own** suffix cards, written with a leading dash: `-lar | plural suffix`. Never fuse a suffix into a "word" card (`-aman` is not a word).
3. **Filter for worth.** Skip proper names, numbers, transparent loanwords in the learner's language, and words rarer than the learner's level warrants. Target 10–25 cards from a typical text; say what you skipped and why in one line.
4. **Rank by usefulness**, most frequent/general first — if they only add the top 10, those should be the right 10.

## Output format

Two modes — ask once which they want, default to the importable CSV.

### 1. Importable CSV (default)

balïk imports this directly (deck editor → menu → Import CSV). Emit a code block with this exact header, then one row per card:

```csv
id,type,front,back,source,sticker,distractors,exerciseData,groupId,hanzi,pinyin,tones,strokeRef
```

- Leave `id`, `source`, `sticker`, `distractors`, `exerciseData`, `strokeRef` **empty** — the app re-mints ids and review state on import. Only `front` and `back` are required for a classic card (leave `type` empty for classic).
- Quote any cell containing a comma per standard CSV.
- **Chinese words are a 4-row family.** For each word emit four rows sharing one made-up `groupId` (e.g. `g1`, `g2`…): types `hanziTone`, `hanziWriting`, `hanziDefinition`, `hanziPinyin`. On all four: `front` = the hanzi, `hanzi` = the hanzi, `pinyin` = **numbered** pinyin (`ni3hao3`, no diacritics, 5 = neutral), `tones` = pipe-joined syllable tones (`3|3`). `back` = the meaning for `hanziDefinition`/`hanziWriting` rows, and the numbered pinyin for `hanziTone`/`hanziPinyin` rows.
- Limits: 200 characters per text field; keep one batch ≤ 300 rows (a free deck's cap).

### 2. Simple list (for hand-typing)

```
word | meaning
word | meaning | note
```

Either mode:
- **Uzbek**: correct Latin orthography (`oʻ`, `gʻ`, apostrophe). Meaning in the learner's language (ask once: English, Russian, or Turkish).
- **Chinese**: include the measure word for nouns in the meaning (`book (本)`). Multi-character words are one vocabulary item; don't decompose into single characters unless asked.

## After the list

Offer: the same text rewritten as a graded story using only these words + their known list (story-weaver style), or example sentences for the top 5 (sentence-forge style), or extraction from the next chunk of text.
