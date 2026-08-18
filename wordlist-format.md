# Word list format

Every skill in this repo accepts your vocabulary in **any** form — pasted text, CSV, or screenshots of the balïk word bank. But if you want the cleanest results, use one line per word:

```
word | meaning
```

Optional third column for notes (part of speech, tone, example):

```
word | meaning | note
```

## Examples

### Uzbek
```
non | bread
suv | water
bormoq | to go
-lar | plural suffix
yaxshi | good | also "well" as adverb
```

Suffixes keep their leading dash, exactly as balïk shows them.

### Chinese
```
你好 | hello | nǐ hǎo
水 | water | shuǐ
喜欢 | to like | xǐhuan
```

For Chinese, put the **pinyin with tone marks** in the note column. If you don't know it, leave it out — the skills will fill it in.

## Marking difficulty (optional)

If a skill asks which words you struggle with, add a `!` at the start of the line:

```
! kechirasiz | excuse me
! 谢谢 | thank you | xièxie
```

## balïk's CSV export (the best input)

The app exports any deck as CSV (deck editor → menu → **Export CSV**). Every skill accepts this file directly. Its header row is:

```
id,type,front,back,source,sticker,distractors,exerciseData,groupId,hanzi,pinyin,tones,strokeRef
```

What the skills read from it:
- `front` / `back` — the word and its meaning.
- `type` — empty means a classic card; `cloze` fronts contain `{{gap}}` markers; the four Chinese types are `hanziTone`, `hanziWriting`, `hanziDefinition`, `hanziPinyin`.
- A Chinese word appears as **up to four rows** sharing one `groupId` — that's one word, not four. Skills treat the family as a single vocabulary item using its `hanzi`, `pinyin` (numbered, e.g. `ni3hao3`), and `tones` (`3|3`).

## balïk's CSV import (what deck-builder outputs)

The same 13-column format goes back in via deck editor → menu → **Import CSV**. Only `front` and `back` are required; ids are re-minted on import and review state always starts fresh. Limits: 200 characters per text field, 300 cards per deck (1200 with Pro).

## From screenshots

Screenshot your deck or word bank list in the app and attach the images. Tell the assistant which language the course is; it will extract the pairs and confirm the list with you before starting.
