# mesh-alice-bio

`mesh-alice-bio` is a small staged example repository used as a manual comparison fixture for Semantic Flow and Weave.

It is intentionally branch-oriented. Each numbered branch represents a specific scenario in the evolution from plain source RDF to a mesh-managed layout, so future CLI and API behavior can be compared against a concrete hand-built baseline.

The current scenario ladder is:

- `0-blank-slate`: repository scaffold only
- `1-source-only`: plain source RDF with no mesh structure
- `2-mesh-created`: manual mesh creation with `_mesh` metadata and inventory
- `3-alice-knop-created`: manual creation of the `alice` Knop
- `4-alice-bio-integrated`: integration of the source artifact as the payload artifact for `alice/bio`
- `5-alice-bio-referenced`: add a ReferenceLink from the `alice` Knop to the `alice/bio` `RdfDocument`
- `6-alice-bio-v2`: update the integrated payload and regenerate affected mesh outputs
- `7-bob-extracted`: extract the referenced Bob IRI into Knop-managed resources

The example is meant to support:

- manual filesystem inspection
- ontology discussion
- API and CLI comparison
- future documentation examples

The intended comparison standard is:

- same filesystem layout
- canonically equivalent RDF graphs
- explicit exclusion of volatile `created` and `updated` timestamps when comparing generated metadata
