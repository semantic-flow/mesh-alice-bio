# mesh-alice-bio

`mesh-alice-bio` is a small staged example repository used as a manual comparison fixture for Semantic Flow and Weave.

It is intentionally branch-oriented. Each numbered branch represents a specific scenario in the evolution from plain source RDF to a mesh-managed layout, so future CLI and API behavior can be compared against a concrete hand-built baseline.

The current scenario ladder is:

- `00-blank-slate`: repository scaffold only
- `01-source-only`: plain source RDF with no mesh structure
- `02-mesh-created`: manual mesh creation with `_mesh` metadata and inventory
- `03-mesh-created-woven`: weave `02-mesh-created`
- `04-alice-knop-created`: manual creation of the `alice` Knop
- `05-alice-knop-created-woven`: weave `04-alice-knop-created`
- `06-alice-bio-integrated`: integration of the source artifact as the payload artifact for `alice/bio`
- `07-alice-bio-integrated-woven`: weave `06-alice-bio-integrated`
- `08-alice-bio-referenced`: add a ReferenceLink from the `alice` Knop to the `alice/bio` `RdfDocument`
- `09-alice-bio-referenced-woven`: weave `08-alice-bio-referenced`
- `10-alice-bio-updated`: update the integrated payload before the next weave
- `11-alice-bio-v2-woven`: weave `10-alice-bio-updated`
- `12-bob-extracted`: extract the referenced Bob IRI into Knop-managed resources
- `13-bob-extracted-woven`: weave `12-bob-extracted`

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
