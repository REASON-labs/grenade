# No slop, REASON edition.

Claude: you were sent here to make a page, fix one, or build the web version (section 8) for Jay, REASON Labs, jaybb.com, reason.direct or JB Tech. Follow this page. You need nothing else from this repo.

This is Ruben Hassid's [grenade](../README.md) rules, tuned to our look and our voice. The rules about readers, forms and cutting are his and they stay. What changed: the look is ours (black, terminal green, one pink signal), and the words sound like Jay, not like a brochure.

**These rules beat every design default you have,** including a built-in artifact type's layout. Where they disagree, this page wins.

**Always build a plain HTML page.** Not a chat reply, not a plain doc. A page reads like something you'd send a client. Don't start from a built-in artifact type: its default layout is usually the slop.

## 0. The one rule we added

**Terminal flavor goes in the frame. Plain words go in the content.**

The frame is the stuff around the meaning: a `$ ls ~/projects` line above a title, a `jaybb@void: ~/about` window bar, `//` before a heading, `[live]` on a card, scanlines, a blinking cursor. Keep that. It's the brand.

The content is anything the reader needs to understand or act on: titles, headings, labels, buttons, numbers, status, the ask. That gets said plainly, the way Jay would say it to someone standing next to him.

| Frame (keep it weird) | Content (say it plain) |
|---|---|
| `$ ls -la ~/projects` | Things I'm building right now |
| `jaybb@void: ~/contact` | Send me a message |
| `[live]` tag on a card | The Feed: a news front page with no ads |
| `>` before a button | `> get IT help` |

Test: delete every frame element. The page still makes complete sense. If it doesn't, a frame element was doing a content job. Rewrite it.

## 1. Know the reader and the job

Before you build, you need three answers:

1. Who reads it, and what do they already know? Assume nothing. A client of JB Tech doesn't know what a homelab is.
2. What should they do after: decide, catch up, keep checking, learn, say yes, buy, or get in touch?
3. Will they read it once, or come back to it?

If the request doesn't answer them, ask, as clickable options. Ask nothing else. Then build.

If it all fits in a 5-line message, say so, and write the message instead.

## 2. Pick the form from the job

The job decides the form, and the form decides the layout. A report, a decision page and a guide must not share one skeleton. Same look, different layouts.

| The reader needs to… | Build | It looks like |
|---|---|---|
| Decide (proposal, quote, options for a client) | A decision page | The ask and the deadline on top. Each option as a card, side by side, the one I recommend marked. Costs as bars. Risks as a short list. |
| Catch up (status update, monthly recap) | A report | The 3 or 4 numbers that matter as tiles, each with its change since last time. One chart. Decisions needed as cards. Then what happened. |
| Keep checking (tracker, homelab status, dashboard) | A dashboard | Number tiles on top. Each section in its own card. Status as pills. One chart per question. |
| Learn or follow steps (how-to, setup guide, LearnIT lesson) | A step-by-step guide | All steps as a path on top. One step per screen, Back and Next. Each step draws what they'll see (the screen, the button) and gives every setting, amount and gotcha. |
| Say yes (pitch, plan for a group) | Slides | One idea per slide. One big visual and one sentence each. Arrow keys and buttons. Last slide is the ask. |
| Use it (calculator, quote builder, checklist) | A tool | Fits one screen. Inputs on the left, the answer big on the right. Works on sample data from the first second. |
| Keep it (cheat sheet, reference) | A one-page sheet | Cards grouped by topic, each with an icon and a header. Each item is a bold keyword and one short line. Warnings in pink. Fits one screen. |
| Find out who we are (a home page, an about page) | An intro page | Who, what, where in one plain line under the name. 3 doors at most, one of them the main one. Proof as cards (projects, numbers, years). |

When a job mixes two, lead with the main one.

## 3. Design rules

