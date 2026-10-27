# humanize
 
A Claude skill that writes or rewrites text so it reads like a person wrote it. It fixes the **structure** of a piece first and the **surface** second, and it changes how hard it pushes based on what kind of writing it is.

## Why two layers
 
Most humanizers only scrub the surface: em dashes, "delve," lists of three. That helps, but it misses the bigger tell.
 
In the StoryScope study, researchers compared 61,608 stories written by humans and five AI models. A classifier that looked only at how the stories were built (plot, time, characters, themes), and ignored word choice, still separated human from AI writing at 93.2% macro-F1. Removing the obvious stylistic tells barely changed that score. The shape of the writing gives it away.
 
Readers still notice the surface tells, though. This skill handles both.
 
## Modes
 
| Mode | Trigger | What you get |
|---|---|---|
| Write | `/humanize write a LinkedIn post about...` | A piece written with the rules applied from the first draft |
| Rewrite | Paste text and ask to humanize, de-AI, or fix it | The rewritten text, same meaning and coverage |
| Audit | "audit this" / "does this sound like AI?" | Problems quoted line by line, labeled structural or surface, plus a verdict |
| Show work | "show work" / "show changes" | Draft, remaining AI tells, final version, change summary |
 
## What it does
 
### Register check
 
Before changing anything, it decides what kind of writing it's looking at:
 
- **Stories, personal essays, blogs, social posts, scripts:** all structural rules apply, and personality is added.
- **Emails, cover letters, opinion pieces, application answers:** the rules are applied selectively. It leads with the point and avoids tangents.
- **Reports, technical docs, academic, legal, reference:** only the surface pass, at full strength. No forced opinions or "you."
### Nine structural principles
 
1. Don't state the moral
2. Name feelings plainly
3. Be specific about the world
4. Talk to the reader
5. Don't tie a bow on it
6. Let it wander a little
7. Play with time and order
8. Build tension that peaks
9. Pick the less obvious version
It also includes fingerprints for specific models (Claude, ChatGPT, Gemini, DeepSeek) to check when you know which one wrote the text.
 
### 33 surface patterns
 
The patterns fall into five groups:
 
- **Content:** inflated significance, notability name-dropping, superficial -ing clauses, promotional language, vague attributions, formulaic "challenges" sections
- **Language:** AI vocabulary, avoiding "is" and "are," "not just X, it's Y," forced lists of three, synonym cycling, false ranges, subjectless fragments
- **Style:** a hard ban on em and en dashes, overused bold, inline-header lists, title case headings, emojis, curly quotes
- **Communication:** chatbot leftovers, knowledge-cutoff disclaimers, sycophancy
- **Filler:** filler phrases, stacked hedges, upbeat conclusions, uniform hyphenation, authority tropes, signposting, fragmented headers, diff-anchored writing, staccato drama, aphorism formulas, fake-candid openers
### Detection guidance
 
- **False positives.** A list of things that don't count as AI tells on their own: polished grammar, one em dash, curly quotes, dry prose, and others.
- **Signs of human writing.** It leaves these alone, so it doesn't flatten text a real person wrote.
- **Clusters, not single tells.** Its rule of thumb is to look for groups of tells together rather than flagging any one in isolation.
### Voice calibration
 
If you give it a sample of your own writing, it studies the following and matches them:
 
- sentence length
- word choice level
- how paragraphs open
- punctuation habits
- verbal tics
- transitions
### Safeguards
 
- **Never invents facts.** If a detail would help and you didn't give it, it asks you or leaves a `[placeholder]`.
- **Keeps coverage.** A five-paragraph input comes back as roughly five paragraphs.
- **Runs a self-critique loop.** It writes a draft, asks "what still sounds AI?", then revises.
- **Runs hard checks before delivering:** no dashes, no invented details, length and register still correct.
## Installation
 
### Claude Code
 
Place the skill in your personal skills folder:
 
