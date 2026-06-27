---
name: humanize-text
description: Rewrite AI-generated text so it reads like a human wrote it. Use this whenever the user shares text they suspect was produced by an LLM and wants it "humanized," "de-AI'd," "made to sound natural," or stripped of "AI tells" — em-dashes, smart quotes, pictographic characters, overused vocabulary ("delve," "leverage," "navigate the landscape"), hedging, and parallel three-item lists. Also use when the user asks to clean up LLM output, remove "AI slop," pass AI-detection tools, or fix text that "sounds like ChatGPT/Claude." Do not just proofread — actively remove the patterns below.
---

# Humanize Text

The goal is text that reads like a real person wrote it in one sitting: uneven sentence lengths, specific word choices, the occasional rough edge. AI-generated prose has a recognizable surface (certain characters, certain vocabulary) and a recognizable rhythm (balanced clauses, tricolons, every paragraph the same shape). This skill addresses both.

Work in three passes, in order. Do not skip ahead — character fixes are cheap and mechanical, while rhythm rewrites need judgment and should be done last on already-cleaned text.

## Pass 1 — Character cleanup (mechanical)

Replace these characters globally. They are the clearest fingerprints of LLM output.

| Find | Replace with |
|---|---|
| `—` (em-dash, U+2014) | ` - ` or restructure into two sentences |
| `–` (en-dash, U+2013) | `-` (hyphen) or ` to ` in ranges |
| `"` `"` (curly double quotes) | `"` (straight) |
| `'` `'` (curly single quotes) | `'` (straight) |
| `…` (ellipsis, U+2026) | `...` |
| `•` `‣` `▪` (bullet glyphs in prose) | remove or convert to real list |
| Non-breaking space (U+00A0), zero-width space (U+200B), thin space (U+2009) | regular space or delete |
| Decorative emoji and pictographs (✨🚀📊💡🎯 etc.) | remove unless clearly intentional |
| Mathematical/fancy letters (𝐁𝐨𝐥𝐝, 𝘐𝘵𝘢𝘭𝘪𝘤) | regular letters |

Em-dashes deserve extra attention — they are the single most reliable AI tell. A human writer uses maybe one or two per page; AI text often has one every paragraph. When replacing, prefer restructuring over a literal hyphen substitution:

- Before: `The results were clear — the model had learned something real.`
- Good:   `The results were clear. The model had learned something real.`
- Also good: `The results were clear: the model had learned something real.`
- Weak:   `The results were clear - the model had learned something real.` (reads as AI with a find-replace applied)

## Pass 2 — Vocabulary (semi-mechanical)

Replace or remove these words and phrases. Most have plain-English equivalents; some are pure filler and should be deleted outright.

**Verbs to replace:**
- delve into → look at, examine, get into
- leverage → use
- utilize → use
- foster → build, encourage, create
- cultivate → build, grow
- harness → use, take advantage of
- unlock → enable, allow, reveal (often just delete)
- empower → let, help, allow
- embark on → start, begin
- navigate → handle, deal with, work through
- streamline → simplify, speed up

**Adjectives to replace or delete:**
- robust → strong, solid (or delete)
- seamless → smooth (or delete — usually filler)
- comprehensive → full, complete, thorough
- multifaceted → complex (or delete)
- pivotal, crucial, paramount, vital → important (or delete — these are usually hedge-inflation)
- cutting-edge, state-of-the-art → new, current, advanced
- ever-evolving, ever-changing → changing (or delete)
- transformative, groundbreaking → new, big, major

**Metaphor nouns that show up everywhere:**
- landscape (of X) → field, area, or just the noun itself
- tapestry → delete, or "mix"
- realm → area, field, world
- journey → process, path
- treasure trove → collection, set
- wealth of → lot of, many
- myriad → many
- plethora → many, a lot of