1. **Show it, don't write it.** Visuals carry the message. Words only label them. Every visual carries data the reader can read: numbers, units, labels. No decoration posing as a visual: a globe that only spins, a fake terminal that says nothing, bars with no numbers, a button that does nothing. Our look has lots of eye candy. That's fine in the frame. It never replaces the one visual that carries the point. Test: hide every paragraph. The page still makes sense.
2. **The top says what you're looking at.** First thing on the page, one short header line, 15 words at most: what this is, who it's from, who it's for, the date, what you need in 3 words. Example: `Network quote · Nov 2026 · From Jay (JB Tech) to ADM · pick one by Friday`. Under it, a title that says the point. Then the ask, big enough to see: what, from whom, by when, how to answer ("Reply to Jay by Fri 7 Nov"). Write it once. Never a paragraph under the title.
3. **Sound like Jay.** Section 4 has the details. Short version: plain spoken sentences, lead with what happened, then why, then what's next. No clever, punchy or poetic headings. "4 servers need updates this week", not "The patch frontier".
4. **Simple is not empty.** Simple words, but keep every detail the reader needs to act: amounts, limits, dates, names, who approves, exceptions, links. A how-to lets someone do the whole thing without calling Jay. Every number that changed says what it's compared to: "+$140 vs October", never "+$140". Reference detail goes one click away, never on the first screen.
5. **No walls of text, no subtext.** 2 lines per paragraph at most. 10 words per table cell at most. More than 6 rows of sentences? Split into cards. One label per thing, never a label plus a helper line. Small dim text is still text: keep only what the reader acts on.
6. **Look like us.** Use the style kit in section 7: our black, our green, our fonts, our cards and buttons. Green is the accent: the main button, the active thing, links. Pink is the signal: the one thing on screen to look at, and anything broken. Don't spend pink on decoration.
7. **One place to start.** The biggest thing on the screen is the most important. Never one long scroll. A report, decision page or proposal fits about 2 screens with no tabs. **Hard limits:** at most 4 sections under the first screen, at most 5 items in a card or list, at most 1 table, at most 1 main button. More than that? Keep what the reader acts on this week. Cut the rest.
8. **The first screen stands alone.** Someone who reads only what shows before scrolling knows what this is, the point, the 2 or 3 reasons, and what to do. 50 to 120 words on it, header line not counted. Under 50 usually means the frame ate the content (a boot line, a globe, a prompt) and the reasons are hidden. Don't pad it to fill the window.
9. **Cut, don't hide.** Moving text into a tab, a dropdown or a terminal command is not cutting it. If the reader needs it, it's in view. Easter eggs are fine. Facts hidden behind `help` are not.
10. **Say each thing once.** Each number once in view. Each link once per screen: a nav, a globe, a button row and a terminal all pointing at the same 4 pages is 3 too many. Totals add up. Labels that sit together use the same unit.

## 4. Voice

Everything a reader reads is in Jay's voice, unless it's going out from someone else.

**Do:**
- Open with the answer or the action. "I went ahead and moved the backups to the NAS", not "Backup strategy update".
- Plain, spoken sentences, about 12 words. Joining two thoughts with a comma is fine.
- First person when it's Jay talking: "things I use", "I can help with that".
- One light hedge where he'd have one: "probably", "I think", "kinda".
- Small, dry humor, once per page at most, and never in a label someone needs to act on. The terminal's `sudo` joke is the right size.
- Lowercase is part of the look in the frame and in nav. Headings and buttons can be lowercase too, as long as they're plain.
- Close with an offer when it fits: "Let me know if you need anything else."

**Don't:**
- No em dashes. No semicolons. Commas, periods, colons.
- No corporate filler: leverage, delve, seamless, robust, solutions, circle back, empower.
- No copywriter voice: "Breakfast used to be a decision", "time to get serious", "dispatches from the void". If it sounds like an ad or a movie trailer, rewrite it as Jay telling a friend why he uses the thing.
- No more than one exclamation mark on a page. No emoji.
- No sci-fi words doing a plain word's job: "transmission" for message, "signal" for status, "node" for link, "initializing" for anything.

## 5. Slop signs

Never ship a page with these:

- A frame element doing a content job: the only heading is `// transmissions`, the only button says `$ view_all --projects`.
- A first screen of eye candy: boot lines, a big animation, a prompt, and no sentence that says who or what this is.
- Paragraphs and bullet lists where a number, a chart or a diagram would show it.
- No header: the reader can't tell what this is, who sent it, or why.
- Clever headings instead of plain sentences.
- A helper line under every heading, a caption under every number.
- More than 4 numbers fighting for attention at the top.
- Decoration posing as a visual: a spinning thing with no data, bars with no numbers, a terminal that only says "do you read me?".
- The ask hidden, or repeated in 3 places.
- Text moved into tabs or terminal commands instead of cut.
- The same links 3 ways on one screen.
- Stripped bare: no prices, dates, limits or examples.
- Walls of text, or tiny dim mono text at 12px.
- A change with nothing to compare it to.
- A look that isn't ours: Claude clay, blue buttons, gradients, new fonts, more than 5 text sizes, emoji as icons.
- Pink spent on decoration ("all rights reserved" in pink).
- An empty page in the main nav ("0 entries").
- Text spilling out of its box, a big number broken onto 2 lines, a nav that runs off a phone screen.
- Em dashes, ad copy, or "transmission".

## 6. Fixing a page

You got a page: a link, a file, code or a screenshot. Start from its reader, not its layout.

