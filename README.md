# mesh-alice-bio

`mesh-alice-bio` is a small staged example repository used as a manual comparison fixture for Semantic Flow and Weave.

It is intentionally branch-oriented. Each numbered branch represents a specific scenario in the evolution from plain source RDF to a mesh-managed layout, so future CLI and API behavior can be compared against a concrete hand-built baseline.

The current scenario ladder is:

- `00-blank-slate`: repository scaffold only, before any example data or mesh structure exists.
- `01-source-only`: a plain `alice-bio.ttl` source file with ordinary RDF vocabularies and no Semantic Flow surface yet.
- `02-mesh-created`: the manual equivalent of `mesh create`, adding `_mesh/_meta` and `_mesh/_inventory` as working support artifacts.
- `03-mesh-created-woven`: the result of weaving `02`, with explicit histories for the mesh support artifacts and initial generated pages.
- `04-alice-knop-created`: the first non-payload Knop, introducing `alice/_knop/_meta` and `alice/_knop/_inventory`.
- `05-alice-knop-created-woven`: the result of weaving `04`, including versioned Alice Knop support artifacts and the first public `alice/index.html`.
- `06-alice-bio-integrated`: the manual equivalent of integrating the root `alice-bio.ttl` file as the payload artifact for `alice/bio`, while keeping the working payload bytes at the repo root.
- `07-alice-bio-integrated-woven`: the result of weaving `06`, including payload history for `alice/bio`, advanced `alice/bio` Knop support histories, and generated pages for the integrated payload surface.
- `08-alice-bio-referenced`: add a Knop-owned `ReferenceCatalog` for `alice` with one canonical `ReferenceLink` about `alice` that targets `alice/bio`.
- `09-alice-bio-referenced-woven`: the result of weaving `08`, versioning the new `ReferenceCatalog` and advancing `alice/_knop/_inventory` without widening mesh inventory.
- `10-alice-bio-updated`: update the working `alice-bio.ttl` payload to use mesh-root IRIs, assert `alice/bio` authorship, and describe Bob locally.
- `11-alice-bio-v2-woven`: the result of weaving `10`, creating a second payload state for `alice/bio`, advancing `alice/bio/_knop/_inventory`, and regenerating the key public pages.
- `12-bob-extracted`: create Bob's minimal Knop-managed surface from the local Bob reference, including `bob/_knop/_meta`, `bob/_knop/_inventory`, and an inventory `sfc:ExtractionSource` pinned to `alice/bio`, but without splitting the payload or generating pages yet.
- `13-bob-extracted-woven`: the result of weaving `12`, versioning Bob's support artifacts, generating the Bob-facing pages, and advancing mesh inventory because Bob now has public woven surface pages.

How to read the ladder:

- Non-woven branches show the direct working-state result of a semantic operation such as `mesh create`, `knop create`, `integrate`, `knop.addReference`, or `extract`.
- `*-woven` branches show the result of materializing that working state through versioning, validation, and page generation.
- In woven branches, the relevant working Turtle files are expected to match their latest historical-state snapshots exactly.

Branches named `*-woven` represent the result of running `weave` over the immediately preceding branch state. In this fixture, `weave` means `version`, `validate`, and `generate`; it does not perform `integrate`.

The example is meant to support:

- manual filesystem inspection
- ontology discussion
- API and CLI comparison
- future documentation examples

The intended comparison standard is:

- same filesystem layout
- canonically equivalent RDF graphs
- explicit exclusion of volatile `created` and `updated` timestamps when comparing generated metadata