**Phrases to delete (or rewrite from scratch):**
- "It's important to note that..." → just state the thing
- "It's worth mentioning..." → just mention it
- "In today's fast-paced world..." → delete
- "In the realm of..." → "In" + noun
- "At the end of the day..." → delete
- "In conclusion" / "In summary" → delete; if the summary is needed, write it without announcing it
- "As an AI language model..." → delete, obviously
- "I hope this helps!" → delete
- "Let's dive in" / "Let's explore" → delete
- "This is a testament to..." → rewrite directly

**Hedging inflation:**
- "could potentially" → "could" or "might"
- "may possibly" → "may" or "might"
- "it is generally considered that" → "most people think" or just state it
- "some might argue" → name who, or delete

## Pass 3 — Rhythm and structure (judgment)

This is where most "de-AI'd" text still fails. The words are fixed but the cadence is still a giveaway. Look for these patterns and break them.

**The tricolon habit.** AI loves three-item lists, especially parallel ones: "clear, concise, and compelling"; "fast, reliable, and scalable." A human uses tricolons occasionally, not in every paragraph. Cut one item, change the structure, or replace with a single well-chosen word.

- Before: `The approach is fast, flexible, and effective.`
- After:  `The approach is fast and it actually works.`

**The "not X, but Y" pattern.** AI overuses rhetorical contrasts: "This isn't just a tool; it's a platform." Replace with direct assertion.

- Before: `It's not just about speed — it's about reliability.`
- After:  `Reliability matters more than speed here.`

**Uniform sentence length.** LLM prose tends toward medium sentences (15-25 words), every one about the same. Human writing varies more: a long sentence followed by a short one, a fragment, then another long one. After cleaning the vocabulary, read the output and deliberately shorten some sentences to under 8 words, lengthen others past 30, and leave at least one fragment if the context allows.

**Every paragraph the same shape.** AI paragraphs often follow: topic sentence → two supporting sentences → wrap-up. Vary this. Let some paragraphs be a single sentence. Let others run long without a tidy conclusion.

**The balanced "on one hand / on the other hand" structure.** Real writers usually have a view. If the original text hedges both sides symmetrically on a question that has a real answer, pick one and commit.

**Over-signposting.** AI announces what it's about to do: "First, let's consider...", "Now, turning to...", "To summarize...". Delete these. The structure should be clear from content, not announcements.

## What to preserve

- **Facts, numbers, names, and quotes** — do not change these, even if they sound "too clean." If a number seems wrong, flag it; do not silently edit it.
- **The author's apparent intent and argument** — humanizing is about surface and rhythm, not about changing what the text says.
- **Technical terms** — if the text is about distributed systems, "leverage" in "leverage a load balancer" might be genuinely the right word. Use judgment; replace only when the word is filler.
- **Any domain-specific conventions** — legal, medical, and academic writing have their own rhythms that can look AI-like but aren't. Ask the user about context if unsure.

## Delivery

Unless the user says otherwise, return just the rewritten text, ready to paste. No preamble, no "here is the humanized version," no summary of changes. If the user asks what was changed, then explain — but default to clean output.

If the text is long (more than ~500 words) and you made many rewrites, offer at the end: "Want me to flag the specific changes?" — but only offer, don't dump the diff unprompted.

## Example

**Input:**
```
In today's fast-paced digital landscape, it's crucial to leverage cutting-edge tools to navigate the ever-evolving challenges of remote work. This isn't just about productivity — it's about fostering a seamless, robust, and comprehensive workflow that empowers teams to thrive.
```

**Output:**
```
Remote work keeps changing, and the tools for it keep changing too. Picking the right ones matters — not just for getting more done, but for building a workflow the whole team can actually rely on.
```

Note what changed: em-dash kept once (a human might use one), tricolon gone, "leverage/navigate/foster/empower/seamless/robust/comprehensive/cutting-edge/ever-evolving" all replaced or deleted, sentence lengths varied, opening cliché cut. The meaning survived; the AI voice did not.
