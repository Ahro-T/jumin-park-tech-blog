# PROJECT KNOWLEDGE BASE

**Generated:** 2026-07-05
**Commit:** 57db186
**Branch:** main

## OVERVIEW

Single-page static technical blog for Jumin Park's Kubernetes-first AI systems engineering notes.
No framework, package manager, build step, test runner, or CI config exists in this repo.

## STRUCTURE

```text
jumin-park-tech-blog/
|-- index.html   # full page markup, navigation anchors, Korean/English content
|-- styles.css   # all layout, tokens, responsive behavior, and thumbnail artwork
|-- DESIGN.md    # authoritative visual system and interaction constraints
|-- README.md    # short project purpose and GitHub Pages URL
`-- .gitignore   # ignores QA/codegraph scratch artifacts
```

## WHERE TO LOOK

| Task | Location | Notes |
| --- | --- | --- |
| Change visible content | `index.html` | Preserve semantic `header`, `nav`, `main`, `section`, `article`, `footer` structure. |
| Change layout or visual style | `styles.css` | Keep tokenized colors/spacing in `:root`; avoid one-off inline styling. |
| Check design intent | `DESIGN.md` | Treat as source of truth before adjusting typography, spacing, motion, or surfaces. |
| Update deployment target docs | `README.md`, `index.html` | Canonical URL points to GitHub Pages. |

## CODE MAP

| Surface | Type | Location | Role |
| --- | --- | --- | --- |
| `<main id="top">` | page root | `index.html` | Main scroll target and content container. |
| `#engineering` | section | `index.html` | Recent engineering notes list. |
| `#serving` | article anchor | `index.html` | Agentic AI harness note and tag target. |
| `#research` | section/article anchor | `index.html` | SLM distillation content and nav target. |
| `#profile` | section | `index.html` | Personal profile block. |
| `.shell` | CSS layout primitive | `styles.css` | Centered max-width page container. |
| `.article-row` | CSS component | `styles.css` | Two-column article list item. |
| `.article-thumb` variants | CSS artwork | `styles.css` | Pure CSS thumbnails; no image assets. |

## CONVENTIONS

- This is plain HTML/CSS. Do not introduce a framework, bundler, package manifest, or generated asset pipeline unless explicitly requested.
- Use `DESIGN.md` as the design contract: quiet editorial technical blog, not a portfolio poster or SaaS dashboard.
- Keep content left-aligned inside the centered `1024px` shell; reading copy should stay near the documented `720px` width.
- Preserve the Korean-first font stack and natural Korean/English wrapping.
- Use CSS custom properties for shared colors and spacing.
- Keep links as links; tag rail items are text links, not fake button controls.
- Body copy should stay at `15px` or larger.
- Letter spacing stays `0`.

## ANTI-PATTERNS (THIS PROJECT)

- Do not add decorative gradients, orbs, heavy shadows, or card-heavy layouts.
- Do not convert article rows into floating cards; the design calls for bordered editorial rows.
- Do not animate decorative effects. Motion is limited to `transform`, `opacity`, and `color`.
- Do not remove `prefers-reduced-motion` handling.
- Do not treat `mailto:hello@example.com` as a verified contact address; it is a placeholder.
- Do not rely on tests or scripts that are not present in the repo.

## COMMANDS

```bash
# No declared build/dev/test/format scripts exist.
# Preview by opening index.html directly, or serve the directory with any static server.
```

## VALIDATION

- Inspect `index.html` directly in a browser after content or CSS changes.
- Check desktop and mobile widths, especially below `760px`.
- Verify navigation anchors still resolve: `#engineering`, `#research`, `#profile`, `#serving`.
- Confirm hover/focus states remain visible and blue accent usage stays limited to links, active states, and direct calls to action.

## NOTES

- The repo is intentionally minimal; extra tooling should earn its keep.
- `.qa/` and `.codegraph` are scratch/analysis artifacts and are ignored.
- No LSP/codegraph tools were available during this initialization; the map is based on direct file inspection.
