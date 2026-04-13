# Tour of the repo

Welcome to `mesh-alice-bio`.

This repository is a compact Semantic Flow demonstration mesh. It is intentionally small enough to inspect by hand while still carrying several distinct lifecycle and page-generation features.

## Highlights

- `alice/` shows identifier-page customization driven by `_knop/_page/page.ttl`.
- `alice/page-main/` shows a governed Markdown artifact that can back a page region.
- `bob/` shows extraction, reference handling, and an imported Markdown page source.
- `_knop/` shows that the root identifier can join the same Knop lifecycle later in the ladder instead of being treated as a bootstrap-only special case.

## What this mesh demonstrates

- mesh creation and mesh inventory history under `_mesh/`
- Knop creation and weaving for ordinary identifiers and the root identifier
- payload integration and later weaving into explicit history/state materialization
- reference-catalog support artifacts under `_knop/_references`
- identifier-page customization through `_knop/_page/page.ttl`
- artifact-backed page regions that follow governed current content
- import-boundary behavior where outside-origin Markdown is brought into a governed local artifact before page rendering follows it

## Suggested stops

- Start at [Alice](alice/) for the clearest customized identifier page.
- Visit [Bob](bob/) for the imported-content page example.
- Visit [Root Knop](./_knop/) to inspect the root-owned support surface.
- Inspect [mesh inventory history](_mesh/_inventory/_history001/) to see the carried ladder accumulate.
- Inspect [Alice page definition](alice/_knop/_page/page.ttl) and [Bob page definition](bob/_knop/_page/page.ttl) to see the page-source model directly.

## Reading the layout

- Public identifier pages live at paths like `alice/index.html`, `bob/index.html`, and `index.html`.
- Support artifacts live under `_knop/` and `_mesh/`.
- Current authored content can live in natural workspace paths such as `home.md`, `alice-page-main.md`, and `mesh-content/root-sidebar.md`.
- Woven historical states live under `_history001/_s0001/`-style paths.

This root page is meant to help a new reader orient quickly before diving into individual identifiers and support artifacts.
