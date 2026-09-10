# B&S LUXURY × Selected Developers — the developer experience

A standalone HTML presentation for strategic conversations with selected luxury
developers. No build step, no internet needed: fonts, photos, video and logos are all
inside `assets/`. It evolves the David Deza / Brown Harris Stevens deck: same design
system, same navigation, a different strategic conversation.

## Run it

- Double-click `index.html` (works from the file system), **or**
- `node serve.mjs` and open <http://localhost:4500> (recommended for the video).

Press **F** for full screen before you start.

## Driving the deck

| Action | Keys / gestures |
| --- | --- |
| Next step or slide | → · ↓ · Space · Enter · Page Down · click (right 80 % of the screen) · swipe left · scroll down |
| Previous | ← · ↑ · Backspace · Page Up · click (left 20 %) · swipe right · scroll up |
| First / last slide | Home / End |
| Full screen | F (or the corner icon bottom-right) |
| Slide index | I (or the menu icon top-right) |
| Jump to a chapter | the five lines on the right edge (hover shows the name) |

Pacing: every reveal delay is scaled by `SPEED` at the top of the deck's step bookkeeping (`0.6` now; `1` is the original, slower timing).

The deck has 14 screens in six chapters. Left and right arrows sit at the edges on every screen size (they fade in on hover on a desktop). Most slides have several **steps**: pressing →
reveals the next idea on the same slide before moving on, so you can pace each point
verbally. Going back lands on the previous slide fully revealed. `#7` in the URL opens
slide 7 directly. The deck holds indefinitely on any slide: ambient motion loops, nothing
auto-advances (on a phone, steps play by themselves).

## The narrative

| # | Chapter | Screens |
| --- | --- | --- |
| 01 | Who we are | Biz & Style · The ecosystem · Our objective · On the map (where we are investing: The Real Deal, building the team, digital lead technology) · Growing progressively, selecting the top (the agent ring) |
| 02 | The market | One screen: 170+ new developments, then five lines — we don't want them all · we select what we believe in · selected, not added · a limited number of projects, a deeper commitment · when we believe, we go all in |
| 03 | The engines | Two engines · Digital lead generation (the tech and the people, both in-house) · International reach (the Biz & Style world map: dotted coastlines, routes from Miami to Los Angeles, Toronto, New York, Mexico City, Santo Domingo, Panama, Bogotá, Lima, São Paulo, London, Paris, Milan, Madrid, Dubai, Singapore) · One integrated ecosystem (luxury ecosystem, lead generation, broker community, international reach around the project) |
| 04 | The partnership | Already committed (the project's own rendering: website built, campaigns running) · Skin in the game (for every $100 you commit, we put $100 of our own into pure media; the goal is sales; at the first commission your $100 comes back; then what the commitment unlocks: the ecosystem, a sales team, international exposure, lead generation and its management) |
| 05 | Next step | "We already committed. Let's explore if we can accelerate." on the project's rendering with its mark |

The money appears only in chapter 05, after the value has been established. The two
commitments are always shown as two separate pools: the developer's partnership
commitment funds the ecosystem / business-development activation; B&S Luxury's own
capital funds the dedicated digital media. No slide adds them into one budget.

## Personalising it for a developer

Everything that changes from one developer to the next lives in the `PROJECT` object at
the top of the `<script>` in `index.html`:

| Key | What it drives |
| --- | --- |
| `name`, `shortName` | cover, the integrated ecosystem, "Integrated", "Already committed", next step. `shortName` (≤ 16 characters) is used inside the circles |
| `developer`, `location` | cover, "Already committed" |
| `logo` | the project mark on "Next step" (a black-on-white file is fine; it is inverted on the dark slide) |
| `currency`, `partnership`, `match` | the two amounts on "Skin in the game" (default `100` and `100`, an illustrative unit; the counters animate to whatever you set) |
| `event` | optional invitation line on "Next step" |
| `images`, `priceRange`, `valueProposition`, `whySelected`, `commissionPct`, `exampleUnitPrice`, `contact` | reserved for optional screens not in the current sequence |

The current values are set for Kempinski Residences Miami Design District (DaGrosa Capital
Development Partners). The renderings behind "Already committed" and "Next step" are
`kempinskiTowers` and `kempinskiDusk` in `ASSETS`; the source files stay in the
`Kempinski Residences Miami Design District/` folder.

Two ways to switch developer without editing the deck:

- URL parameters for a quick run: `index.html?project=The%20Residences&developer=Acme%20Development&partnership=25K&match=25K#1`
- A small script before the deck loads: `<script>window.PROJECT_OVERRIDES = { name: '…', … }</script>` placed right before the main `<script>` in `index.html`, or copied into a per-developer HTML file that includes the deck.

All figures are illustrative and the legal line on the economic slides says so. Change the
figures, keep the line.

## Replacing images and logos

Every visual is resolved from the `ASSETS` map at the top of the `<script>`. Change a path
there and the deck follows; nothing else references files.

| Key | Used on | File now |
| --- | --- | --- |
| `coverVideo` / `coverPoster` | cover | `assets/photos/miami-hero.mp4` / `.jpg` |
| `southOfFifth` | "120+ new developments" | `assets/photos/south-of-fifth.webp` |
| `logoBns` / `logoBnsDark` | chrome, cover | `assets/logos/bns-luxury-miami-*.png` |
| `logoBizStyle` / `logoBizStyleDark` | chrome, organisation chart | `assets/logos/bizandstyle-*.png` |
| `logoRealDeal` | The Real Deal | `assets/logos/the-real-deal.png` |
| `brickell`, `miami`, `fisherIsland`, `miamiBeach`, `partner…` | not used in the current sequence; kept for the optional screens | `assets/…` |

Photos are graded dark in CSS (`.media__img` filter and `.media__veil`), so bright daytime
shots still read as cinematic. Landscape, at least 1920 px wide, is ideal. Partner marks
are black-on-white files rendered with a multiply blend on the ivory slide; a transparent
or white-background logo works best.

## Review helpers

`index.html?nofx=1&full=1#12` opens slide 12 with every step revealed and motion frozen,
counters landed — useful for screenshots or proofreading. `&step=2` instead of `full=1`
opens a specific step.

## Deploying

The repository deploys to Netlify straight from GitHub  (see : no build step,
the root is the site). Push to  and Netlify publishes; the  branch is for work in
progress. The Kempinski source folder is git-ignored; the deck reads its copies in .
