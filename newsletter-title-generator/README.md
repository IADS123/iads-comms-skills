# iads-newsletter-titles

A Claude skill that generates the short, one-line titles that sit beside each news item in the IADS newsletter. Every item shows the member or company name in the layout, so the title starts with a past-tense verb and never repeats the name.

## What this is

This is a [Claude skill](https://docs.claude.com): a `IADS_Newsletter_Title_Generator-SKILL.md` file containing instructions Claude follows when the skill is triggered. Drop the folder into your skills directory (or upload `IADS_Newsletter_Title_Generator-SKILL.md` to your Claude workspace) and it activates when you paste a news item and ask for title options.

- `IADS_Newsletter_Title_Generator-SKILL.md`: the skill itself (instructions for Claude).
- `README.md`: this file.

The `iads-newsletter-titles-notion-notes.md` file, kept alongside this repo, is a plain-language walkthrough for team members and interns and is not loaded by the skill.

## What it does

Paste a full news post (the "What / Why it is important / body / IADS Notes" block) and ask for title options. You get three to five one-line options, each of which:

- Starts with a past-tense verb (Launched, Unveiled, Opened, Reported, Marked), with three accepted exceptions: CEO interview titles ("CEO [Name] on..."), rhetorical or question titles ("Can it be fabulous again?"), and "closer to the original" requests. All flagged as conscious editorial calls.
- Drops the parent company name (already shown in the layout) but keeps the new product, store, or concept name (e.g. "The Hyundai Hi"), and named individuals when they are the substance of the news (e.g. "Appointed Peter Ruis", "Founder Mike Ashley warns").
- When the original headline is a question featuring the company name ("Can Harvey Nichols be fabulous again?"), replaces the name with "it" ("Can it be fabulous again?").
- Fits on one line with the "(link)" label, which means roughly 78 characters or fewer for the title.
- Uses a different opening verb from the other items in the same newsletter.
- Says only what the article says: no invented figures, no ungrounded superlatives.
- Currency figures use the ISO code and spell out the unit: EUR 550 million, not €550m. Apply to all currencies (USD, GBP, EUR, etc.).
- Checks the tense against the article: past tense (Launched, Approved) for completed events; forward-looking language (will present, plans to open, set to launch) for announced but not yet executed events.

## Example

Input (news body):

> Marks & Spencer launches its first international wholesale fashion partnership with David Jones, bringing clothing ranges to 24 Australian department stores.

Output:

```
Entered Australia via first international wholesale fashion deal with David Jones
Launched first global wholesale fashion partnership through David Jones in Australia
Expanded internationally with a wholesale fashion launch in David Jones stores
Partnered with David Jones to bring clothing ranges to 24 Australian stores
```

## Follow-ups it handles

- **"Needs to fit on one line" / "should fit on one line"**: regenerates shorter versions. The most common request.
- **"What about: [your own title]?"**: checks a title you wrote against the article, word by word, before you publish.
- **"Is this accurate?"**: same accuracy check on a title.
- **"This is the Nth [company] article, previous titles start with S, T, U, V"**: continues an alphabetical sequence of opening verbs across editions.
- **"Reorder these / put [X] first"**: usually raised during a newsletter meeting after titles exist. When several titles sit under one company, their opening verbs run alphabetically down the block. Reordering the items means re-picking each lead verb so the block stays alphabetical in the new order, without changing what any title says. Example: "Planned major store closings" becomes "Announced major store closings" so an A-verb can lead.
- **"Give me a range"**: produces one option per letter across as many letters as possible so you can slot the right one into your alphabetical sequence.
- **"Give me both options"**: when the sequence is unconfirmed and two scenarios are possible, produces clean options for both without asking for clarification first.

## The one rule that can't bend: accuracy

These titles are reviewed and accuracy is treated as a reliability issue. Any figure, date, or superlative in a title has to be findable in the pasted article. When the skill flags a small mismatch (the article says "strongest", your title says "biggest ever"), that is a conscious call for the editor to make, not an error to ignore.

## Notes

- The ~78-character budget is specific to the current newsletter template's column width and font. If the template changes, re-measure against a title that fits perfectly with the "(link)" label visible, and update the budget in `SKILL.md`.
- The skill is for titles only. It is not for LinkedIn posts, long-form editorial, or key takeaways.
