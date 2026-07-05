# Jumin Park Tech Blog Design System

## 1. Atmosphere & Identity

A quiet engineering journal for LLM platform work. The site should feel like a technical blog, not a portfolio poster: spacious, precise, and readable, with the signature being a Toss-Tech-inspired category page where each entry reads as a concise engineering note.

## 2. Color

### Palette

| Role | Token | Light | Usage |
| --- | --- | --- | --- |
| Surface/primary | `--surface-primary` | `#ffffff` | Page background |
| Surface/secondary | `--surface-secondary` | `#f9fafb` | Footer, soft section backgrounds |
| Text/primary | `--text-primary` | `#191f28` | Navigation, strong labels |
| Text/heading | `--text-heading` | `#333d4b` | Page titles and article titles |
| Text/secondary | `--text-secondary` | `#6b7684` | Descriptions, metadata |
| Text/tertiary | `--text-tertiary` | `#8b95a1` | Supporting labels |
| Border/subtle | `--border-subtle` | `#e5e8eb` | Dividers and hairlines |
| Accent/primary | `--accent-primary` | `#3182f6` | Links, focus, active category |
| Accent/soft | `--accent-soft` | `#e8f3ff` | Active tag background |

### Rules

- Use blue only for links, active states, and direct calls to action.
- Keep the background white and let the article rhythm carry the page.
- Do not use decorative gradients, orbs, or heavy card shadows.

## 3. Typography

### Scale

| Level | Size | Weight | Line Height | Tracking | Usage |
| --- | --- | --- | --- | --- | --- |
| Display | `36px` | `700` | `1.35` | `0` | Category/page title |
| H1 | `30px` | `700` | `1.35` | `0` | Profile headline |
| H2 | `24px` | `700` | `1.45` | `0` | Section headers |
| H3 | `20px` | `700` | `1.45` | `0` | Article titles |
| Body/lg | `17px` | `400` | `1.7` | `0` | Lead text |
| Body | `16px` | `400` | `1.65` | `0` | Default body |
| Body/sm | `15px` | `400` | `1.6` | `0` | Metadata and summaries |
| Caption | `13px` | `600` | `1.45` | `0` | Category labels |

### Font Stack

- Primary: `"Toss Product Sans", "SF Pro KR", "Apple SD Gothic Neo", "Noto Sans KR", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`
- Mono: `"SFMono-Regular", "Consolas", "Liberation Mono", monospace`

### Rules

- Letter spacing is always `0`.
- Korean and English text must wrap naturally; avoid narrow columns that orphan particles or split technical terms.
- Body copy never goes below `15px`.

## 4. Spacing & Layout

### Base Unit

All spacing derives from a base of `4px`.

| Token | Value | Usage |
| --- | --- | --- |
| `--space-2` | `8px` | Inline gaps |
| `--space-3` | `12px` | Tight component padding |
| `--space-4` | `16px` | Compact section gaps |
| `--space-6` | `24px` | Header/footer padding |
| `--space-8` | `32px` | Article item gaps |
| `--space-10` | `40px` | Section rhythm |
| `--space-12` | `48px` | Page header rhythm |
| `--space-16` | `64px` | Major vertical sections |

### Grid

- Max content width: `1024px`
- Reading column width: `720px`
- Article row thumbnail: `160px x 96px` on desktop, full-width top media on mobile
- Breakpoints: mobile below `720px`, desktop from `960px`

### Rules

- Main page content is left-aligned inside a centered `1024px` shell.
- Article rows use a two-column list, not floating cards.
- Footer uses a soft tonal background with structured link groups.

## 5. Components

### Site Header
- **Structure**: brand link, category nav, action links.
- **Spacing**: `--space-4` horizontal nav gap, `--space-6` vertical shell.
- **States**: links change to `--accent-primary` on hover/focus.
- **Accessibility**: semantic `header` and `nav`; visible focus outline.
- **Motion**: `160ms ease-out` color transition only.

### Category Hero
- **Structure**: title, one-sentence description, compact link row.
- **Spacing**: `--space-12` top, `--space-10` bottom.
- **States**: link chips use hover/focus background.
- **Accessibility**: single page `h1`.

### Article Row
- **Structure**: native `details` row with category, title, metadata, toggle label, expanded summary, optional thumbnail.
- **Spacing**: `--space-8` gap, `--space-10` vertical padding.
- **States**: row title and thumbnail respond on hover/focus; expanded rows keep the title blue and reveal body copy below the metadata.
- **Accessibility**: use `summary` for the interactive control; keep focus visible and text contrast clear.
- **Motion**: `180ms ease-out` color and transform on thumbnail only.

### Tag Rail
- **Structure**: inline category filters.
- **Spacing**: `--space-2` gap.
- **States**: active tag uses `--accent-soft`; hover changes text to `--text-primary`.
- **Accessibility**: links remain text links, not fake buttons.

### Profile Section
- **Structure**: local profile image, name, short headline, facts list, and two concise body paragraphs.
- **Image**: `160px x 160px` desktop, `96px x 96px` mobile; `8px` radius with a subtle border.
- **Facts**: label/value rows with `104px` label column on desktop and stacked rows on mobile.
- **Accessibility**: meaningful image alt text; facts use a semantic `dl`.
- **Motion**: none.

## 6. Motion & Interaction

### Timing

| Type | Duration | Easing | Usage |
| --- | --- | --- | --- |
| Micro | `160ms` | `ease-out` | Link hover, focus |
| Standard | `180ms` | `ease-out` | Thumbnail lift |

### Rules

- Only animate `transform`, `opacity`, and `color`.
- Respect `prefers-reduced-motion`.
- No decorative animation; motion only signals links and focusable rows.

## 7. Depth & Surface

### Strategy

Borders-only with tonal backgrounds.

| Type | Value | Usage |
| --- | --- | --- |
| Subtle divider | `1px solid var(--border-subtle)` | Header, article rows |
| Soft surface | `var(--surface-secondary)` | Footer, active tag support |

No box shadows in the default surface. The page should feel editorial and technical, not like a SaaS dashboard.
