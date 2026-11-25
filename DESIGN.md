# DESIGN.md — Eren Akçanal portfolio

Static single-page portfolio (+ a few project pages) for GitHub Pages.
Audience: hiring managers and engineers at Zürich robotics / vision companies.
Feeling: **calm, precise, technical** — like a well-set engineering report, with the
project media doing the talking. Matches the CV (Lato, black on white, thick rules).

Reference: ewamiazga.github.io (single page, hero with availability note, dated
timeline with logos, project cards with video/GIF thumbnails). UXKIN was not
connected, so this direction is based on that reference and the CV, not on a
survey of comparable sites.

## Color
Earthy palette chosen by Eren (2026-11-25): warm beige ground + sage `#8A8E75`.
All colors are CSS variables in `assets/css/tokens.css`. Pages never use raw values.

| Token | Light | Dark | Role |
|---|---|---|---|
| `--bg` | `#F3EEE4` | `#1C1B17` | Page background (beige / warm charcoal) |
| `--surface` | `#E9E2D4` | `#2A2923` | Media placeholders, subtle panels |
| `--card` | `#FBF8F2` | `#22211C` | Project card body |
| `--border` | `#DCD3C2` | `#3A382F` | Card outlines, dividers |
| `--rule` | `#2B2A24` | `#E8E2D5` | Thick section rules |
| `--text` | `#2B2A24` | `#E8E2D5` | Body text, headings (12.4:1 / 13.4:1) |
| `--text-muted` | `#6E6A5E` | `#A39D8F` | Dates, labels, captions (4.7:1 / 6.4:1) |
| `--sage` | `#8A8E75` | `#8A8E75` | Signature color: avatar ring, status dot, decorative fills. **Not for text** (2.9:1 on beige). |
| `--sage-tint` | `#E3E4D9` | `#2E2F27` | Tag and status-pill background |
| `--on-sage-tint` | `#4A4D3B` | `#C9CCB5` | Text on sage tint |
| `--primary` | `#5C604A` | `#A9AD92` | Dark sage: primary button fill, link text (5.6:1 / 7.5:1) |
| `--on-primary` | `#F3EEE4` | `#1C1B17` | Text on primary button |
| `--accent` | `#9A5530` | `#D58B5E` | Terracotta: link underline on hover, focus ring, active nav. Small doses only. |
| `--error` | `#A3361F` | `#F08A6B` | Form errors |

Why: warm beige and sage give a calm, natural, "made by a person" feel and set the
site apart from blue/purple tech portfolios; dark sage keeps text and buttons readable;
terracotta adds one earthy warm accent. No gradients.

## Typography
- **Family:** Lato (Google Fonts) for everything — same as the CV. Weights 400, 700, 900.
  Fallback: `system-ui, -apple-system, "Segoe UI", sans-serif`.
- Numerals in dates and figures: `font-variant-numeric: tabular-nums`.

| Token | Size / line height | Weight | Use |
|---|---|---|---|
| `--fs-display` | 44 / 1.05 (32 on mobile) | 900 | Name in hero |
| `--fs-h2` | 28 / 1.15 | 900 | Section titles |
| `--fs-h3` | 20 / 1.3 | 700 | Project and timeline titles |
| `--fs-lead` | 19 / 1.55 | 400 | Hero intro |
| `--fs-body` | 17 / 1.6 | 400 | Body text (max 68ch) |
| `--fs-small` | 15 / 1.5 | 400 | Card summaries, meta |
| `--fs-label` | 13 / 1.4 | 700 | Affiliation labels, tags (sentence case) |

## Spacing & layout
- 8-based scale: `--s-1` 4, `--s-2` 8, `--s-3` 12, `--s-4` 16, `--s-5` 24, `--s-6` 32,
  `--s-7` 48, `--s-8` 64, `--s-9` 96.
- Content width `--content` 1040px; text column max 68ch. Side gutter ≥ 20px.
- Section spacing: 96px desktop, 64px mobile. Section title sits on a 3px `--rule`.
- Breakpoints: 600px (stack), 900px (two-column hero, 2-col project grid).

## Shape & depth
- Radius: `--r-sm` 4 (tags, buttons), `--r-md` 8 (cards, media), `--r-pill` 999 (status pill).
- No shadows. Depth comes from 1px `--border` and the media itself.

## Components
- **Nav:** top bar, name left, anchor links right (Projects, Experience, Education, CV).
  Sticky above 900px with `--bg` and bottom border. Active link underlined in `--accent`.
- **Hero:** photo (round, 144px) + name + one-line title + 2–3 sentence intro +
  status pill ("Open to full-time roles from March 2027 · Zürich · Swiss B permit",
  `--sage-tint` pill with `--sage` dot) + link row (Email, GitHub, LinkedIn, CV PDF).
- **Buttons:** primary = `--primary` fill, `--on-primary` text; secondary = 1px `--text` outline;
  quiet = text link with arrow. Hover: accent underline / darken; focus: 2px `--accent`
  outline, 2px offset; disabled: 40% opacity. Min height 44px.
- **Links:** `--primary` text with 1px underline in `--border`; hover underline → `--accent`.
- **Project card:** `--card` background, 1px `--border`; 16:9 media (muted looping video or GIF, `--surface` placeholder),
  affiliation label (`--fs-label`, `--text-muted`, e.g. "EPFL · CV Lab"), title (h3),
  one-line summary, tag row, links (Project page / Code / Report). Featured projects
  (top 2) span full width with media left, text right.
- **Timeline row:** date range column (140px, muted, tabular) · logo (32px, monochrome) ·
  org + location · role · 1–2 sentence description.
- **Tag:** `--fs-label`, `--sage-tint` background, `--on-sage-tint` text, `--r-sm`, no border.
- **Footer:** one line: email · GitHub · LinkedIn · "Last updated <month year>".

## Imagery & icons
- Project media are real results only (renders, masks, demo clips). 16:9, ≤ 3 MB per
  clip, MP4/WebM with poster image; GIF only if tiny.
- Company/school logos: monochrome SVG/PNG, 32px, from official sources.
- Icons: inline SVG from Lucide (1.5px stroke), 18px, `currentColor`. No emoji.

## Don'ts
No gradients, glassmorphism, gradient text, centered-everything layouts, three
identical feature cards, or stock imagery. Nothing confidential from AlpVision or ETH.
