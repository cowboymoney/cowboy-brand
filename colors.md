# Brand: colors

The colors cowboy uses, as the app's Tailwind theme defines them. The source
of truth is cowboy-agent's `app/palette.css`: if this page and that
file disagree, the file wins, so fix this page. When the palette changes,
update this page in the same PR. The approved boards are the **02 Color** and
**04 Components** boards of the Cowboy Design System canvas (linked from
[README.md](README.md)).

Red is not a brand color: the brand is not a P&L. Coral (and coral ink as
text) may mark a loss or an alert, and nothing else.

## The brand palette

Four brand colors. In the app each one is a Tailwind utility
(`bg-brand-cream`, `text-brand-ground`, ...) and a CSS variable
(`var(--color-brand-cream)`).

| Name | Hex | Tailwind | Job |
| --- | --- | --- | --- |
| Ground | `#252322` | `brand-ground` | The stage: the landing page's flat dark brown. The page in dark mode; text and the primary button in light mode |
| Cream | `#EFE9DF` | `brand-cream` | Text and the logo on the ground; cards and panels in light mode |
| Paper | `#F8F5F1` | `brand-paper` | The page in light mode. Cream cards sit on it |
| Cobalt | `#2B3F91` | `brand-cobalt` | The one accent: the brand's single color (avatars, links, chart slot 2). Not a button fill: buttons are ink |
| Cobalt bright | `#6F86FF` | `brand-cobalt-bright` | Cobalt on the dark ground, where the base is 1.7:1: links, chart series |

Plain white (`#FFFFFF`) and black (`#000000`) are also in the theme, for
mixing and for the rare spot that needs them.

### Surfaces and text: blends, not brand colors

Every other neutral is mixed from the brand colors in `palette.css` with
`color-mix()`. They have no brand token: use the semantic utility.

| Name on the boards | Hex | Recipe | Utility |
| --- | --- | --- | --- |
| Hide | `#312F2D` | Ground 93% · Cream | `bg-card` in dark mode |
| Dust | `#ACA8A1` | Cream 70% · Ground | `text-muted-foreground` in dark mode |
| Muted ink | `#6A6763` | Ground 62% · Cream | `text-muted-foreground` in light mode |
| Line | `#CFCAC1` | Ground 14% · Cream | `border-border` in light mode |

The light blends are mixed into cream, the darker of the two light surfaces,
so they pass on cream cards and, with room to spare, on the paper page
(muted ink is 4.7:1 on cream, 5.2:1 on paper).

## High Noon: status

The same five colors in both modes, bright on purpose.

| Name | Hex | Tailwind | Job |
| --- | --- | --- | --- |
| Mint | `#46D98A` | `brand-mint` | Success, found money, "buy" |
| Marigold | `#FFB020` | `brand-marigold` | Warnings and deadlines |
| Coral | `#FF6A4D` | `brand-coral` | Attention and destructive actions |
| Sky | `#4F8CFF` | `brand-sky` | Information |
| Aqua | `#38C6C0` | `brand-aqua` | The sixth chart series, the odd accent |
| Coral ink | `#C22F14` | `brand-coral-ink` | Coral deepened to read as text: error copy and the destructive button in light mode |

### How to use them ("full sun")

- **Dark mode:** the colors read as text and as tints on the ground.
- **Light mode:** the colors are **fills only**, at full strength, with
  ground text on top (8.6:1 on mint and on marigold). On paper, mint and
  marigold are 1.5:1, so they are never text there. The one exception is
  error copy, which uses coral ink.
- **Solid blocks are for one thing at a time:** a badge, a status pill, a
  one-line confirmation, the deadline, the move to approve. A panel with
  several lines of grey text stays a tint: solid marigold under it reads as
  an alarm, and grey on marigold fails contrast.
- **Link-preview cards** (`lib/link-preview/card.tsx`) can be a solid mint
  or marigold card with ground text, as on the Voice board.
- **Losses** read in `destructive`: coral ink as text on light, coral on
  dark. A gain stays ink.

### Color cards

One whole card in a High Noon fill with ground text: the link-preview look
inside the app (`ColorCard` in `components/ui/color-card.tsx`, the
*10 · Color cards* board).

- **The fill is the job:** mint money, marigold time, sky news, coral an
  alert, aqua research. Never chosen for looks.
