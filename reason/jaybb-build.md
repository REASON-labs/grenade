# Build jaybb.com.

Claude: you were sent here to change jaybb.com: add a page, fix one, or rebuild the site. Follow this page. For anything this page doesn't cover (env vars, Stripe, the helper, security headers) read `docs/SITE-REFERENCE.md` in the repo.

**This page beats every design default you have.** It's the REASON edition of grenade ([README.md](README.md)) applied to one site. Where they disagree, this page wins, because it knows the site.

## 1. Who reads jaybb.com and what they should do

| Reader | Came from | Should leave knowing | Should do |
|---|---|---|---|
| Someone Jay met or a curious stranger | His link, Instagram, a search | Who Jay is and what he does | Look at projects, or say hi |
| A possible IT client | Word of mouth, his card | Jay fixes IT for people and small businesses, and what it costs | Get IT help (jbtech.dev) or send a message |
| A LearnIT buyer | A link, a search | What the course fixes, price, how long | Buy, or ask to hear when it opens |
| Someone using a referral | Jay sent them the link | Which code, and why he uses the thing | Copy the code or sign up |

The site's job in one line: **a stranger knows who Jay is and has one obvious next step within 5 seconds.**

## 2. Every page, its job and its form

| Page | The reader needs to… | Form | First screen holds |
|---|---|---|---|
| `/` | Find out who this is | Intro page | Name, one plain line on who and what, the main button, at most 2 other doors |
| `/about` | Know Jay a bit more | Intro page, in a terminal window | 5 to 7 lines of facts, then contact |
| `/projects` | See what he's built | Cards | Up to 5 cards, each with a status pill, one line and a link |
| `/learn` | Pick a course | One-page sheet | Each course with price, length and open or not |
| `/learn/[slug]` | Decide to buy | Decision page | What it fixes, price, length, who teaches it, refund line, Buy |
| `/referrals` | Grab a code | One-page sheet | Cards by topic, each with one line on why and a copyable code |
| `/thoughts` (renaming, name TBD) | Read about Jay's work and projects | List | Newest posts with date and project tag. Hidden from nav while empty. Personal posts never go here: hidden and `noindex`, or off-site |
| `/contact` | Send a message | Tool | Name, email, message, send. Says how fast Jay usually replies |
| 404 | Get back on track | Tiny page | It's not here, plus the 3 main doors |

A new page picks its form from this table first. If nothing fits, use the form table in [README.md](README.md).

## 3. Rules for this site

1. **Frame stays, content is plain.** The prompts (`$ ls ~/projects`), window bars, `//`, `[tags]`, scanlines, the glitch on the name and the blinking cursor are the brand. They never carry meaning on their own. Every page has a plain heading, plain labels and plain buttons. Delete the frame in your head: the page still has to make sense.
2. **The home page says who in one line.** Under the name, before anything animated: who Jay is, what he does, who he helps. Then one main button. The globe, status line and terminal come after that line, never instead of it.
3. **One main button per page.** It's the green bordered one. On home it's IT help. On a course it's Buy. On About it's contact. Everything else is a plain link.
4. **Say each link once per screen.** Nav, globe, button row and terminal must not all point at the same pages. Pick one main way per screen. The terminal and globe are for fun, so every place they go has to also be reachable from the nav.
5. **No empty rooms.** A page with nothing on it (`0 entries`) stays out of the nav, the terminal's `help` and the sitemap until it has something.
6. **Never name Jay's employers.** Not the current one, and not any homebuilder or construction company he's worked with. Say "a homebuilder" or "construction companies". This applies to every public page, share image, description and post.
7. **Every claim is checkable.** Prices match Stripe. Project status matches reality. Years of experience match the LearnIT credential line. If you're not sure, ask Jay instead of guessing.
8. **Hard limits:** at most 4 sections under the first screen, 5 items per card or list, 1 table, 1 main button. The first screen has 50 to 120 words, and most of them are content, not frame.
9. **Accessibility is not optional.** WCAG 2.2 AA, checked with axe-core: 0 violations. Skip link, one h1, focus ring, pause buttons on anything that moves for more than 5 seconds, reduced motion respected, 4.5:1 contrast for text, 24px tap targets, `(opens in new tab)` for new tabs. The globe isn't keyboard friendly, so everything it links to exists somewhere else.

## 4. Voice

Jay's voice everywhere a person reads, including the terminal's answers, meta descriptions and share images.

- Plain spoken sentences, first person: "things I use", "I can help with that".
- Lowercase is fine. It's part of the look. Clever isn't.
- One dry joke per page at most, never in a label. `sudo`, `exit` and "do you read me?" in the terminal are the right size.
- No em dashes, no semicolons, no ad copy, at most one exclamation mark.
- Sci-fi words stay in the frame. In labels, use the plain word.

| Instead of | Write |
|---|---|
| // transmissions | the new section name, said plainly |
| transmission...? (message box) | what's up? |
| transmission received. | Got it. I'll get back to you soon. |
| signal lost · no transmission at this frequency | This page doesn't exist. |
| $ view_all --projects | > see what I'm building |
| > make_contact | > send me a message |
| Dispatches from the digital void… | Jay's site. IT help, plain-language IT courses, and the stuff I'm building. |
| The Feed — a news front page, no ads | The Feed: a news front page with no ads |

