---
name: "humanize"
description: "Write or rewrite text so it reads human at both the structural and surface level. Use for /humanize, humanizing, de-AI-ing, auditing, or when text sounds AI-generated."
---

# Humanize

AI writing gives itself away at two levels.

1. **Structure (the bigger tell).** In the StoryScope study (Russell, Rajendhran, Pham, Iyyer, Wieting; University of Maryland and Google DeepMind, arXiv 2604.03136), researchers compared 61,608 stories written by humans and five AI models on the same prompts. A classifier that looked only at how stories were built (plot, time, characters, themes) and ignored word choice separated human from AI writing at 93.2% macro-F1. Editing out the obvious stylistic tells barely moved it (95.5 to 93.9). The shape of the writing is the main tell.
2. **Surface (the tell readers notice first).** Specific words, phrasings, punctuation, and formatting habits that show up far more in LLM text. These come from Wikipedia's "Signs of AI writing" page (WikiProject AI Cleanup), built from thousands of observed cases.

This skill fixes structure first and surface second, scaled to the register of the piece. The study was on fiction, so structural rules are applied fully to narrative and personal writing and selectively to everything else (see the register table).

---

## Modes

Pick the mode from the request. If unclear, default to Rewrite when text is pasted and Write when it isn't.

1. **Write.** "/humanize write a LinkedIn post about..." Build the principles in from the first draft. Never write an AI-shaped draft and patch it.
2. **Rewrite.** User pastes text and asks to humanize, de-AI, edit, or fix it. Diagnose, then rewrite. Keep meaning, facts, voice, and coverage. Change structure and surface, not substance.
3. **Audit.** User says "audit," "review," "what's wrong with this," or "does this sound like AI." List problems with the exact line each appears in, labeled structural or surface, most serious first. Say how strong the overall signal is (isolated tells vs a cluster). Rewrite only if asked.
4. **Show work.** User asks to see the process, or says "show work" / "show changes." Deliver the draft, the still-AI critique, the final version, and a change summary.

---

## Ground rules (every mode)

- **Never invent facts.** Several principles push toward specifics: numbers, names, places, tools, dates. Only use specifics the user gave or that are in the source text. If a specific would help and you don't have it, either ask (Write mode: up to 3 short questions before drafting, only if the piece depends on them) or leave a bracketed placeholder like [number of clients] or [name of the tool]. Never fill a gap with a plausible guess.
- **Preserve coverage.** A rewrite covers everything the original covers. Five paragraphs in means roughly five paragraphs out, unless the user asks for cuts. Compressing is not humanizing.
- **Preserve meaning.** Same claims, same stance, same facts. You can reorder and reframe; you can't change what the author is saying.
- **User style wins.** A writing sample, voice profile, or stated style rules override every default in this skill.
- **Don't over-edit human writing.** If the input already shows signs of a real person (see Detection), touch only clear tells.

---

## Step 1: Identify the register

The register decides which structural principles apply and whether to add personality. Plain and neutral *is* the human voice for reference and technical text.

| Register | Structural principles | Personality and direct address |
|---|---|---|
| Story, personal essay, blog, social post, script, newsletter | All nine | Yes. Opinions, asides, "you," mixed feelings |
| Email, cover letter, opinion piece, speech, application answer | 1, 2, 3, 5 (light), 7 (lead with the point), 9 | Some. Direct address is natural; no tangents or time jumps |
| Report, technical doc, academic, legal, reference, documentation | 1 (state the claim once, no moral at the end), 3 | No. Neutral, plain, first person only where the genre allows. Surface pass at full strength |

When a piece mixes registers (a work-term report with a personal reflection section), apply the matching row to each section.

---

## Step 2: Calibrate voice (if a sample is available)

If the user provides their own writing (inline, a file, or saved style rules), read it before writing and note:

- Sentence length patterns (short? long? mixed?)
- Word choice level (casual, academic, between). If they say "stuff" and "things," don't upgrade to "elements" and "components."
- How paragraphs start (jump in, or set context first)
- Punctuation habits (parentheses, semicolons, colons)
- Recurring phrases or verbal tics
- Transitions (explicit connectors, or just starting the next point)

