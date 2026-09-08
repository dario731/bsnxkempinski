# B&S LUXURY — strategic conversation deck

A standalone HTML presentation for the in-person strategic meeting. No build step, no
internet needed: fonts, photos, video and logos are all inside `assets/`.

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
| Jump to a section | the seven lines on the right edge (hover shows the name) |

The deck has 22 screens. Most slides have several **steps**: pressing → reveals the next idea on the same slide
before moving on, so you can pace each point verbally. Going back lands on the previous
slide fully revealed. `#7` in the URL opens slide 7 directly.

The deck holds indefinitely on any slide: ambient motion loops, nothing auto-advances.

## Replacing images and logos

Every visual is resolved from the `ASSETS` map at the top of the `<script>` in
`index.html`. Change a path there and the deck follows; nothing else references files.

| Key | Used on | File now |
| --- | --- | --- |
| `coverVideo` / `coverPoster` | opening and closing screens | `assets/photos/miami-hero.mp4` / `.jpg` |
| `miami` | "We are playing the long game" | `assets/photos/miami.webp` |
| `fisherIsland` | "Going after the big fish" | `assets/photos/fisher-island.webp` |
| `brickell` | "Not registration. Relationship." | `assets/photos/brickell.webp` |
| `logoBizStyle` / `logoBizStyleDark` | bottom-right on every slide, org chart | `assets/logos/bizandstyle-white.png` / `-black.png` |
| `logoRealDeal` | positioning tiles | `assets/logos/the-real-deal.png` |
| `partnerLeviate`, `partnerSunseeker`, `partnerOneWater`, `partnerClive` | "This is not concierge" | `assets/logos/…` |

Photos are graded dark in CSS (`.media__img` filter and `.media__veil`), so bright
daytime shots still read as cinematic. Landscape, at least 1920 px wide, is ideal.
Partner marks are rendered monochrome; a transparent or white-background logo works best.

The B&S LUXURY wordmark is type, not an image, per the brand kit: Cormorant Garamond
with the MIAMI tagline beneath. Edit `.wordmark` in the CSS if the kit changes.

## Review helpers

`index.html?nofx=1&full=1#12` opens slide 12 with every step revealed and motion frozen —
useful for screenshots or proofreading.
