# CLAUDE.md

## Project

`marianolfunes.github.io` — Mariano's project to generate and publish his work: papers, essays, analyses, charts, ideas, tools — whatever he makes. Audience-agnostic, eclectic by intent.

**The content is the project. HTML is the medium that carries it** — chosen specifically because it can do what X / a plain text blog cannot: charts, diagrams, animation, interactive elements, custom layout.

**Three pillars + the exercise.** A piece belongs on the site if it carries all three together: **(1) visualization** (HTML affordances readers can't get on X), **(2) data** (hard numbers, real investigation, verified specifics), and **(3) insight** (Mariano's operator thinking, his domain depth, his argument). Plus: **the site is Mariano's thinking exercise.** The act of writing the prose, investigating the data, designing the visualization IS the value — not just the published output. AI-drafted articles violate the exercise dimension entirely. If a piece is pure prose with no visualization, or pure visualization without real data and insight, it doesn't belong on the site. The medium serves the content; never the other way around.

Reference pattern for HOW to render content well (not WHAT to make): Thariq Shihipar's HTML-effectiveness piece (`https://thariqs.github.io/html-effectiveness/`) and his site (`https://www.thariq.io/?mode=professional`).

Hosted on GitHub Pages as a user-site (`https://marianolfunes.github.io`). Local-first workflow: work in this folder, push when a piece is ready to be public.

## Operating principles

1. **Content drives the medium.** Every decision about HTML, CSS, structure, layout serves the piece of content being made. If a chart needs interactivity, render it interactive; if a paper needs static diagrams, keep them static. Never start from "let's make a cool HTML thing" — start from "what is Mariano trying to say."

2. **Authoring loop = conversation → piece.** Mariano brings the substance in conversation; you render and structure it. The piece exists or it doesn't. Distribution (X, LinkedIn, peers, email) is downstream and out of scope for the creation step itself.

3. **One piece = one self-contained file.** Each piece is one `.html` with embedded CSS, inline SVG for diagrams, and embedded JS when interactivity is needed. No build pipeline, no framework, no SSG at this stage — plain HTML opens in any browser on double-click. Adopt a framework only when shared-layout cost across pieces makes the build step pay for itself.

4. **Catalog homepage, not chronological feed.** `index.html` is a grid/catalog of pieces by tag and type, not a reverse-chronological blog. Each piece is atomically shareable (one URL per thing). Pieces don't decay because newer ones get added.

5. **Visual identity grows from real pieces.** Develop a small design-system HTML file (shared CSS variables, typography, color palette) once there are ~3-5 pieces to harmonize. Until then, keep each piece self-styled — no premature abstraction.

6. **Communication style.** Terse, sequential, abstract by default. Two modes — exploring vs directing. No closing push. Direct answers for verification questions; multi-option `(a)/(b)/(c)` format only for substantive decisions that change what gets built. Full doctrine in memory (`feedback_communication_style.md`, `feedback_options_explanation.md`).

7. **Disciplined execution.** Two modes: design (research, alternatives, decide together) and implementation (one step, one review, one approval). When a gap appears mid-implementation, stop and return to design.

8. **Simplify by default.** Complexity earned by current evidence, never anticipated. The piece you're writing today does not need to anticipate the piece you might write next month.

9. **Iterative build; vanilla first, evolve over time.** The site does not need to be fully defined at the start. Start with whatever is minimal and clear. First visualizations may live inside articles before the homepage gets its visualization layer. Let patterns emerge from real pieces; let the homepage evolve as those patterns harden. Don't block on perfection at v0. Don't try to ship the v1.0 of every section simultaneously.

## Hard rules

- **Never commit without explicit approval.** `git commit` requires per-commit approval. Push to origin follows commit approval (no separate ask). "Proceed with work" ≠ "proceed to commit." Doctrine in `feedback_no_commit_without_approval.md`.
- **No default defer.** Surfaced findings: fix or ditch. Defer only with named future home + captured pointer. Severity tags signal urgency, not deferral permission. Doctrine in `feedback_no_default_defer.md`.
- **Read in full before proposing delete.** For retirement/deletion work, every file in scope must be read in full before disposition; grep-based audits are insufficient. Doctrine in `feedback_read_before_delete.md`.
- **Mariano writes article prose; Claude helps correct.** Articles on the site are in Mariano's voice. Claude does NOT draft full articles in pseudo-operator-voice. Claude's value-add on articles is the visualization layer (charts, diagrams, animation), hard data presentation, structure scaffolds, and copy-edit/correction of Mariano's drafts. Doctrine in `feedback_article_authorship_visualization_first.md`.

## Security

- No credentials, no API keys, no private data in the repo. Anything sensitive stays out — this is a public site.
- Analytics: Cloudflare Web Analytics only (cookieless beacon, public token, on every page). No other analytics or third-party trackers.
- External links open in new tab; user-submitted content (if ever added) is treated as untrusted.

## Where things live

| What | Where |
|---|---|
| Homepage (catalog) | `index.html` |
| Pieces (one HTML file each) | `pieces/<slug>.html` |
| Design system (when needed) | `design-system.html` |
| Static assets (images, fonts) | `assets/` |
| Project doctrine | `CLAUDE.md` (this file) |
| Auto-memory store | `~/.claude/projects/-Users-marianofunes-marianolfunes-ops/memory/` (shared with `marianolfunes-ops`) |
| Claude Code home base | `~/marianolfunes-ops/` (private ops engine). This site folder is opened as an additional working directory when authoring or editing a piece. |
| Private ops engine (sibling repo) | `~/marianolfunes-ops/` → `https://github.com/marianolfunes/marianolfunes-ops` (PRIVATE) |

## Workflow

1. **Local-first.** Work in this folder. Open the generated `.html` in a browser by double-click to preview.
2. **Push when ready.** First push: `gh repo create marianolfunes.github.io --public --source=. --push`. Subsequent: standard `git add` / `git commit` / `git push`.
3. **GitHub Pages auto-deploys** within ~30 seconds after push. Verify at `https://marianolfunes.github.io`.
4. **Custom domain (optional, later).** If Mariano buys `marianolfunes.com`, point CNAME at `marianolfunes.github.io` and add a `CNAME` file to the repo.
