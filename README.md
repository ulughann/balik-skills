# balïk AI Skills

AI assistant skills for **balïk** learners — bring your word bank to Claude, ChatGPT, and Gemini.

balïk's word bank is your personal collection of saved words with spaced-repetition review. These skills let you use that vocabulary *outside* the app: generate stories written only with words you know, get quizzed, build mnemonics for stubborn words, practice conversation, and turn any text into new cards.

## What's inside

| Skill | What it does |
|---|---|
| `story-weaver` | Writes short graded stories using only your known words (plus a few new ones, glossed) |
| `quiz-master` | Runs an interactive quiz session over your word list — recall, cloze, multiple choice |
| `sentence-forge` | Generates natural example sentences and collocations for each of your words |
| `mnemonic-maker` | Builds memory hooks for the words you keep forgetting (your "leeches") |
| `chat-partner` | Roleplays everyday conversations constrained to vocabulary you've learned |
| `deck-builder` | Turns any text (article, song, menu, subtitles) into a clean new card list for your word bank |
| `hanzi-helper` | Chinese-specific: tones and sandhi, character components, pinyin, and the 4-card hanzi family |
| `weak-words-planner` | Reads your review stats and builds a focused study plan |

## How to use

### Claude (claude.ai or Claude Code)
Each folder under `claude-skills/` is a Claude Skill (`SKILL.md` with YAML frontmatter).
- **claude.ai**: Settings → Capabilities → Skills → upload the skill folder (zip it first if asked).
- **Claude Code**: copy a skill folder into `~/.claude/skills/` (personal) or `.claude/skills/` in a project, then invoke it with `/<skill-name>` or just describe the task.

### ChatGPT (custom GPT)
1. Go to chatgpt.com → Explore GPTs → **Create**.
2. In **Configure → Instructions**, paste the matching file from `chatgpt-and-gemini/`.
3. Name it (e.g. "balïk Story Weaver"), add a conversation starter like *"Here's my word list: …"*, save.

### Gemini (Gem)
1. Go to gemini.google.com → **Gems** → New Gem.
2. Paste the same file from `chatgpt-and-gemini/` into the Gem's **Instructions**.
3. Save. Optionally attach your exported word list as a knowledge file.

## Getting your words out of balïk

- **Best: export a deck as CSV.** In the app, open a deck in the deck editor → menu → **Export CSV**, then attach that file (or paste its contents) to the assistant. All skills understand balïk's CSV columns, including the Chinese 4-card hanzi families.
- **Screenshots** of your word bank / deck screens also work — all three assistants read images.
- **Type or paste** words in any format; the skills normalize whatever you give them. The simple hand-typed format is one word per line: `word | meaning` (see `wordlist-format.md`).

Going the other way, the `deck-builder` skill outputs CSV in balïk's own import format, so you can save its file and import it straight into a deck (deck editor → menu → **Import CSV**).

## Languages

Built for balïk's current courses — **Uzbek** (for English, Russian, and Turkish speakers) and **Mandarin Chinese** (HSK 1–2) — but every skill degrades gracefully to any language pair.

## License

MIT — do whatever you like.
