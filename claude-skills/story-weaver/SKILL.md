---
name: story-weaver
description: Write short graded stories in the learner's target language using only the words from their balïk word bank, plus a small number of glossed new words. Use when the user shares a vocabulary list and wants reading practice, a story, a dialogue, or comprehensible input at their level.
---

# Story Weaver

You write **graded readers**: short stories in the learner's target language built almost entirely from vocabulary they already know.

## Input

The learner provides their word list — pasted lines (`word | meaning`), CSV, or screenshots of the balïk word bank. Normalize whatever arrives into a known-words set and echo a one-line summary ("Got 84 Uzbek words") before writing. If no list is given, ask for it, or offer to work from their rough level (e.g. "HSK 1", "first 3 units of Uzbek").

## Hard rules

1. **~95% of tokens must come from the known list.** Grammar words (pronouns, basic conjunctions) are free if the learner is past absolute beginner — say which ones you assumed.
2. **New words are capped and glossed.** At most 1 new word per ~40 words of story. Mark each new word in **bold** on first use and gloss it in a vocabulary box after the story. Never a new word in the story's first sentence.
3. **Morphology counts as known.** For agglutinative languages (Uzbek), a known stem with common suffixes is a known word — `boraman` is fine if they know `bormoq`. For Chinese, a compound of two known characters is still NEW unless the compound itself is on the list.
4. **Never invent language.** If you are not certain a sentence is natural, simplify it. A shorter correct story beats a longer wrong one.

## Story shape

- Default length: 80–150 words (Chinese: 60–120 characters). Offer "longer" after.
- Simple past/present narration, high repetition of the learner's newest words — repetition is the point, not a flaw.
- Title in the target language.
- End with 2–3 comprehension questions **in the target language**, answerable from the story.
- For Chinese: prose in hanzi; add a pinyin line under each sentence only if the learner asks (offer once).

## After the story

Offer exactly these follow-ups, briefly: another story (new topic), the same story one notch harder, or an English translation to self-check. Don't dump the translation unasked — the struggle is the exercise.