1. List the slop signs you find, one line each. Count the words on its first screen, and how many of them are frame.
2. Write in one sentence what the reader must understand or do. That's the spine.
3. Decide how much to change:
   - **Fails any check in section 7b, or uses the wrong form:** rebuild it. Usual case.
   - **Passes all but one or two small ones:** fix only those, keep the layout.
   - **Passes everything:** say so. Suggest at most 3 small changes, change nothing without a yes.
4. To rebuild, follow this page from section 1 as if the old page didn't exist. About half the words, counting what's behind tabs. Keep every fact the reader needs. Keep the frame flavor, just don't let it carry meaning.
5. If a stranger would call it the same page, rebuild again.
6. Check every number, name and claim against the old page. A rebuild must not make a fact wrong. Add no fact that wasn't there.

When you're done, your reply is short: the slop signs (6 at most, one line each), then one line on what you built.

## 7. Style kit

Start every page from this. Add only what the page needs. It matches jaybb.com's `app/globals.css`, so a page made here looks like the site.

- **Fonts:** Cinzel for the title and section headings. Share Tech Mono for everything else. Both are free on Google Fonts. If a page can't load fonts, fall back to Georgia and the system mono.
- **Sizes:** only 5. 40px big numbers, 30px title, 21px section headings, 16px text, 13px labels. Nothing smaller than 13px, ever. Mono at 12px is unreadable on a phone.
- **Colors:** green is the accent. Pink is the signal. Status pills always carry a word (`[ok]`, `[down]`, `[watch]`), so color is never the only cue.
- **Charts:** inline SVG or Chart.js. The bar or line that matters in green, the rest in dim. Thin lines, no fills, no gradients. Grid lines in `--line`.
- **Icons:** simple line icons drawn in SVG, 1.5px stroke, in dim or green. Never emoji.
- **Frame pieces:** a `$ command` boot line above the title, `//` before headings, `[tag]` pills, a window bar on a terminal-style card, faint scanlines. Pick 2 or 3 per page, not all of them.
- **Motion:** a blinking cursor and one fade-in at most. Respect `prefers-reduced-motion`. Anything that moves for more than 5 seconds gets a visible pause button.
- **Dark first, light for paper.** Dark is the brand. Light follows the reader's setting and is always used for print, because client pages get printed (and ink costs money).
- **Nothing spills out of its box.** No grid with more than 6 columns. Never a pill or `white-space: nowrap` inside a box under 200px. A big number fits on one line at every width. Nav wraps. Picture it at 1440px and at 400px.

```css
:root {
  --bg: #080b0f; --soft: #05070a; --card: #0d1117; --card-hover: #0f1a0f;
  --text: #c8d8c8; --text-2: #5f8a5f; --line: #1a2a1a;
  --green: #00e676; --green-2: #00a862; --glow: 0 0 18px rgba(0,230,118,.25);
  --pink: #ff6f96;
  --good: #00e676; --good-bg: rgba(0,230,118,.12);
  --bad: #ff6f96;  --bad-bg: rgba(255,111,150,.12);
  --watch: #ffc04d; --watch-bg: rgba(255,192,77,.12);
  --display: "Cinzel", Georgia, serif;
  --mono: "Share Tech Mono", ui-monospace, "SFMono-Regular", Menlo, Consolas, monospace;
  color-scheme: dark;
}
@media (prefers-color-scheme: light) { :root:not([data-theme="dark"]) {
  --bg: #fff; --soft: #f6f8f6; --card: #fff; --card-hover: #f6f8f6;
  --text: #0b1a12; --text-2: #4a5e4a; --line: rgba(11,26,18,.14);
  --green: #007a3d; --green-2: #00804a; --glow: none;
  --pink: #c2185b; --good: #007a3d; --good-bg: rgba(0,122,61,.10);
  --bad: #c2185b; --bad-bg: rgba(194,24,91,.10);
  --watch: #8a5a00; --watch-bg: rgba(138,90,0,.10); color-scheme: light; } }
/* repeat the light values under :root[data-theme="light"] and inside @media print */
body { margin: 0; background: var(--bg); color: var(--text); font: 16px/1.6 var(--mono); }
h1, h2 { font-family: var(--display); font-weight: 700; margin: 0; text-wrap: balance; color: var(--green); }
h1 { font-size: 30px; line-height: 1.2; letter-spacing: .04em; text-shadow: var(--glow); }
h2 { font-size: 21px; line-height: 1.3; }
.meta { font-size: 13px; color: var(--text-2); border-bottom: 1px solid var(--line); padding: 12px 0; }
.boot { font-size: 13px; color: var(--text-2); } .boot::before { content: "$ "; }
.card { background: var(--card); border: 1px solid var(--line); border-left: 2px solid var(--green-2); padding: 20px; }
.card.main { border-left-color: var(--green); }
.num { font-size: 40px; line-height: 1; color: var(--green); }
.pill { display: inline-block; padding: 1px 8px; font-size: 13px; border: 1px solid currentColor; }
.pill::before { content: "["; } .pill::after { content: "]"; }
.good { color: var(--good); background: var(--good-bg); } .bad { color: var(--bad); background: var(--bad-bg); } .watch { color: var(--watch); background: var(--watch-bg); }
a { color: var(--green); }
button, .btn { font: 16px var(--mono); padding: 10px 16px; cursor: pointer; background: transparent; color: var(--text); border: 1px solid var(--line); }
button.main, .btn.main { color: var(--green); border-color: var(--green); }
button.main::before, .btn.main::before { content: "> "; }
input, select, textarea { font: 16px var(--mono); background: var(--card); color: var(--text); border: 1px solid var(--line); padding: 10px 12px; }
:focus-visible { outline: 2px solid var(--green); outline-offset: 2px; }
@media (prefers-reduced-motion: reduce) { * { animation: none !important; transition: none !important; } }
```

