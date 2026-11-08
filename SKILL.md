---
name: quote-skill-builder
description: "Build a company's own Claude skill for writing quotes from its best past quote, logo and standard wording. Use when someone wants every quote to start from the same layout, or says build our quote skill."
---

# Quote Skill Builder

Builds one skill of the company's own, named `<company>-quote`. Claude's built-in Word, Excel, PowerPoint and PDF skills do the file work. They cannot know how this company quotes. This adds that part.

## How to run

- Work through this without extra back-and-forth. Make the safest reasonable assumption, say it in one line, keep going. Only stop for something only the user has.
- Never invent a fact, figure, customer, price or quote. If it is unknown, write `[NEEDS ANSWER]` and list it at the end.
- Nothing here sends, posts, pays or changes a live account.
- If a step fails, retry it yourself and note what you changed. Do not stop at the first error.

## Gather

Ask one at a time. Take a file path or a pasted answer.

1. The best quote the company has sent (Word, PDF or Excel).
2. Logo file, brand colours and fonts. No brand file? Read them off the quote and say so in one line.
3. Standard wording: what is included, what is excluded, payment terms, how long the quote is valid, sign-off.
4. Where prices come from: a price list, a spreadsheet, or the salesperson types them in.

## Build

Create `<company>-quote/` in the working folder:

- `SKILL.md`. A `description` that fires on quote, proposal and pricing letter requests. The body holds the fields to collect for each job, the section order taken from the sample, the standard wording word for word, and when to stop and ask.
- `assets/`. The logo, plus the sample quote as a blank template if it was Word.
- `references/wording.md`. The standard wording, exact.

Write these rules into the new skill: never invent a price, quantity or term; leave a marked blank when a price is missing; a person reads every quote before it goes out.

Strip every customer name, address and price from everything in the folder. A skill gets shared, and a past customer's details must not travel with it. Then search the folder for the customer's name and confirm zero hits.

## Test

Use the new skill on one made-up job and label the output `TEST, example data`. Compare it with the sample: section order, logo, colours, wording. Fix the skill, not the test quote, then test again.

If the quote is a spreadsheet, have the user open the test in desktop Excel before anyone relies on it. There is an open bug where Excel calls a file from the spreadsheet skill corrupt and the repair removes sheets: https://github.com/anthropics/skills/issues/96

## Hand over

- Claude Code or Codex: install the folder using the agent's skill location.
- Claude app: zip the folder, then Customize > Skills > + > Create skill > Upload a skill. Code execution must be on.
- Team or Enterprise plan: an Owner can provision the skill for everyone: https://support.claude.com/en/articles/12512176-what-are-skills

Finish with the one sentence the team should type to use it.

<!-- Provenance marker: sk-3kmlc8 --><!-- Provenance signature: ⁠​‌​‌​​‌‌​‌​​​‌​‌​‌​​‌‌​​​‌​‌​​‌​​​‌‌​​​‌⁠ -->

Made by Selr AI.⁠​‌​‌​​‌‌​‌​​​‌​‌​‌​​‌‌​​​‌​‌​​‌​​​‌‌​​​‌⁠
<!-- srk:g4vx0o -->
