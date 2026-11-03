# jaybb.com audit

`Audit · 3 Nov 2026 · From Claude to Jay · pick which fixes to do first`

**jaybb.com looks great and reads badly.** The look is consistent and the accessibility work is solid. But a stranger who lands on the home page can't tell who you are or what you do, because the terminal flavor is doing all the talking.

Checked against [No slop, REASON edition](README.md). I read the live site at 1440px wide and the code in REASON-labs/my-site (main at `4b8874d`, Nov 2). I couldn't load it at phone width, so the phone findings come from the CSS.

**Who I assumed reads it:** someone who got your link and wants to know who you are, a possible IT client, and a LearnIT buyer. If that's wrong, tell me who and the ranking changes.

## The scorecard

| Rule | Home | About | Projects | Learn | Referrals | Thoughts |
|---|---|---|---|---|---|---|
| Frame vs content | fail | fail | fail | pass | pass | fail |
| First screen stands alone | fail | fail | fail | pass | pass | fail |
| One clear next step | fail | weak | fail | weak | pass | fail |
| Plain headings and labels | fail | fail | fail | pass | weak | fail |
| Every detail to act | fail | fail | fail | pass | pass | n/a |
| Voice (no em dashes, no ad copy) | weak | weak | weak | pass | fail | weak |
| Look and type sizes | weak | weak | weak | weak | weak | weak |

LearnIT is the best page on the site: price, length, who teaches it, and a buy button. The rest needs words, not more design.

## Fixes, ranked by impact

| # | Fix | Why it matters | Size |
|---|---|---|---|
| 1 | **Say who you are on the home page** | First screen has about 35 words, almost all frame, and none say who you are or what you do | Small |
| 2 | **Rewrite the site description** | Google and every share card show "Dispatches from the digital void", which matches nothing the site offers | Tiny |
| 3 | **One main button, in plain words** | 4 equal buttons, all written as commands, and none of them is "get IT help" | Small |
| 4 | **Give the About terminal real facts** | 11 lines that say nothing you can act on ("hopefully changing. moving forward.") | Small |
| 5 | **Fill out Projects** | 2 one-line cards, while you have more live work than that | Medium |
| 6 | **Hide Thoughts until there's a post** | An empty page ("0 entries") sits in the main nav | Tiny |
| 7 | **Shrink the globe or make it carry data** | Biggest thing on the first screen, carries no information, repeats the nav | Medium |
| 8 | **Make the nav wrap on phones** | 7 links in a row with no wrap, likely runs off a 400px screen | Tiny |
| 9 | **Cut to 5 text sizes, 13px minimum** | About 25 sizes in the CSS, most body text at 12 to 13.6px in mono | Medium |
| 10 | **Rewrite referral blurbs in your voice** | Em dashes and ad copy ("Breakfast used to be a decision") | Small |

## What each fix looks like

**1. Home first screen.** Keep `root@void ~ JAYBB`, the boot line and the status line. Add one plain line right under the name, then the main button. Draft (your call on what to say about work):

> I'm Jay. IT manager by day, I build self-hosted AI at home, and I help small businesses with their tech.
>
> `> get IT help`  `projects`  `contact`

That gives the first screen about 30 words that mean something, without losing the look.

**2. Site description** (`lib/site.ts`, `SITE_DESCRIPTION`). Draft: "Jay's site. IT help, plain-language IT courses, and the stuff I'm building." The about page description ("the cyberhome of jaybb — reader, hacker, artist.") has the same problem and an em dash.

**3. Buttons.** Today: `$ view_all --projects` · `> whoami` · `> github` · `> contact`. Draft: one main button `> get IT help` (to jbtech.dev or /contact), then `projects` and `contact` as plain links. GitHub can live on the Projects page, it's already there.

**4. About.** Keep the window bar and the typing effect. Swap the script for 5 to 7 lines of facts: what you do, roughly where, what you can help with, what you're building, how to reach you. One joke is fine. "do you read me?" can stay as the last line.

**5. Projects.** Each card gets a status pill (`[live]`, `[building]`), one plain line on what it does, and a link. Candidates I know of: The Feed, Echo Journal, the IT helper, LearnIT, REASON Labs. You pick which are public. Today's subtitle "running log / things i'm building" is close, just make "things I'm building right now" the heading.

**6. Thoughts.** Take it out of `components/Nav.tsx`, the terminal's `help`, and the sitemap until the first post exists. The code to bring it back is already there.

**7. Globe.** Two options. Make it smaller and put the intro line beside it on desktop. Or make the nodes carry something real, like each live project with its status, and drop the nav duplicates. Right now the nav, the globe, the button row and the terminal all go to the same pages.

**8. Phone nav.** `.nav-links` in `app/globals.css` has `display: flex` but no `flex-wrap`. Add `flex-wrap: wrap`, or cut the nav to 5 items once Thoughts is hidden.

**9. Type.** Map every `font-size` to 5 tokens: 40px numbers, 30px titles, 21px headings, 16px body, 13px labels. The status line, card bodies and terminal sit at 12 to 13.6px today.

**10. Referrals.** Same facts, your voice. Huel today: "Breakfast used to be a decision. Not a meal replacement philosophy — just one less thing to think about before 9am." Draft: "Means I don't have to think about breakfast before 9am."

## Smaller things

- **Pink is spent on decoration.** "all rights reserved" in the footer and every `[live]` tag are pink. Pink should be the one thing to look at. `[live]` is good news, so green.
- **Sci-fi words doing plain jobs.** "transmissions" (blog), "transmission...?" (message box), "transmission received." (sent), "signal lost" (404), "open a channel" (contact). Keep one or two in the frame, make the labels plain.
- **"opening soon" with no date and no way to hear.** The course page could say "Want a heads-up when it opens? Send me a message."
- **AGENTS.md lists Vercel projects that don't exist** (`my-site-dev`, `my-site-staging`), and SITE-REFERENCE.md still says `jay-bakers-projects/my-site`. The real one is `jaybb-com`.

## What already works

- **Accessibility.** Skip link, one h1 per page, focus ring, pause buttons, reduced motion, contrast all checked. Keep all of it.
- **One look everywhere.** Same palette, fonts and frame pieces on every page and on the IT helper.
- **LearnIT.** Price, time, who teaches it, refund line, and nothing for sale until you open it.
- **Referrals.** Copyable codes, honest "please use them" line, grouped by topic.
- **Plumbing.** Share images, canonical URLs, structured data, security headers, tests.

The rebuild plan for all of this, page by page, is in [jaybb-build.md](jaybb-build.md).