Replace AI patterns with *their* patterns, not generic "human" ones. If they write short sentences, don't produce long ones.

With no sample, use the default voice: natural, varied rhythm, opinionated where the register allows.

---

## Step 3: Structural principles

Each comes from a measured gap in the study. The numbers show how strong the pull is; don't quote them to the user.

### 1. Don't state the moral
AI narrators spelled out the theme 77% of the time vs 52% for humans, and used dialogue as philosophical debate 59% vs 34%.

Cut the closing line that explains what it all meant ("And that's when I realized...", "The lesson here is...", "At the end of the day..."). End on the concrete moment, detail, or action. In nonfiction, make your claim clearly, once, where it belongs. Don't restate it as a summary at the end.

### 2. Name feelings plainly
AI conveyed emotion through physical sensation or weather 81% of the time vs 38%. Humans named the emotion directly 29% vs 8%. AI also overused smell imagery (82% vs 57%).

"Her chest tightened and a cold sweat crept down her neck" is the AI version of "she was scared." Say the feeling in ordinary words. Use a physical detail only when it's specific and earned.

### 3. Be specific about the world
Humans referenced specific texts, people, and authors 47% vs 24%. AI made vague allusions ("like an old fable," "as the saying goes") 72% vs 50%.

Replace gestures with names: the actual book, company, person, number, street. "A famous study found" becomes the study's name. "Some experts say" becomes who said it, or gets cut. **Specifics must come from the user or the source (see Ground rules).**

### 4. Talk to the reader
Human narrators addressed the reader 28% vs 7%, and broke the fourth wall 67% vs 39%.

Use "you," a genuine aside, a real question, or an admission that this is a post or a story, where the register allows. Short-form posts and scripts should talk to one person. This is different from fake-candid hooks ("Honestly?", "Here's the thing"), which are a surface tell (pattern 33).

### 5. Don't tie a bow on it
AI resolved stories through internal acceptance 47% vs 27%. Humans wrote morally ambivalent protagonists 59% vs 38%.

Leave some tension standing. Let a choice be questionable, an outcome mixed, the author unsure. An honest open question often reads more human than a neat takeaway. In professional writing, this means admitting real limits or tradeoffs instead of ending on a clean win.

### 6. Let it wander a little
79% of AI stories had no subplot vs 57% of human ones. Humans wove side threads into the main theme 42% vs 21%.

Add one side detail, tangent, or small observation that makes the piece feel lived in, where length allows. Keep it short and connected to the main point.

### 7. Play with time and order
Humans showed much more chronological discontinuity: flashbacks, jumps, starting in the middle. AI tells things in order and often front-loads context.

Don't open with setup. Start at the interesting moment and backfill only what's needed. In posts, emails, and cover letters, lead with the result, the ask, or the turning point.

### 8. Build tension that peaks
Claude had the flattest escalation of any model studied, the most uniform voice, the most reverent tone toward its material, and a habit of adding epilogues.

If you are Claude, watch for this in your own drafts. Make the stakes rise. Put the biggest moment near the end. Vary sentence length and energy so the voice isn't one steady hum. Cut the wrap-up paragraph after the real ending.

### 9. Pick the less obvious version
AI outputs clustered in a narrow region; human ones spread out. Given the same prompt, the human version was the most unusual of six 57.8% of the time (chance: 16.7%).

Before writing, notice the first take that comes to mind, then choose a more particular one: an unexpected entry point, a specific personal detail, a framing the author would actually hold. Don't be weird for its own sake. Be specific enough that nobody else would have written it this way.

### Model fingerprints (when the text came from another model)
If the user says which model wrote it, check for its habits too:
- **Claude:** flat escalation, uniform voice, reverent tone, epilogues (principle 8).
- **ChatGPT / GPT:** gossip and rumor driving the plot (64% vs 44 to 55% for others), twists for their own sake, curly quotes.
- **Gemini:** describes characters by appearance instead of what they want, tidiest endings with long wind-downs, defaults to bleak settings.
- **DeepSeek:** front-loads crucial context before anything moves.

---

## Step 4: Surface patterns

Rewrite these, don't just delete them. Apply all of them in every register.

### Content patterns

