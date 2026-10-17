# Cowboy brand kit: logo, color and type

This is the approved design system. The boards it describes live in the
**Cowboy Design System** canvas:
<https://claude.ai/artifact/Msd7uXnP4xB9grxzTvvfV3> (01 Logo, 02 Color,
03 Type, 04 Components, 05 Voice). A second canvas, *Cowboy Color
Explorations* (<https://claude.ai/artifact/QGPd6Wr5gujUZPtuSwRQVj>), holds
the palettes that were tried and not chosen. It is history, not guidance:
build from this file, [colors.md](colors.md), [`brand.json`](brand.json), cowboy-agent's `app/palette.css` and the
Design System canvas only.
Both canvases are private to the owner until shared.

## Logo

The cowboy logo is two pieces: the **spur** (a six-point rowel with a hub)
and the **wordmark** (the spur beside "cowboy" set in Archivo). Use these
files rather than re-drawing or re-typesetting either one.

### Files

| File | Use it for |
| --- | --- |
| [logo/cowboy-wordmark-black.svg](logo/cowboy-wordmark-black.svg) | The wordmark on a light ground, transparent background |
| [logo/cowboy-wordmark-white.svg](logo/cowboy-wordmark-white.svg) | The wordmark on a dark ground, transparent background |
| [logo/cowboy-wordmark-white-on-black.svg](logo/cowboy-wordmark-white-on-black.svg) | The board as designed: white on `#0E0E0E`, padding included |
| [logo/cowboy-wordmark-black-on-white.svg](logo/cowboy-wordmark-black-on-white.svg) | The same, inverted |
| [logo/cowboy-spur-black.svg](logo/cowboy-spur-black.svg) | The spur alone: avatars, app icons, favicons, a small mark |
| [logo/cowboy-spur-white.svg](logo/cowboy-spur-white.svg) | The spur alone, for dark grounds |
| [logo/png/](logo/png/) | PNG exports of all of the above (wordmarks 2400px wide, spurs 1024px) for tools that won't take SVG |
| [fonts/Archivo-900.ttf](fonts/Archivo-900.ttf) | The wordmark's face, to install for Figma, Canva, Keynote |
| [fonts/Archivo-900.woff2](fonts/Archivo-900.woff2) | The same face for a web page |

Every wordmark SVG has the letters as outlines, so it renders the same
everywhere without the font installed. Prefer SVG; reach for the PNGs only
when a tool can't take vectors.

### Spec

| | |
| --- | --- |
| Typeface | **Archivo**, weight 900 (Black). Not the separate Google family called "Archivo Black": that is a different design. In a font menu pick *Archivo* → *Black*. |
| Case | Lowercase only: `cowboy` |
| Tracking | −0.05em (`letter-spacing: -0.05em`) |
| Spur size | 1.31× the type size (220px spur beside 168px type) |
| Gap | 0.24em between spur and "cowboy" (40px at 168px) |
| Alignment | Spur centered on the row; the type sits 9px (0.054em) above center |
| Ink | `#0E0E0E` on light, `#FFFFFF` on dark. The spur is one solid color; the hub is a hole, not a second color. |

In the app the logo takes the text color, so it shows as the ground on
light and the cream on dark. It is always one ink, never a High Noon color
([colors.md](colors.md#the-logos-ink)).

Don't stretch, recolor part of, outline, add effects to, or re-space the
logo. Don't set "cowboy" in Archivo next to the spur by hand: use the file,
which has the spacing and kerning baked in.

## Icons

Brand icons are drawn the way the spur is: one ink, straight cuts and true
circle arcs, ends cut flat, on the spur's 350 × 350 grid (viewBox
`-175 -175 350 350`) so they line up with it at the same size. They are the
brand's marks; interface icons are still Lucide.

| File | Use it for |
| --- | --- |
| [icons/sun-black.svg](icons/sun-black.svg), [-white](icons/sun-white.svg) | The market open, the opening bell at 9:30 ET. Twelve tapered rays, long and short, round a core with the spur's hub (r 26) |
| [icons/moon-black.svg](icons/moon-black.svg), [-white](icons/moon-white.svg) | The market close, the closing bell at 4:00 ET. A crescent with flat-cut tips, drawn 300 tall rather than 350 so its solid mass balances the sun's open rays |

The pair is the point: use them together for open and close, not the moon
alone for "night" or the sun for "settings". Same ink rules as the logo:
`#0E0E0E` on light, `#FFFFFF` on dark, never a High Noon color, and in the
app they take the text color. They hold down to 16px.

## Color

Colors are on their own page: [colors.md](colors.md). In short: four brand
colors (Ground, Cream, Paper, Cobalt), the High Noon status set (Mint,
Marigold, Coral, Sky, Aqua) used "full sun" in light mode (solid fills,
ground text on top), every other neutral is a blend of the brand colors,
and one color card per screen for the thing worth seeing. Red is not a brand
color; coral may mark a loss or an alert.

The components themselves are in the *Cowboy Component Library* canvas
(<https://claude.ai/artifact/XuB8FthsowYN7Q4GiGA2x6>) and live in the app at
`/dev/components`; the rule for using them is in the root `AGENTS.md`.

## Type

| Role | Face | Use |
| --- | --- | --- |
| Display | Iowan Old Style, roman and italic (`font-serif`); Georgia where it isn't installed | The agent's voice: page titles, the home recap, a suggested idea, the big number on a card |
| Eyebrow and labels | Geist Mono 400, capitals, `0.08em` tracking, 12–13px, muted (`font-eyebrow` / `font-mono`) | The small line a title card opens with ("Welcome to the"), section labels |
| Heading and body | Open Runde 600 / 400 (`font-sans`) | Interface text; body 15–17px at 1.55 leading |
| Data | Geist Mono, tabular figures (`font-mono`) | Prices, dollars, tickers, times. Exact, never dressed up |
| Logo | Archivo 900 | The wordmark only, already outlined in the SVGs. Never in interface text |

The eyebrow used to be Newsreader italic; it was dropped for the mono
label, so the app loads one face fewer.

The display face used to be Instrument Serif. It is now Iowan Old Style,
Apple's system serif, which we do not license or ship: Macs and iPhones
draw it from the system, everything else falls back to Georgia. The link
preview pictures are drawn on the server, where it isn't available, so
their titles are set in Open Runde. Buying a webfont license would put
Iowan on every device and in the previews.

The heading and body face used to be Geist. It is now Open Runde
([github.com/lauridskern/open-runde](https://github.com/lauridskern/open-runde)),
Inter with rounded terminals, under the SIL Open Font License. It is
shipped with the app, so it is the same on every device and in the link
previews. Weights 400, 500, 600 and 700. Geist Mono stays for labels and
data.

## Motion

The spur has three moves in the app, all CSS keyframes in `app/globals.css`
drawn by cowboy-agent's `components/cowboy-logo.tsx`. The videos in [motion/](motion/) are
recordings of them on cream, 1080×1080 at 60fps, for decks, posts and
anyone designing next to them:

| File | Move | Where in the app |
| --- | --- | --- |
| [motion/spur-thinking.mp4](motion/spur-thinking.mp4) | The hop, recorded from the app's CSS: crouch, a coin-spin jump on the bottom point, a small second bounce, spin down to face you. 2.4s loop, shown twice | Beside "Thinking" while the agent works on a reply (`SpurLoader motion="hop"`) |
| [motion/spur-page-loader.mp4](motion/spur-page-loader.mp4) | The roll, recorded from the app's CSS: the spur turns flat in its own plane, like a wheel, at a steady speed. 1.4s per turn, shown three times | While a signed-in tab loads (`app/(app)/loading.tsx`) |
| [motion/spur-bounce.mp4](motion/spur-bounce.mp4) | The bounce as first designed: the same hop, larger and with motion blur, settling to a hold. 3.4s, plays once | The reference the hop was built from; not used in the app as a file |

Pointing at the wordmark gives the spur one coin turn (no bounce); that one
has no video. The squash in the hop is kept to 10% so the logo is never
visibly stretched.

## Characters

The bot employees on `/desk` (Scout, Chartist, Bull, Bear, Risk, Trader,
Crypto watcher, Macro reader) are 3D velvet-vinyl animal toys, one brand
color each, a small cowboy hat and one prop. The style rules, the exact
generation prompt and every character's subject line are in
[characters.md](characters.md): use it for any new character so the cast
stays one set.

## In the app

This repo is the source of truth for these files. cowboy-agent pins a commit
of it in `brand.lock.json` and copies what it serves into `public/` before
`next dev` and `next build` (`scripts/sync-brand.mjs` there):

| Served at | From |
| --- | --- |
| `/brand/cowboy-wordmark-black.svg`, `-white.svg` | `logo/cowboy-wordmark-black.svg`, `-white.svg` |
| `/brand/cowboy-mark-black.svg`, `-white.svg` | `logo/cowboy-spur-black.svg`, `-white.svg` |
| `/brand/cowboy-wordmark-letters-black.svg` | `logo/web/`: the wordmark with the spur path removed (same viewBox), so the spur can turn on its own |
| `/brand/cowboy-mark-*.png`, `/brand/cowboy-wordmark-*-on-*.webp` | `logo/web/` |
| `/brand/icons/sun.svg`, `moon.svg` | `icons/sun-black.svg`, `icons/moon-black.svg` |
| `/desk/<id>.jpg` | `characters/<id>.jpg` |

To change an asset: change it here, then bump the commit in cowboy-agent's
`brand.lock.json`. The X bot (cowboy-money/x-bot) reads `brand.json` and the
files from this repo's `main` directly, so it picks changes up at once.

Inside the app, colors come only from cowboy-agent's `app/palette.css`; the
`colors` in `brand.json` must match it, and cowboy-agent's sync fails the
build when they don't.

## Where these came from

Exported from the Claude Design file *Cowboy Spur Logo*, board
**"Lockup · Archivo"** (the spur is the board's blunt six-point rowel, path
copied unchanged). The wordmark outlines were set from Archivo at weight 900
with HarfBuzz, at the board's size, tracking and gap, and checked against the
board rendered in Chrome. The earlier files in cowboy-agent's `public/brand/` were traced
from a raster of the same design; these replace them.

## Font license

Archivo is © 2020 The Archivo Project Authors, under the SIL Open Font
License 1.1 ([fonts/OFL.txt](fonts/OFL.txt)). The files here are Google
Fonts' Latin subset pinned at weight 900. You can use, embed and share them
freely; the license must travel with the font files. The full family is at
<https://fonts.google.com/specimen/Archivo>.
