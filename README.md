<p align="center">
  <img src="assets/tracefoundry-mark.svg" alt="TraceFoundry mark" width="112" />
</p>

<h1 align="center">TraceFoundry</h1>

<p align="center">
  <strong>Evidence infrastructure for complex investigation.</strong><br />
  Discover what matters. Trace why it matters. Know what is still missing.
</p>

<p align="center">
  <a href="https://github.com/viniburilux/TraceFoundry">
    <img src="https://img.shields.io/badge/status-public%20core-1f2937.svg" alt="Status: public core" />
  </a>
  <a href="docs/TEST_MATRIX.md">
    <img src="https://img.shields.io/badge/policy-metadata--only-0f766e.svg" alt="Metadata only" />
  </a>
  <img src="https://img.shields.io/badge/license-MIT-2563eb.svg" alt="License: MIT" />
  <img src="https://img.shields.io/badge/python-3.9%2B-3776ab.svg" alt="Python 3.9+" />
</p>

> **TraceFoundry is the public research infrastructure layer of LUXVERSO.**
>
> **TraceFoundry é a camada pública de infraestrutura de investigação do LUXVERSO.**

[**LUXVERSO**](https://github.com/viniburilux/LuxVerso) é o ecossistema independente de Research & Build criado e conduzido por Vinícius Buri Lux.

---

# What is TraceFoundry?

TraceFoundry is an **evidence infrastructure for complex investigation**.

It helps transform fragmented public information into a structured, reviewable investigation:

```text
Complex question
       ↓
Discovery
       ↓
Evidence + entities
       ↓
Claims + relations + gaps
       ↓
Investigation state
       ↓
Research move
       ↓
Next defensible action
```

The goal is not simply to find information.

The goal is to make the reasoning space around a decision inspectable.

TraceFoundry connects scientific datasets, papers, patents and research assets across public sources, normalizes their metadata, preserves provenance, applies explicit eligibility rules, represents evidence and gaps, and records what should happen next.

It is designed for investigations where being able to explain why a conclusion or next action is justified matters as much as finding the information itself.


---

## The problem

Complex research rarely fails because information does not exist.

It fails because information is:

- fragmented across sources

- represented under incompatible identifiers

- difficult to connect

- mixed with duplicates and false positives

- detached from its provenance

- interpreted without clearly separating fact from inference

- missing explicit records of what was rejected

- unable to show what remains unknown
- difficult to revisit after the original investigation.


A search result is not yet evidence.

A candidate is not yet a validated asset.

A paper is not proof that a dataset exists.

A correlation is not a causal conclusion.

And an absence of search results is not necessarily evidence that something does not exist.

TraceFoundry keeps these distinctions visible.


---

## From information to investigation

Traditional search answers:

> "What can I find?"



RAG systems often answer:

> "What can I generate from this corpus?"



TraceFoundry addresses a different layer:

> "What do we actually know, why do we believe it, what is still missing, and what should we investigate next?"



That requires more than retrieval.

It requires a chain:

SOURCE
  ↓
OBSERVATION
  ↓
ENTITY
  ↓
EVIDENCE
  ↓
CLAIM
  ↓
RELATION
  ↓
GAP / CONTRADICTION / INSUFFICIENCY
  ↓
INVESTIGATION STATE
  ↓
RESEARCH MOVE
  ↓
NEXT ACTION

This is the core idea behind TraceFoundry.


---

## The investigation model

TraceFoundry deliberately separates different epistemic states.

FACT

What is directly supported by an observed source.

Examples:

- a paper exists

- an author is associated with a work

- a patent record exists

- a dataset reports a particular version

a source exposes a particular metadata field.


Every factual assertion should be traceable to its underlying evidence.

INFERENCE

What can reasonably be derived by connecting multiple observations.

Examples:

- relationships between entities

- recurring institutional patterns

- cross-source connections

- clusters of related research

convergence between independent evidence.


Inference is explicitly represented as inference.

It is not silently presented as fact.

HYPOTHESIS

A direction suggested by the evidence but not yet demonstrated.

Examples:

- an unexplored research direction

- a potentially relevant technology

- a possible connection between actors

a promising but insufficiently supported opportunity.


Hypotheses remain hypotheses until evidence changes their status.

GAP

Something relevant that is currently missing from the evidence.

BLOCKAGE

A dependency prevents investigation from continuing.

Examples:

- rate limits

- missing credentials

- inaccessible source

unavailable metadata.


A blocked source is not treated as negative evidence.

CONTRADICTION

Two or more observations cannot currently be reconciled.

This distinction matters because uncertainty is information too.


---

## What TraceFoundry does

01 — Discover

Query multiple public sources through a common interface.

Current adapters include:

DANDI

Zenodo

OpenAlex

PatentsView


The architecture is extensible to additional sources.


---

02 — Normalize

Convert source-specific responses into canonical records with:

- stable identifiers

- metadata

- URLs

- versions

- source information

- warnings

provenance.


This makes heterogeneous sources comparable without pretending they are identical.


---

03 — Resolve and connect

Represent relationships between:

- datasets

- papers

- authors

- institutions

- patents

- inventors

- assignees

- research assets

investigations.


The objective is not simply to collect records.

It is to understand how the records connect.


---

04 — Select transparently

Candidates are evaluated through explicit rules.

TraceFoundry records:

- why an item was selected

- why it was rejected

- what constraint caused rejection

what evidence supported the decision.


There is no requirement to hide the decision process behind an opaque ranking score.


---

05 — Preserve negative evidence

"No eligible result" is different from:

- source failure

- rate limiting

- missing credentials

- incomplete metadata

blocked dependency.


This allows an investigation to distinguish:

NOT FOUND
    ≠
NOT ELIGIBLE
    ≠
INSUFFICIENT EVIDENCE
    ≠
SOURCE BLOCKED

That distinction is critical in serious discovery and due diligence.


---

06 — Represent claims and evidence

The investigation layer connects claims to their supporting evidence.

This makes it possible to ask:

> What supports this statement?



and:

> What evidence would change this conclusion?



The system is designed to make the evidence chain reviewable rather than hiding it behind a generated answer.


---

07 — Track gaps

A good investigation does not only record what was found.

It records what remains unresolved.

TraceFoundry can represent:

- missing evidence

- unresolved entities

- contradictory observations

- insufficient support

- blocked sources

unanswered questions.


This turns uncertainty into an explicit research object.


---

08 — Propose Research Moves

A ResearchMove represents a proposed next investigation step.

It records:

- the proposed action

- why the action is justified

- the expected observation

stop criteria.


The objective is not autonomous decision-making.

It is to make the next defensible move explicit and reviewable.


---

## The TraceFoundry loop

A TraceFoundry investigation can be understood as a loop:

┌─────────────────────┐
                 │   COMPLEX QUESTION  │
                 └──────────┬──────────┘
                            ↓
                    ┌───────────────┐
                    │   DISCOVERY   │
                    └───────┬───────┘
                            ↓
                  ┌───────────────────┐
                  │ EVIDENCE / ENTITY │
                  └─────────┬─────────┘
                            ↓
                 ┌────────────────────┐
                 │ CLAIMS / RELATIONS │
                 └──────────┬─────────┘
                            ↓
                    ┌──────────────┐
                    │ GAPS / STATE │
                    └───────┬──────┘
                            ↓
                   ┌────────────────┐
                   │ RESEARCH MOVE  │
                   └───────┬────────┘
                           ↓
                ┌─────────────────────┐
                │ NEXT ACTION / TEST  │
                └──────────┬──────────┘
                           │
                           └──────────────→ new evidence

The investigation can therefore evolve instead of ending at a search result.


---

## Where it fits

TraceFoundry is designed for:

| Domain | Investigation question |
| --- | --- |
| Scientific scouting | Which technologies, datasets, papers or research groups deserve attention first? |
| R&D intelligence | What evidence supports a technical direction? |
| Technology intelligence | Which actors, technologies and relationships are emerging? |
| Technical due diligence | What is actually supported by the available evidence? |
| Innovation | Which opportunities are supported, which are speculative, and what should be tested next? |
| Partner discovery | Which institutions, researchers or companies appear connected to the problem? |
| Patent intelligence | Which families, classifications, inventors and assignees appear in a reproducible investigation? |
| Sustainability & clean tech | Which public evidence supports a technology, process or hypothesis? |
| Research operations | What has already been investigated, rejected, blocked or left unresolved? |


The domain can change.

The underlying discipline remains:

provenance + evidence + relationships + uncertainty + next action.


---

## What makes TraceFoundry different

The differentiation is not:

> "AI that searches the internet."



It is the combination of several properties that are normally separated.

Cross-source

Different public sources can be investigated under common contracts.

Explainable

Selection and rejection have explicit reasons.

Provenance-first

Evidence retains its source context.

Epistemic

Facts, inferences, hypotheses, gaps, blockages and contradictions are not collapsed into one confidence score.

Reproducible

Queries, timestamps, observations and decisions can be packaged into versioned manifests.

Reviewable

The system is designed for human inspection rather than hiding reasoning behind an opaque answer.

Action-oriented

The investigation can end with a proposed Research Move, not merely a pile of documents.


---

## A different kind of output

A conventional discovery workflow might produce:

20 links
5 papers
3 datasets
2 patents

TraceFoundry aims to produce something closer to:

QUESTION
    ↓
WHAT WAS SEARCHED
    ↓
WHAT WAS FOUND
    ↓
WHAT WAS CONNECTED
    ↓
WHAT SUPPORTS EACH CLAIM
    ↓
WHAT WAS REJECTED AND WHY
    ↓
WHAT REMAINS UNKNOWN
    ↓
WHAT IS BLOCKED
    ↓
WHAT SHOULD BE INVESTIGATED NEXT

That is the difference between retrieval and investigation infrastructure.


---

## Public core

TraceFoundry is intentionally designed as a public infrastructure layer.

The public core includes:

- source adapters

- canonical metadata contracts

- deterministic selection

- provenance

- manifests

- investigation contracts

- evidence and claim structures

- Research Moves

- reproducible fixtures

- testing infrastructure

- scientific staging guidance

- claim-audit guidance

publication workflow.


The public core is metadata-only by default.

It does not download scientific datasets or deserialize formats such as:

- pickle

- NWB

HDF5.


The system can establish what a public source reported and how a deterministic policy treated that information.

It does not pretend that metadata alone proves scientific validity.


---

## Public infrastructure, private research

TraceFoundry is the reusable public infrastructure layer of LUXVERSO.

The boundary is deliberate.

LUXVERSO
                         │
              ┌──────────┴──────────┐
              │                     │
        PUBLIC LAYER           PRIVATE LAYER
              │                     │
        TraceFoundry          Research systems
              │               Derived datasets
              │               Private decisions
              │               Research memory
              │
        Evidence / discovery
        provenance / claims
        investigation state
        research moves

Private research can generate candidates, observations and discoveries.

Public work can expose:

- infrastructure

- reproducible evidence

- demonstrations

- methodologies

shareable knowledge.


The boundary prevents private research state from being confused with public evidence.


---

## Architecture

At its core:

Source API
    ↓
Source Adapter
    ↓
Canonical Records
    ↓
Explainable Selection
    ↓
Versioned Manifest
    ↓
Evidence / Claims / Gaps
    ↓
Investigation State
    ↓
Research Move
    ↓
Human Review
    ↓
Controlled acquisition / analysis

The architecture intentionally separates discovery, representation, evidence, investigation and action.


---

## Current source coverage

| Adapter | Mode | Credential | Typical use |
| --- | --- | --- | --- |
| DANDI | Metadata-only live queries | No | Neurophysiology and organoid dataset discovery |
| Zenodo | Metadata-only live queries | No | Research records, datasets and artifacts |
| OpenAlex | Metadata-only live queries | No | Papers, authors, institutions and citation context |
| PatentsView | Offline normalization + conditional live queries | `PATENTSVIEW_API_KEY` | Patent metadata, classifications, inventors, assignees and families |


The architecture is intentionally source-agnostic.

New sources can implement the adapter contract without changing the core investigation model.


---

## Five-minute first run

python3 -m venv .venv
. .venv/bin/activate
python -m pip install -e .

Example:

PYTHONPATH=src python scripts/oi_discover.py \
  --source dandi \
  --dataset-id 001603 \
  --version draft \
  --format nwb \
  --max-assets 1 \
  --output discovery_result.json

The result is a metadata manifest.

It records:

download_performed: false

so the result can be inspected before controlled acquisition.


---

## Patent metadata

For PatentsView, provide the credential explicitly:

export PATENTSVIEW_API_KEY="..."

Then:

PYTHONPATH=src python scripts/oi_discover.py \
  --source patentsview \
  --dataset-id "methanol detection" \
  --max-assets 5 \
  --output patents_result.json


---

## Linking to private research systems

A public manifest can be handed to a private memory or research system without automatically writing to its database:

PYTHONPATH=src python scripts/link_manifest_to_luxmemory.py \
  --manifest discovery_result.json \
  --output discovery_memory_link.json \
  --memory-type result \
  --capability-id CAP-OBS-EVIDENCE_MEMORY_DECISION

This preserves the separation between public infrastructure and private research state.


---

## Validation

Run the offline suite without credentials or network access:

PYTHONPATH=src python tests/run_offline_tests.py
PYTHONPATH=src python tests/run_dsl_registry_tests.py

Metadata-only live checks:

PYTHONPATH=src python tests/run_live_metadata_tests.py
PYTHONPATH=src python tests/run_cross_domain_live_tests.py

The repository includes:

- [Test Matrix](docs/TEST_MATRIX.md)
- [Cross-Domain Results](docs/CROSS_DOMAIN_TESTS.md)
- [Benchmark v0](docs/BENCHMARK_V0_RESULTS.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Investigation Contracts](docs/INVESTIGATION.md)
- [Scientific Staging Playbook](docs/SCIENTIFIC_STAGING_PLAYBOOK.md)
- [Claim Audit Starter Kit](docs/CLAIM_AUDIT_PLAYBOOK.md)
- [Publication Pipeline](docs/PUBLICATION_PIPELINE.md)
- [Commercial Positioning](docs/POSITIONING.md)



---

## What TraceFoundry does not claim

TraceFoundry does not claim that:

- metadata proves scientific validity

- a dataset is automatically suitable for a research hypothesis

- a paper proves a technology works

- an inferred relationship is necessarily causal

- a candidate is automatically a validated asset

- an LLM-generated statement is true merely because it sounds plausible

the system replaces expert judgment.


Instead:

> TraceFoundry makes expert investigation faster to start, easier to audit, and harder to accidentally overstate.




---

## Maturity

The public core is currently a functional and demonstrable research infrastructure.

The following capabilities exist in the public repository:

- source adapters

- canonical records

- deterministic selection

- provenance

- reproducible manifests

- metadata-only tests

- investigation contracts

- evidence and claim representation

- Research Moves

cross-domain fixtures.


What remains to be demonstrated empirically is the magnitude of the operational benefit:

- how much investigation time is reduced

- how much ambiguity is removed

- whether decision quality improves

- how much rework is avoided

whether teams are willing to pay for the capability.


Those are validation questions, not claims.


---

## Roadmap

The next product gate is not simply:

> "Add more adapters."



The more important question is:

> Can TraceFoundry measurably reduce the time, ambiguity and unsupported reasoning required to reach a defensible next action?



Planned extensions include:

- stronger entity resolution

- cross-source deduplication

- richer claims/evidence graphs

- readiness gates

- paper-to-code relationships

- expanded investigation state

- private research-state integration

- broader domain adapters

controlled value tests.



---

## The core idea

TraceFoundry is built around a simple principle:

> An investigation should leave a trail.



Not just a final answer.

A trail showing:

what was asked
    ↓
what was searched
    ↓
what was observed
    ↓
what was connected
    ↓
what supports each claim
    ↓
what was rejected
    ↓
what remains uncertain
    ↓
what is blocked
    ↓
what should happen next

That trail is the infrastructure.


---

## Bring a difficult question

> Bring a difficult discovery question.

Leave with a reviewable evidence map, explicit gaps and a next action you can defend.




---

## Contributing

Contributions are welcome when they preserve the core principles:

- metadata-only by default

- explicit provenance

- deterministic selection

- negative evidence as a valid result

- explicit epistemic states
- reviewable investigation
- no scientific conclusion without supporting evidence.


Start with [CONTRIBUTING.md](CONTRIBUTING.md) and read [ARCHITECTURE.md](docs/ARCHITECTURE.md) before adding a source adapter.


---

## License

The public core is released under the [MIT License](LICENSE).

Datasets, papers, external APIs and private research artifacts remain subject to their own terms.


---

<p align="center">
  <strong>TraceFoundry</strong><br />
  Evidence infrastructure for complex investigation.
</p>