**1. Inflated significance and legacy.** Watch: stands/serves as, is a testament/reminder, vital/crucial/pivotal/key role or moment, underscores its importance, reflects broader, enduring/lasting, setting the stage for, marks a shift, evolving landscape, indelible mark, deeply rooted.
> Before: Established in 1989, marking a pivotal moment in the evolution of regional statistics.
> After: Established in 1989 to collect and publish regional statistics.

**2. Notability name-dropping.** Watch: cited in [list of outlets], active social media presence, leading expert.
> Before: Her views have been cited in The New York Times, BBC, and Financial Times.
> After: In a 2024 New York Times interview, she argued regulation should focus on outcomes.

**3. Superficial -ing analyses.** Watch: highlighting, underscoring, ensuring, reflecting, symbolizing, contributing to, fostering, showcasing, tacked onto the end of a sentence.
> Before: The palette resonates with the region, symbolizing bluebonnets, reflecting the community's deep connection to the land.
> After: The temple uses blue, green, and gold. The architect said they reference local bluebonnets.

**4. Promotional language.** Watch: boasts, vibrant, rich (figurative), profound, nestled, in the heart of, groundbreaking, renowned, breathtaking, must-visit, stunning, commitment to.
> Before: Nestled within the breathtaking region, it stands as a vibrant town with rich heritage.
> After: It's a town in the Gonder region, known for its weekly market.

**5. Vague attributions.** Watch: experts argue, observers have cited, industry reports, some critics, several sources.
> Before: Experts believe it plays a crucial role in the ecosystem.
> After: It supports several endemic fish species, according to a 2019 survey by [source].

**6. Formulaic "challenges and outlook" sections.** Watch: Despite its... faces several challenges, Despite these challenges, Future Outlook.
> Before: Despite these challenges, it continues to thrive as an integral part of the city's growth.
> After: Traffic increased after three IT parks opened in 2015. A drainage project began in 2022.

### Language and grammar patterns

**7. AI vocabulary.** Additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate, key (adjective), landscape (abstract), navigate (abstract), pivotal, showcase, tapestry, testament, underscore, valuable, vibrant, game-changer, unlock, elevate, "it's important to note." They cluster; one is a hint, three is a signal.

**8. Copula avoidance.** Serves as / stands as / represents / boasts / features in place of is, are, has.
> Before: Gallery 825 serves as the exhibition space. It boasts over 3,000 square feet.
> After: Gallery 825 is the exhibition space. It has 3,000 square feet.

**9. Negative parallelisms and tailing negations.** "Not only... but," "It's not just X, it's Y," and clipped fragments like "no guessing" tacked onto a sentence.
> Before: It's not merely a song, it's a statement.
> After: The heavy beat adds to the aggressive tone.
> Before: The options come from the selected item, no guessing.
> After: The options come from the selected item, so the user doesn't have to guess.

**10. Rule of three.** Ideas forced into groups of three to look complete.
> Before: Attendees can expect innovation, inspiration, and industry insights.
> After: There are talks, panels, and time to network between sessions. (Three is fine when there really are three things.)

**11. Synonym cycling.** The protagonist / the main character / the central figure / the hero for the same person. Pick one name and repeat it.

**12. False ranges.** "From X to Y" where X and Y aren't on a scale.
> Before: From the singularity of the Big Bang to the enigmatic dance of dark matter.
> After: The book covers the Big Bang, star formation, and dark matter.

**13. Passive voice and subjectless fragments.** "No configuration needed." "Results are preserved automatically." Name the actor when it makes the sentence clearer.
> After: You don't need a configuration file. The system saves results automatically.

### Style patterns

**14. Em and en dashes: hard ban.** The final text contains no em dashes or en dashes, and no spaced ` -- ` used as a dash. Replace with, in rough order: a period, a comma, a colon, parentheses, or a restructured sentence. Before delivering, scan for these characters. Any hit means the draft isn't done. (Exception: the user's own style sample uses dashes, or the dash is inside a quotation or proper name.)

**15. Boldface overuse.** Mechanical bolding of terms in prose. Remove it in prose output.

**16. Inline-header lists.** Bullets that start with a bolded label and colon, each restating the label. Turn into a sentence or a plain list.
> After: The update improves the interface, speeds up load times, and adds end-to-end encryption.

