# Rules For Writing Texts

These rules apply to any prose written for the books, contracts,
or other documents in this project (chapters, forewords, 
summaries, blurbs, captions, etc.). 

The goal is to write text that already reads like a
human wrote it in one sitting, from the first draft onward -
not to produce AI-sounding prose and clean it up later.

Source of truth for *why* each rule exists:
`.claude/skills/humanize/SKILL.md`. That skill describes how
to rewrite AI text back into human text. These rules are the
same guidance, flipped: never introduce those patterns in the
first place.

## Overall goal

Real human prose has uneven sentence lengths, specific word
choices, and the occasional rough edge. It does not have
balanced clauses on every line, tricolons in every paragraph,
em-dashes every few sentences, or the same paragraph shape
over and over. Write with a voice. Commit to opinions
instead of hedging both sides of every question.

## Rule 1: Characters to avoid

Never use these characters when writing documents or prose. 
They are the clearest giveaways of machine-generated text.

| Avoid | Use instead |
|---|---|
| `—` em-dash (U+2014) | split into two sentences, or use a colon `:` - rarely, a plain hyphen with spaces ` - ` |
| `–` en-dash (U+2013) | hyphen `-`, or the word `to` in ranges |
| `"` `"` curly double quotes | `"` straight double quote |
| `'` `'` curly single quotes | `'` straight single quote |
| `…` ellipsis (U+2026) | `...` (three dots) |
| `•` `‣` `▪` bullet glyphs in prose | a real Markdown list, or remove |
| non-breaking space, zero-width space, thin space | a regular space |
| decorative emoji and pictographs (✨🚀📊💡🎯) | remove, unless the user specifically asked for them |
| mathematical/fancy letters (𝐁𝐨𝐥𝐝, 𝘐𝘵𝘢𝘭𝘪𝘤) | normal letters; use Markdown `**bold**` / `*italic*` for emphasis |

Em-dashes deserve special discipline. A human author uses at
most one or two per page. Default to zero. When you are
tempted to use one, prefer two short sentences or a colon.

## Rule 2: Vocabulary to avoid

Do not reach for these words. Plain English is almost always
better. Entries marked *(delete)* are usually filler that
adds nothing once removed.

**Verbs - pick a concrete one:**
- delve into -> look at, examine, get into
- leverage -> use
- utilize -> use
- foster -> build, encourage, create
- cultivate -> build, grow
- harness -> use, take advantage of
- unlock -> enable, allow, reveal *(often just delete)*
- empower -> let, help, allow
- embark on -> start, begin
- navigate -> handle, deal with, work through
- streamline -> simplify, speed up

**Adjectives - most are hedge-inflation:**
- robust -> strong, solid *(or delete)*
- seamless -> smooth *(usually delete)*
- comprehensive -> full, complete, thorough
- multifaceted -> complex *(or delete)*
- pivotal, crucial, paramount, vital -> important *(or delete)*
- cutting-edge, state-of-the-art -> new, current, advanced
- ever-evolving, ever-changing -> changing *(or delete)*
- transformative, groundbreaking -> new, big, major

**Metaphor nouns that appear in every AI paragraph:**
- landscape (of X) -> field, area, or just the noun itself
- tapestry -> *delete*, or "mix"
- realm -> area, field, world
- journey -> process, path
- treasure trove -> collection, set
- wealth of -> lot of, many
- myriad, plethora -> many, a lot of

**Phrases to never write:**
- "It's important to note that..." - just state the thing
- "It's worth mentioning..." - just mention it
- "In today's fast-paced world..." - delete
- "In the realm of X" - "In X"
- "At the end of the day..." - delete
- "In conclusion" / "In summary" - delete; if a summary is
  needed, write it without announcing it
- "Let's dive in" / "Let's explore" - delete
- "This is a testament to..." - rewrite directly

**Hedging inflation - tighten:**
- "could potentially" -> "could" or "might"
- "may possibly" -> "may" or "might"
- "it is generally considered that" -> "most people think"
  or just state the claim
- "some might argue" -> name who, or delete

## Rule 3: Rhythm and structure

This is where AI prose still fails even after the vocabulary
is cleaned up. Watch the cadence as you write.

**No tricolon habit.** AI loves three-item lists, especially
parallel ones: "clear, concise, and compelling"; "fast,
reliable, and scalable." A human uses tricolons sparingly.
If you write one, read the paragraph again and consider
cutting an item or changing the structure.

**No "not X, but Y" drumbeat.** Rhetorical contrasts like
"This isn't just a tool; it's a platform" get boring fast.
Prefer a direct assertion of the point you actually want to
make.

**Vary sentence length.** LLM prose clusters around 15-25
words per sentence, every one about the same size. Human
writing varies more. Mix long sentences with short ones. An
occasional fragment. Like this. Then a long, winding
sentence that carries the reader along and lets the paragraph
breathe before snapping back to something brief.

**Vary paragraph shape.** Do not make every paragraph a
topic-sentence / two-supporting-sentences / wrap-up unit.
Let some paragraphs be a single sentence. Let others run
long without a tidy conclusion.

**Commit to a view.** When a real answer exists, take it.
Do not produce symmetrical "on one hand / on the other hand"
paragraphs on every question. Real writers have opinions.

**No over-signposting.** Do not announce what the text is
about to do. Drop openers like "First, let's consider...",
"Now, turning to...", "To summarize...". Structure should be
obvious from the content, not from announcements.

## Rule 4: What to preserve

These are not AI tells. Leave them alone.

- **Facts, numbers, names, and quotes.** Never "smooth out"
  a number or rename a person because it reads cleaner. If
  something seems factually wrong, flag it to the author; do
  not silently edit.
- **The author's argument and intent.** These rules govern
  surface and rhythm, not substance. Humanizing the voice
  must not change what the book or document says.
- **Technical terms in technical contexts.** "Leverage a
  load balancer" may be the right phrase in a systems
  chapter. Replace only when the word is filler, not when
  it is the accepted term of art.
- **Domain conventions.** Legal, medical, academic, and
  audit/compliance writing have their own rhythms that can
  look AI-ish but are not. Follow the conventions of the
  specific domain the chapter is written in.

## Rule 5: Delivery

When the user asks for a draft, return the draft itself. No
preamble ("Here is the chapter..."), no summary of choices
made, no closing offer to revise. Default to clean output.

If the user asks what was changed or why a word was picked,
explain then. Otherwise stay out of the way of the prose.

## Example

**Do not write this:**

```
In today's fast-paced digital landscape, it's crucial to
leverage cutting-edge tools to navigate the ever-evolving
challenges of remote work. This isn't just about
productivity - it's about fostering a seamless, robust, and
comprehensive workflow that empowers teams to thrive.
```

**Write this instead:**

```
Remote work keeps changing, and the tools for it keep
changing too. Picking the right ones matters. Not just for
getting more done, but for building a workflow the whole
team can actually rely on.
```

What changed: the opener cliche is gone, the tricolon is
gone, "leverage / navigate / foster / empower / seamless /
robust / comprehensive / cutting-edge / ever-evolving" are
all replaced or cut, sentence length varies, and no em-dash
was needed. The meaning survives. The AI voice does not.
