# Tour of the repo

Welcome to `mesh-alice-bio`.

This repository is a compact demonstration mesh about Alice Ghostley, Bob Newhart, and Carol Burnett. It is intentionally small enough to inspect by hand while still showing how a few people, datasets, biographies, and pages can fit together.

## Highlights

- `alice/` is the clearest customized person page.
- `bob/` is a generated identifier page with a separate imported biography at `bob/bio/`.
- `carol/` adds a richer dataset and connects Carol Burnett to both Alice and Bob.
- `alice/data/` and `carol/data/` are the source datasets behind the people pages.

## What this mesh demonstrates

- local Turtle datasets for people and relationships
- imported Markdown biographies kept as governed content
- customized pages that combine authored prose with generated resource panels
- history pages that show how the mesh has changed over time

## Suggested stops

- Start at [Alice](alice/) for the clearest customized identifier page.
- Visit [Bob](bob/) for the generated identifier page, then [Bob bio](bob/bio/) for the imported-content example.
- Visit [Carol](carol/) for the richer biographical dataset.
- Visit [Root Knop](./_knop/) to inspect the root-owned support surface.
- Inspect [mesh inventory history](_mesh/_inventory/_history001/) to see how the repository changed over the ladder.

## Reading the layout

- Public identifier pages live at paths like `alice/index.html`, `bob/index.html`, and `index.html`.
- Support artifacts live under `_knop/` and `_mesh/`.
- Current authored content can live in natural workspace paths such as `home.md`, `bob/bio/bob-bio.md`, and `mesh-content/sidebar.md`.
- Woven historical states live under `_history001/_s0001/`-style paths.

This root page is meant to help a new reader orient quickly before diving into individual identifiers and support artifacts.
