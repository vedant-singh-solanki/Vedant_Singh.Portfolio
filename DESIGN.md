# DESIGN.md — Vedant Singh Solanki · Legal Portfolio

Design system for the portfolio. It's modelled on the editorial agency style in the reference video: a dark photographic hero, huge tightly tracked sans headlines, an off-white body, one accent colour, and a giant wordmark footer. It has been adapted to a formal, legal tone.

---

## 1. Principles
- **Typography does the work.** Use one photograph only (the hero portrait). Everything else is type, rules and space.
- **One accent.** Oxblood is the only colour and it is used sparingly: one word in a headline, an active state, a `+` bullet, an arrow.
- **Dark → light → dark band → light → light footer.** The rhythm alternates between charcoal and paper sections.
- **Quiet motion.** Content fades and slides in once. Nothing loops.

## 2. Colour tokens
| Token | Hex | Use |
|---|---|---|
| `--ink` | `#0E0E0F` | Nav bar, hero background, darkest text |
| `--charcoal` | `#1A1A1C` | Dark band (publications), dark card |
| `--cream` | `#E8DDCB` | Headlines on dark backgrounds |
| `--paper` | `#F7F6F3` | Page background |
| `--white` | `#FFFFFF` | Cards |
| `--text` | `#1B1B1D` | Body text on light |
| `--muted` | `#6E6E6E` | Secondary text, labels |
| `--faint` | `#B9B6B0` | "Not yet revealed" headline lines |
| `--rule` | `#E2E0DB` | Hairline dividers |
| `--oxblood` | `#7A1F2B` | Accent on light |
| `--oxblood-lit` | `#B23A48` | Accent on dark |

## 3. Typography
- **Family:** `Plus Jakarta Sans` (400, 500, 600, 700, 800) for everything.
- **Signature:** `Mrs Saint Delafield`, used once in the About card.

| Role | Size | Weight | Tracking | Case |
|---|---|---|---|---|
| Display (hero, statements) | `clamp(3rem, 9vw, 8.5rem)` | 800 | -0.045em | UPPER |
| Footer wordmark | `clamp(4rem, 19vw, 17rem)` | 800 | -0.05em | UPPER |
| H2 section statement | `clamp(1.8rem, 3.6vw, 2.9rem)` | 600 | -0.035em | Sentence |
| H3 card title | `clamp(1.6rem, 2.6vw, 2.4rem)` | 700 | -0.03em | Title |
| Body | `1.0625rem / 1.6` | 400 | -0.01em | Sentence |
| Label | `0.75rem` | 600 | 0.08em | UPPER |
| Wordmark (nav) | `0.95rem` | 600 | 0.35em | UPPER |

Display line-height is `0.92`. Lines that stack touch each other.

## 4. Motifs
- **§ section mark.** This is the brand glyph in oxblood. It replaces the reference's asterisk logo and appears next to the wordmark, in section labels and in the footer.
- **Ruled headlines.** Each line of a statement headline sits on a 1px `--rule` line. Lines are indented in a staircase.
- **Grid overlay.** The hero carries a faint 64px grid (white at 6% opacity).
- **Vertical micro-text.** Small rotated text on the hero's right edge.
- **`+` bullets.** Lists use an oxblood `+` instead of a dot.
- **Arrow link.** Text, then a 40px hairline that ends in an arrowhead, in oxblood. The line grows on hover.
- **Pill button.** 1px border, fully rounded, with text and an arrow.
- **Tag dot.** A small two-tone dot (oxblood + cream) in front of eyebrow tags.

## 5. Layout
- Max content width is `1240px`, with gutters of `clamp(16px, 5vw, 64px)`.
- **Nav:** sticky, `--ink` background, 56px tall. Wordmark on the left, links on the right. On phones it collapses to a menu toggle.
- **Section padding:** `clamp(80px, 12vw, 160px)` vertical.
- **Cards:** white, `border-radius: 14px`, no shadow, with a 1px `--rule` border on paper.
- **Stats:** numbers sit in a left column with a 1px rule on their left edge. Title and description sit to the right. Each stat row is separated by a rule.

## 6. Components
1. Nav bar
2. Hero: photo, gradient, grid, name block, practice column, giant headline, vertical text
3. Ruled statement headline
4. Practice-area switcher: list, big title, sub-list
5. Stat row with a rolling counter
6. Experience accordion row: date, firm, role, city, expandable bullets
7. Card trio: profile card with signature, vertical strip, dark card, light card
8. Publication slider on a dark band with quote mark and arrows
9. Credential cards with `+` lists
10. CTA block with a pill button
11. Footer: giant wordmark, tagline rule, columns, large email and phone

## 7. Motion
- **Reveal:** `opacity 0 → 1`, `translateY(28px → 0)`, 0.9s, `cubic-bezier(.2,.7,.2,1)`. Triggered once when 15% of the element is in view.
- **Statement lines:** colour goes from `--faint` to `--text` as each line enters, staggered by 120ms.
- **Counters:** count up over 1.4s with an ease-out curve.
- **Hover:** links fade to oxblood, and arrow lines grow 40px → 56px.
- With `prefers-reduced-motion: reduce`, all transitions are off and content shows immediately.

## 8. Imagery
There is exactly one photograph, `assets/vedant.jpg`. It's used as the hero background (darkened) and as the small portrait in the About card. Don't add stock imagery.