- **One per screen.** It is loud because everything around it is quiet; a
  long feed may have two, never side by side. The one exception is the
  Agents page's trading week, which is a picker: every card on it is a job
  you can add, in that job's fill, on quiet day columns, so the colour says
  which job it is rather than what needs you.
- **Ground text and ink buttons, always** (4.9:1 on sky up to 8.6:1 on mint
  and marigold), and the **same fill in both modes**: unlike a chip it
  stays solid on the ground.
- **The number in the serif**, its unit at half size; flat, 18px corners,
  no border, shadow or gradient.

## The app's roles (light and dark)

The app UI is built from semantic tokens (`bg-background`, `text-foreground`,
`bg-card`, `text-muted-foreground`, `border-border`, `bg-primary`, ...) that
swap with the system's light or dark mode. Every one is a brand color or a
mix of two. The hex values are what the mixes resolve to, rounded, for
design tools that need a flat color; in code, always use the token.

| Role | Light | Dark |
| --- | --- | --- |
| Background (the page) | Paper `#F8F5F1` | Ground `#252322` |
| Foreground (text) | Ground `#252322` | Cream `#EFE9DF` |
| Card, popover | Cream `#EFE9DF` | Hide `#312F2D` (popover `#363432`) |
| Primary (buttons, the action) | Ground, with cream text | Cream, with ground text |
| Secondary, muted, accent fills | Ground at 6% on cream, `#E1DCD2` | Ground with 14% cream, `#3D3B39` |
| Muted text | Muted ink `#6A6763` | Dust `#ACA8A1` |
| Border | Line `#CFCAC1` | Cream at 14%, translucent |
| Input border | Ground at 18% on cream, `#C7C1B9` | Cream at 20%, translucent |
| Focus ring | Ground | Cream |
| Destructive (error text, the button) | Coral ink `#C22F14`, white text on the button | Coral `#FF6A4D`, ground text on the button |

### Status

| State | Fill | Chip (badge, pill, short note) | Text naming the state |
| --- | --- | --- | --- |
| Success (authorized, done) | Mint `#46D98A` | Light: solid mint. Dark: mint at 18% | Light: ground. Dark: mint |
| Info (pending) | Sky `#4F8CFF` | Light: solid sky. Dark: sky at 16% | Light: ground. Dark: sky lifted, `#84B1FF` |
| Warning (deadlines, needs attention) | Marigold `#FFB020` | Light: solid marigold. Dark: marigold at 15% | Light: ground. Dark: marigold |

In code: `bg-success-chip text-success-foreground` (with
`border-success-chip-border` when it has an edge) for a chip;
`text-on-status` for text on a solid `bg-success`, `bg-info` or `bg-warning`
in either mode. Larger panels keep a tint (`bg-warning/5`, `border-info/30`).

## Charts

Charts (the portfolio snapshot, the blend) use six series colors in a fixed
order: slot 1 is always the largest holding, and "you" in a blend.

| Slot | Light | Dark |
| --- | --- | --- |
| 1 | Ground `#252322` | Cream `#EFE9DF` |
| 2 | Cobalt `#2B3F91` | Cobalt bright `#6F86FF` |
| 3 | Mint `#46D98A` | Mint |
| 4 | Marigold `#FFB020` | Marigold |
| 5 | Coral `#FF6A4D` | Coral |
| 6 | Aqua `#38C6C0` | Aqua |

In light mode mint and marigold are under 3:1 against the page, so a light
series always carries a label or a legend. This set has not yet been run
through the colour-blind separation check the previous one passed.

## The logo's ink

The logo files carry their own ink: `#0E0E0E` on light and `#FFFFFF` on dark
(see [README.md](README.md#spec)). In the app the logo is drawn as a mask and
takes the text color, so it shows as the ground on light and the cream on
dark, which is how the design boards show it. Either way it is one solid
ink, never a High Noon color, even the mint the logo board once tried.

## In code

Never write a hex in the app. Use the Tailwind utility or the CSS variable,
and add a new color to `app/palette.css` (named for its job) only when no
existing one fits. The full rules are in cowboy-agent's `AGENTS.md` ("Colors: only from app/palette.css")
and are enforced by `npm run lint:palette`.
