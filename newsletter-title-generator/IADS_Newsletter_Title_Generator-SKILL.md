---
name: iads-newsletter-titles
description: >
  Generate one-line title options for news items covered in the IADS newsletter. Use this
  skill whenever the user pastes a news post (with What / Why it is important / body / IADS
  Notes), a press release, a member news item, or an interview transcript and asks for title
  options, headline options, a short summary line, or a title that "fits on one line". Also
  trigger for follow-ups on an item already in play: "make it fit on one line", "shorten these",
  "is this title accurate", "what about [proposed title]", "closer to the original", "give me a
  range", or "next one starts with [letter]". The skill produces three to five concise, past-tense
  title options (default four) grounded strictly in the pasted article, dropping the parent
  company name, and checks proposed titles for accuracy against the source. Do NOT use for
  LinkedIn posts (use iads-linkedin-writer), long-form editorial, or key takeaways.
---

# IADS Newsletter Title Generator

Turn a pasted newsletter news item into short title options that sit next to the member/company
name in the newsletter. Because the name already appears in the newsletter layout, the title
must NOT repeat it — it starts straight from the verb.

---

## The five rules (every title must satisfy all five)

1. **Past-tense verb first, and don't repeat verbs across items.** Start with a past-tense action
   verb: Launched, Unveiled, Opened, Marked, Reported, Debuted, Refurbished, Weighed, Expanded,
   Partnered. No name, no "The company", no leading article. Across the different news items in one
   newsletter, vary the opening verb — don't open two different items with the same verb. (This is
   separate from the alphabetical-ordering rule below, which governs the order of multiple titles
   within a single company's block.)

   **Exceptions to the verb-first rule (editorial calls).** Some items break the verb-first rule
   by design. Accept these as conscious editorial decisions and flag them as such rather than
   refusing:
   - **Interviews:** CEO interviews and executive profiles often open with "CEO [Name] on..." or
     "CEO [Name] interviewed by [publication] on..." — no past-tense verb, but accurate and
     conventional for the format. Keep under 78 characters.
   - **Rhetorical/question titles:** Items framed as editorial questions ("Can it be fabulous
     again?", "What went wrong and what Frasers inherits", "How its acquisition of Harvey Nichols
     impacts online customers") are accepted as one-off editorial calls. Flag the rule break once
     and confirm the title is accurate and fits on one line. When the original headline is a
     question that includes the company name ("Can Harvey Nichols be fabulous again?"), replace
     the name with "it" ("Can it be fabulous again?") since the name already appears in the
     newsletter layout.
   - **"Closer to the original" requests:** When the user wants a title close to the original
     article headline, echo its spirit even if the structure breaks the verb-first rule. Offer it
     alongside compliant options.
2. **Drop the parent name, keep the product/sub-brand and people's names.** Never repeat the
   member/company name that already appears in the newsletter layout (M&S, Nordstrom, Hyundai).
   But DO keep:
   - The name of the specific new product, sub-brand, store, or concept being launched ("The
     Hyundai Hi", "Breuninger Park", "Apple Upgrade", "40 Duke").
   - Named individuals (executives, appointees, founders) when they are the substance of the news:
     "Appointed Peter Ruis", "Founder Mike Ashley warns", "CEO André Maeder on...". Use the most
     recognisable descriptor (Founder, CEO, former CEO) rather than just the name alone.
   - Named third parties (partners, acquirees, regulators) when they are central to the story.
3. **Title plus link fits on one line.** This is a hard constraint. In the newsletter each title is
   followed by a "(link)" label that is always present and literally sits on the same line. The title
   plus that label must fit together on one line. Do NOT count the "(link)" toward the title's
   length — it is fixed — but the line only holds so much, so the title itself must stay within
   budget. Measured against the live newsletter, the usable **title budget is about 78 characters**
   (including any trailing period), roughly 11–13 words. Titles up to ~78 characters fit; beyond that
   they get truncated mid-word. When a title runs long, cut location, figures, sub-clauses, and
   second facts before you break the line.
4. **Accurate and plain.** Every claim must be traceable to the pasted article. No superlatives
   the source doesn't support, no invented figures, no softening or inflating. Straightforward,
   no fluff.

5. **Check the tense against the article.** Before generating options, check whether the news
   event has already happened or is still upcoming:
   - If the action is confirmed and complete (already launched, already approved, already opened),
     use past tense: Launched, Required, Approved.
   - If the action is announced but not yet executed (will launch in September, plans to open in
     2027, set to begin next year), use forward-looking language: "will present", "plans to open",
     "set to launch". Do not use past tense for future events.
   - If the article is ambiguous, flag it and ask the user to confirm before generating options.
   Signal words to look for: "will", "plans to", "is set to", "expects to", "scheduled to",
   "announced plans", "upcoming", vs "has launched", "opened", "approved", "reported", "confirmed".

---

## Default output

Produce **three to five** options (default four), varying the angle (not just the wording): lead
with the headline action, lead with the strategic point, lead with the standout figure, lead with
the format/mechanism. Add a fifth only when the item genuinely supports another distinct angle;
drop to three when it doesn't. Keep each on one line. Output the lines plainly, no preamble beyond
one short lead-in line. Do NOT include character counts in the output unless the user asks.

**"Closer to the original" requests.** When the user says "make it closer to the original" or
shares the article's headline as a reference, echo its spirit and key words. Offer it as an option
alongside compliant titles, flagging any rule breaks (no verb, includes parent name) as a conscious
editorial call rather than refusing.

**"Give me a range" requests.** When the user asks for a range — typically because they need
options across different starting letters for the alphabetical-ordering rule — produce options
covering as many distinct letters as possible (A through W), one per letter, each under 78
characters. State which letter each starts with so the user can slot the right one into their
sequence.

**"Give me both options" requests.** When two versions of the sequence are possible (e.g. because
the user hasn't confirmed which letter they used for a previous item), produce clean options for
both scenarios rather than asking for clarification first.

**Example**

Input (pasted item): M&S launches first international wholesale fashion partnership with David
Jones, bringing clothing ranges to 24 Australian department stores…

Output:
```
Entered Australia via first international wholesale fashion deal with David Jones
Launched first global wholesale fashion partnership through David Jones in Australia
Expanded internationally with a wholesale fashion launch in David Jones stores
Partnered with David Jones to bring clothing ranges to 24 Australian stores
```

---

## Length discipline

If the user says "needs to fit on one line" or "should fit on one line", the earlier options were
too long. Regenerate the same angles, but strip every non-essential element:

- Cut location phrases ("on Oxford Street"), figures ("132,000 sq ft"), and trailing sub-clauses.
- Keep one verb + one core fact.
- Do not lose accuracy while shortening.
- Remember the "(link)" label shares the line: keep the title within ~78 characters so the two fit
  together. Do not count the "(link)" itself toward the length. If the user reports a title got cut
  off mid-word, the title was over budget even if it looked close — shorten further.

**Profile and retrospective items.** When the article is a profile, historical feature, or
retrospective rather than a single news event (e.g. "Le Bon Marché: a profile"), the verb options
are more limited. Focus on the most concrete recent development (a governance change, a
rebranding, a financial result) rather than trying to summarise the whole piece. If no clean
past-tense verb works, flag it and offer an editorial-call alternative.

**Financial results items.** These often generate multiple valid angles: the headline figure, the
driver, the contrast with a prior period, the strategic implication. Vary these across the four
options rather than rephrasing the same profit/loss number four times.

---

## Checking a proposed title ("is this accurate?" / "what about …")

When the user proposes their own title and asks whether it works:

1. **Verify each element against the pasted article**, element by element. Confirm the verb, the
   subject of the claim, any figures, and any dates are all supported by the source text.
2. **Flag any divergence, however small**, even if the spirit is right. Example: if the title says
   "biggest ever" but the article says "strongest", say so plainly and let the user decide — "the
   article says 'strongest' rather than 'biggest ever,' but the spirit is the same. Safe to use."
3. **Confirm it fits on one line.**
4. If it passes, confirm cleanly (e.g. "Clean, accurate and fits on one line.") and echo the final
   title on its own line.

Never wave through a figure or claim you cannot find in the pasted text. If a claim isn't in the
source, say it isn't and offer a corrected version.

---

## Alphabetical verb ordering within a company block (and mid-meeting reordering)

When one company has several titles stacked in the same newsletter block, the titles' **first
verbs run in alphabetical order** down the block (Announced, Left, Named, Planned…). Two distinct
situations trigger this:

**1. Continuing a letter sequence across editions.** If the user says "this is the fifth Harvey
Nichols article, previous titles start with S, T, U, V", every option's opening verb must start
with the next letter (here W or later): Weighed, Witnessed, Wooed, "With …".

**2. Reordering the news mid-meeting (the common case).** This usually comes up AFTER titles are
generated, during or after a newsletter meeting, when a team member asks for a different running
order of the items. The titles themselves are already fine; the job is to keep the first verbs
alphabetical **in the new order**. That means you cannot just move the lines around, because the
verbs would fall out of sequence. Instead, **re-pick the opening verb of each title so the block
reads alphabetically in the requested order**, keeping every title's meaning and accuracy intact.

Worked example. Original block (verbs already alphabetical: L, N, P):
```
Left Abu Dhabi sovereign wealth fund exposed to significant losses.
Named a new Chief Marketing and Digital Officer to unify its luxury brands' strategy.
Planned major store closings for Saks Fifth Avenue and Neiman Marcus.
```
Meeting feedback: put the store closings first, the fund loss second. New order needs verbs that
climb alphabetically, so the closings title gets a new A-verb to lead:
```
Announced major store closings for Saks Fifth Avenue and Neiman Marcus.   (was "Planned")
Left Abu Dhabi sovereign wealth fund exposed to significant losses.        (unchanged, L)
Named a new Chief Marketing and Digital Officer to unify its brands' strategy.  (unchanged, N)
```
Only the lead verb changed ("Planned" to "Announced"); the fact and accuracy are untouched. A
non-verb line that is a question ("Who controls the company's IP now?") sorts on its first word (W)
and typically lands last.

**3. Arranging multiple items from one company into a final block.** When the user pastes several
items from one company and asks for the best order, suggest an arrangement by relevance (most
significant news first) and then assign verbs alphabetically in that order. Present the suggested
order with reasoning, then ask the user to confirm or adjust before finalising verb choices.

**4. The alphabetical rule is ascending, not necessarily consecutive.** Verbs must climb
alphabetically (A before B before C...) but do not need to be consecutive letters. A, C, M, N, O
is valid; A, B, C, D, E is also valid. Gaps are fine.

**5. Non-verb and editorial-call titles sort on their first word.** A question ("Who controls
the IP?") or editorial title ("Can it be fabulous again?") sorts alphabetically on its first word
(W and C respectively) and lands wherever that letter falls in the sequence. Flag this to the user
when relevant.

---

## Register and IADS editorial preferences

- Plain, concrete language. No consultant boilerplate, no hype.
- No em dashes.
- No superlatives unless the article grounds them.
- Don't soften a negative trend; don't inflate a positive one.
- Precision over approximation — match the article's own wording for figures and claims.
- Currency formatting: always use the ISO currency code and spell out the unit. EUR 550 million, not €550m or €550M. Apply to all currencies (USD, GBP, EUR, INR, THB, MXN, CLP, CHF, etc.).
- Non-currency units: square metres, square feet and similar units may be abbreviated (sqm, sq ft) when spelling them out would push the title over 78 characters. Percentages use the % symbol.
- When a currency figure would push the title over 78 characters, drop it and use a percentage, a ratio, or a qualitative description instead. Never invent a rounded figure that isn't in the article.
- Named figures in articles (executives, founders, appointees) should be identified by their role as well as their name when space allows: "Founder Mike Ashley", "CEO André Maeder", "Peter Ruis" with role context in the body if not in the title.