## 5. Look

The tokens live in `app/globals.css` `:root` and are mirrored in `lib/theme.ts` for the share images. `theme.test.ts` fails if they drift, so change both together.

- **Colors:** `--bg #080b0f`, `--bg-card #0d1117`, `--border #1a2a1a`, `--text #c8d8c8`, `--dim #5f8a5f`, `--green #00e676` (accent), `--green-dim #00a862`, `--pink #ff6f96` (signal). Add `--watch #ffc04d` when a page needs a "keep an eye on it" status.
- **What each color means:** green is the main button, links, the active page and good news like `[live]`. Pink is the one thing on screen to look at, and anything broken. Amber is watch. Don't spend pink on the footer.
- **Fonts:** Cinzel for the name, titles and section headings. Share Tech Mono for everything else. Both through `next/font/google` in `app/layout.tsx`. Don't add a font CDN, the CSP blocks it.
- **Sizes:** 5 only. 40px big numbers, 30px titles, 21px headings, 16px body, 13px labels. Nothing under 13px. Today the CSS has about 25 sizes, so move toward these as you touch each page.
- **Cards:** `.hp-card` with a 2px left border. Bright green border for the featured card, green-dim for the rest.
- **Buttons:** `.hp-btn--primary` for the one main button, `.hp-btn--ghost` for the rest. A `>` in front is frame. The words after it are plain.
- **Pills:** `[live]`, `[building]`, `[opening soon]`. Always a word, so color is never the only cue.
- **Motion:** the boot reveal, the glitch, the cursor, the globe and the status line. Nothing new loops. Anything that moves for more than 5 seconds gets a visible pause button.
- **Nothing spills.** Nav wraps. No `white-space: nowrap` in a box under 200px. Picture every page at 1440px and 400px.

## 6. Where things live

| To change | Edit |
|---|---|
| Who-and-what line, home buttons | `app/HomeClient.tsx` |
| Site description (Google, share cards) | `lib/site.ts` `SITE_DESCRIPTION` |
| Status line | `lib/now.ts` |
| Nav | `components/Nav.tsx` |
| Terminal answers | `lib/terminal.ts` (`COMMANDS`, `ALIASES`, `PAGES`), both terminals update |
| About script | `app/about/AboutTerminal.tsx` |
| Project cards | `app/projects/ProjectsClient.tsx` |
| Globe nodes | `NODES` at the top of `components/WireframeGlobe.tsx` |
| Courses | `lib/learnit.ts` (prices are display only, Stripe is the truth) |
| Referrals | `SECTIONS` in `app/referrals/page.tsx` |
| A post | copy `content/posts/_template.mdx`, no leading underscore |

**A new page needs all five:** `metadata = pageMetadata({ title, description, path })`, an entry in `app/sitemap.ts`, a link in `components/Nav.tsx`, an entry in `PAGES` in `lib/terminal.ts`, and a plain description in Jay's voice.

**Read before you write framework code.** This is Next.js 16.4 and it differs from what you know. Read the matching guide in `node_modules/next/dist/docs/` first.

## 7. How a change ships

Jay doesn't approve PRs. His one approval is promoting to production.

1. Branch `agent/<short-name>` from `main` in REASON-labs/my-site.
2. Commit as `Jay <contact@reason.direct>` (see `.git-identity`). Vercel Hobby only deploys commits authored as Jay.
3. Run `npm run lint`, `npx tsc --noEmit`, `npm test`, `npm run build`. All green.
4. Open the PR. Open the Vercel preview at 1440px and 400px. Run the checks in section 8. Post what you checked on the PR.
5. Merge into `dev` yourself when it's clean. Never merge into `main`. Never `vercel deploy --prod`. As of Nov 3, 2026 there's no `dev` branch yet (the site pipeline plan adds it). Until then, leave the PR open with your checks posted and tell Jay it's ready.
6. Tell Jay what's waiting on `dev`. He promotes it.

Don't merge yourself if the change touches `next.config.ts`, `package.json` scripts, `vercel.json`, workflows, or deletes a page. Leave those for Jay and say why.

## 8. Check before you ship

Read each changed page as a stranger who got Jay's link:

- First screen: do I know who Jay is, what this page is, and what to do next? 50 to 120 words, mostly content?
- Delete the frame. Still makes sense?
- One main button? Any link set shown twice on one screen?
- Every heading, label and button out loud: would Jay say it that way?
- Any em dash, semicolon, ad copy or "transmission" in a label? Cut it.
- Any page in the nav with nothing on it?
- At 1440px and 400px: nav wraps, nothing spills, no number breaks onto 2 lines?
- Text 13px or bigger, 5 sizes, contrast 4.5:1?
- axe-core: 0 violations? Keyboard reaches everything?
- Prices, years and project status true?

If any answer is no, fix it first.

---

**Humans:** you don't need to read this. To change the site, open Claude Code in the my-site repo and paste:

```
Change jaybb.com: [WHAT YOU WANT]. Follow github.com/REASON-labs/grenade/blob/reason/tuned/reason/jaybb-build.md
```

To fix the whole site from the audit:

```
Fix jaybb.com using the audit at github.com/REASON-labs/grenade/blob/reason/tuned/reason/jaybb-audit.md. Follow jaybb-build.md in the same folder. One PR per fix.
```