**17. Title Case Headings.** Use sentence case: "Strategic negotiations and global partnerships."

**18. Emojis** on headings or bullets. Remove.

**19. Curly quotes.** Convert to straight quotes when other tells are present.

### Communication patterns

**20. Chatbot leftovers.** I hope this helps, Of course!, Certainly!, Great question, Let me know if, Would you like me to, Here is a... Remove from content.

**21. Knowledge-cutoff disclaimers and speculative gap-filling.** "As of my last update," "While details are limited," "maintains a low profile," "likely grew up," "it is believed that." Say what isn't known, or cut the sentence. Never dress a guess as fact.

**22. Sycophantic tone.** "You're absolutely right," "excellent point." State the substance instead.

### Filler and hedging

**23. Filler phrases.** In order to → To. Due to the fact that → Because. At this point in time → Now. In the event that → If. Has the ability to → Can. It is important to note that → (cut).

**24. Excessive hedging.** "It could potentially possibly be argued that it might have some effect" → "It may affect outcomes." Keep hedges that reflect real uncertainty; cut stacked ones.

**25. Generic upbeat conclusions.** "The future looks bright." "Exciting times lie ahead." Replace with a concrete fact or end earlier.

**26. Uniform hyphenation.** Keep hyphens on compounds before a noun ("a high-quality report"); drop them after the noun ("the report is high quality").

**27. Authority tropes.** The real question is, at its core, in reality, what really matters, fundamentally, the heart of the matter. Just make the point.

**28. Signposting.** Let's dive in, let's break this down, here's what you need to know, without further ado. Start with the content.

**29. Fragmented headers.** A heading followed by a one-line paragraph that restates it ("## Performance / Speed matters."). Cut the warm-up line.

**30. Diff-anchored writing.** Docs or comments that narrate a change ("This was added to replace the old approach") instead of describing what the thing is. Fine in changelogs and migration guides only.

**31. Manufactured punchlines and staccato drama.** Every sentence written like a quotable closer, or several short fragments stacked for effect ("No aesthetic prior. No nostalgia. The old rules were gone."). One short sentence for emphasis is fine. A run of them is a tell. Vary length by letting sentences connect, not by chopping them.

**32. Aphorism formulas.** X is the language of Y, X becomes a trap, not a tool but a mirror, the currency of, the architecture of. Replace with the concrete claim.

**33. Fake-candid openers.** "Honestly?", "Look,", "Here's the thing,", "Real talk," as standalone hooks before an ordinary point. The tell is the theatrical pause-and-reveal. Mid-sentence "honestly" in casual writing is fine.

---

## Step 5: Detection guidance

### Not tells on their own (don't flag or "fix")
- Perfect grammar or consistent style. Polish isn't AI.
- Mixed casual and formal registers. Common in technical people, young writers, neurodivergent writers.
- Bland or dry prose without specific tells. Dry isn't AI.
- Formal vocabulary in general. Only the specific words in pattern 7 count.
- Letter-style greetings and sign-offs.
- A single transition word like "however" or "moreover."
- Curly quotes alone (most editors auto-curl).
- Em dashes alone in someone else's text being audited (many journalists use them). They still get removed in your own output.
- One short emphatic sentence.
- "Honestly" or "look" mid-sentence.
- Unsourced claims.
- Clean, complex formatting.
- Watched phrases inside quotations, titles, proper names, or where the phrase is being discussed.

Look for **clusters**. One em dash means nothing. Em dashes plus rule of three plus "vibrant tapestry" plus a "Conclusion" section is a confession.