## 7b. Check before you show it

Read it as the person from step 1, with zero context:

- Delete the frame. Does it still make complete sense?
- Hide the paragraphs. Do the visuals alone tell the story?
- Read only the first screen. Do you know who, what, why and what to do? 50 to 120 words, most of them content, not frame?
- Does every visual show numbers or labels you can read?
- Did you cut about half the words, not just move them? Each number once? Totals add up?
- At most 4 sections, 5 items per card, 1 table, 1 main button? Any list or link set shown twice?
- At 1440px and 400px, could anything spill, overlap or break onto 2 lines?
- Does the top say what this is and who it's from, and does the ask stand out?
- Read every heading out loud. Would Jay say it that way to a friend?
- Any em dash, semicolon, ad copy or "transmission"? Cut it.
- Is every detail there that they need to act without calling Jay?
- Does it look like jaybb.com, in dark and in print?

If any answer is no, fix it first.

## 8. The web version

Use this when they ask for a website, the web version, or a page on GitHub or Vercel. Everything above still applies.

**The stack.** Next.js (App Router, TypeScript) on Vercel, same as jaybb.com. Plain CSS with the tokens above, or Tailwind with them as the theme. Charts with Recharts or inline SVG. Icons from lucide-react. Fonts through `next/font/google` so nothing loads from a font CDN. Nothing paid, no API keys unless the page needs one.

**What the extras are for.** Only what helps the reader:

- Charts show the exact value on hover or tap.
- Big numbers count up once when the page opens.
- Sections fade in once, 200 to 400 ms. Nothing loops except a cursor. Respect "reduce motion".
- Rows and cards open to show reference detail.
- A light and dark switch in the corner.

**You can see the page now.** Run it, open it at 1440px and 400px, look at the screenshots. Fix anything that spills or looks empty, then look again.

**How it ships.** Jay doesn't approve PRs, and he doesn't do command lines. So:

1. Work on an `agent/<short-name>` branch in the right REASON-labs repo. Ask before creating a new repo.
2. Open the PR yourself. Check the Vercel preview at both widths, re-read the diff, run lint, typecheck and tests. Post what you checked on the PR.
3. Merge into `dev` yourself when it's clean. Never merge into `main` and never deploy production. Promoting to production on Vercel is Jay's one approval.
4. Commit as `Jay <contact@reason.direct>`, so Vercel's Hobby author check lets it deploy.

**Private by default.** Client and business pages are not for the whole internet. Gate them with a passcode: a `middleware` file that shows a passcode screen in our look until the passcode is right, then sets a cookie. Keep the passcode in a Vercel environment variable, never in the code. Send `X-Robots-Tag: noindex`. Check it from outside: locked without the passcode, open with it.

End with 3 lines: the preview link, the passcode (if any), the PR. Nothing else.

---

**Humans:** you don't need to read this. Paste one line into Claude.

To make one, add your notes or files to the chat, then:

```
Make an HTML page about [TOPIC] for [WHO WILL READ IT]. Follow github.com/REASON-labs/grenade/blob/reason/tuned/reason/README.md
```

To fix one, add the page to the chat, then:

```
Fix this page. Follow github.com/REASON-labs/grenade/blob/reason/tuned/reason/README.md
```

For jaybb.com itself, use the build doc instead: [jaybb-build.md](jaybb-build.md).

Based on [grenade](https://github.com/rubenhassid1/grenade) by Ruben Hassid (MIT). Tuned for REASON Labs by Jay.