### Signs of human writing (preserve these)
- Specific, odd, hard-to-fabricate detail ("the lawyer who used to work upstairs from my dentist").
- Mixed feelings and unresolved tension.
- Dated slang, memes, or in-jokes tied to a year or subculture.
- Editorial choices the writer could defend.
- Real variety in sentence length.
- Genuine asides, parentheticals, and self-corrections.
- Anything written before November 30, 2022 (ChatGPT's launch) is almost certainly human.

---

## Step 6: Draft, critique, revise

Run this loop in every Write and Rewrite. In Show work mode, the user sees it; otherwise do it silently.

1. **Draft** with the register, voice, structural principles, and surface patterns applied.
2. **Critique.** Ask: "What makes this obviously AI-generated?" List the remaining tells briefly. Check especially: a stated moral, a tidy ending, flat escalation, an epilogue, setup before the interesting part, uniform sentence rhythm, compression compared with the original.
3. **Revise** into the final version.
4. **Hard checks before delivering:**
   - No em or en dashes (search for both characters).
   - No fact, number, name, or detail that isn't in the user's input or source. Anything missing is a [placeholder].
   - Coverage and rough length match the original (Rewrite).
   - Register is still right: no forced personality in technical text, no flat neutrality in a personal post.
   - Pattern 7 words: none left unless the user's own voice uses them.

---

## Output

- **Write / Rewrite (default):** Deliver the finished text and stop. No preface, no explanation of principles, no list of changes. If you used [placeholders], add one line after the text listing what to fill in.
- **If the user asks what changed:** the two or three biggest structural changes and the main surface fixes, one line each.
- **Audit:** Problems grouped as Structural and Surface, each with the quoted line and a one-line fix, most serious first. End with a one-line verdict (isolated tells, a few clusters, or obviously AI). No rewrite unless asked.
- **Show work:** Draft, then "What still sounds AI" (short bullets), then Final, then a short change summary.

---

## Examples

### Rewrite, personal post (all structural principles)

User input, with the facts they supplied: three weeks freelancing, one client, $640 invoiced, a Notion page called "backup plan," client referred her sister.

**Before:**
> When I quit my job to freelance, my heart pounded and my palms were slick with sweat. The first month was a whirlwind of challenges and growth. I learned that success isn't about having all the answers, it's about embracing the journey. In the end, I realized that taking the leap was the best decision I ever made.

**After:**
> Three weeks into freelancing I had one client, $640 in invoices, and a Notion page titled "backup plan" that I'd opened four times. I was scared, honestly. Not of failing, more of having to explain it at Christmas. Then the client referred her sister. I still don't know if this works. But I haven't opened the backup plan since Tuesday.

What moved: the feeling is named instead of shown through sweaty palms; vague "challenges" became the user's own numbers and tool; the moral is gone; the ending stays open; it starts at the interesting moment.

Without those facts from the user, the rewrite would use placeholders: "[weeks] into freelancing I had [number] client(s) and [a concrete detail about how it felt]."

### Rewrite, technical documentation (surface pass, no personality)

**Before:**
> Let's dive into caching! At its core, our system serves as a robust, high-performance solution — ensuring seamless, scalable, and reliable data access. This function was added to replace the previous approach, which caused O(n²) performance.

**After:**
> The cache stores query results in memory so repeat requests skip the database. This function uses a hash map for O(1) lookups, avoiding the O(n²) cost of scanning every item.

What moved: signposting and authority trope cut, copula fixed, em dash and rule of three removed, diff-anchored sentence rewritten to describe current behavior. No opinions or "you" added, because the register is reference.

### Show work, travel post (coverage preserved)

**Before (excerpt):**
> I recently spent five unforgettable days in Lisbon, and let me tell you — this city completely stole my heart. Nestled along the Tagus River, Lisbon stands as a vibrant testament to Portugal's enduring spirit... Would I go back? Absolutely. ✨

**Draft:**
> I spent five days in Lisbon and I'm still a little split on it. The city is beautiful, but more tiring than I expected...

**What still sounds AI:**
- Too compressed compared with the original; texture was dropped instead of rewritten.
- "The city is beautiful, but..." explains the point too cleanly.
- The closing line is flat and generic.

**Final (excerpt):**
> I spent five days in Lisbon and still have mixed feelings about it. Beautiful, yes. Also harder on the knees than anyone warned me... I would go back, but [season] and with better shoes.

**Changes:** Removed chatbot framing, significance inflation, promotional language, the em dash, and the emoji. Kept every section of the original. Rebuilt around friction and mixed feelings, with placeholders where the original had no specifics.

---

## References
- Russell, Rajendhran, Pham, Iyyer, Wieting. StoryScope. University of Maryland and Google DeepMind. arXiv 2604.03136.
- Wikipedia: Signs of AI writing, WikiProject AI Cleanup. https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing