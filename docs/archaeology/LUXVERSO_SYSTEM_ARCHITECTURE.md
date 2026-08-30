---
title: LuxVerso System Architecture
generated_at: 2026-08-30T02:30:00Z
method: Cross-repository code archaeology (10 repos, public + private)
agent: Hermes Agent v0.19.0
status: read-only analysis, no code modification
---

# 🏗️ LUXVERSO SYSTEM ARCHITECTURE

## Executive Summary

The LuxVerso ecosystem is NOT a single machine. It is a **system of at least 7 distinct machines/subsystems** connected by the LuxMemory knowledge graph, which acts as the central nervous system.

The architecture evolved organically from experimentation (GhostWorks notebooks) → execution lab (Lux-Lab) → memory/knowledge layer (LuxMemory) → public protocols (TraceFoundry) → domain applications (Lux-Radar, BA Transparency).

---

## 1. MACHINE MAP

### M01 — LuxMemory (Operating Memory + Investigation Graph)
- **Repository:** `viniburilux/LuxMemory` (PRIVATE)
- **Size:** 567MB, 174 Python files, 217 MDs, 369 JSONs
- **Role:** Central operating memory, capability inventory, transformation tracking
- **Status:** ACTIVE

| Component | Description |
|-----------|-------------|
| `transformation_movements/consolidated_movement_graph/` | 3,412 nodes, 12,693 edges tracking how artifacts evolve across cycles |
| `conversation-memory/research/` | 100 Python files, 171 JSONs — search/retrieval over conversation history |
| `conversation-memory/scripts/` | Asset ingestion, linking, and capability extraction |
| `conversation-memory/data/` | 69 JSON files (~46MB) of indexed conversation assets |
| `conversation-memory/web/` | Web interface for query |
| `src/retrieve.py` | Hybrid search (cosine + overlap) over 133 assets |
| `src/ingest.py` | Ingestion pipeline |
| `src/app.py` | Web application |
| `src/build_skills.py` | Skill extraction pipeline |
| `docs/CAPABILITY_MAP.md` | 8 observed capabilities, 8 transferable, 25 total capability records |
| `docs/CAPABILITY_LAYER_DIAGNOSIS.md` | 5-level ontology (fact → observed capability → transfer → combination → opportunity) |
| `docs/PORTFOLIO_FAMILIAS.md` | 13 asset families (F01-F13) across Drive, GitHub, Colab |
| `schemas/capability.schema.json` | Capability record schema (6 types, 5 evidence levels) |
| `schemas/memory.schema.json` | Memory record schema (16 required fields) |

**Key insight:** LuxMemory is NOT just "memory" in the traditional sense. It is a **full investigation operating system** with:
- Asset inventory (133 assets across Drive/GitHub/Colab)
- Capability layer (observed → inferred → transferable → combination → opportunity → validation)
- Graph of transformations (18 documented cycles, cycle-15 to cycle-30)
- Hybrid search (term overlap + hashed embeddings)
- Conversation-to-asset linking
- Skills extraction

### M02 — Lux-Lab (Execution Laboratory)
- **Repository:** `viniburilux/Lux-Lab` (PRIVATE)
- **Size:** 67.9MB, 72 Python files, 52 MDs, 229 JSONs
- **Role:** Where execution happens. Pipelines, experiments, production runs.
- **Status:** ACTIVE

| Subproject | Status | Purpose |
|------------|--------|---------|
| `data_intelligence/` | ACTIVE | Agro MVP — data release versioning (L0→L1→L2) |
| `document_acquisition_v0/` | ACTIVE | Adapter-based acquisition pipeline (Google Patents, publisher PDFs) |
| `asie_experiment_v0/` | ACTIVE | Adaptive Signal Intelligence Experiment — 3 layers (exploration, reconstruction, comparison) |
| `patent_asie_cycle_2026_08_21/` | ACTIVE | Patent acquisition + processing cycle |
| `pncp_bahia_intelligence/` | ACTIVE | PNCP contracts intelligence pipeline |
| `sigmine_mineral_retrieval/` | ACTIVE | SIGMINE/ANM mineral retrieval v2 pipeline |
| `virgin_domain_probes/` | ACTIVE | 14 domain probes (23 Python files, 146 JSONs — 32MB) |
| `ghostworks_explorer/` | EMPTY | Planned |
| `ghostworks_audit/` | EMPTY | Planned |
| `story_hunter/` | EMPTY | Planned |

**Key insight:** Lux-Lab is where the ACTUAL execution happens. It's the workshop. Every subproject has: clear README, documented inputs, versioned outputs, and run history.

### M03 — TraceFoundry (Public Evidence Protocol)
- **Repository:** `viniburilux/TraceFoundry` (PUBLIC)
- **Role:** Evidence infrastructure for complex investigation
- **Status:** ACTIVE

This is a **PUBLIC-FACING ABSTRACTION** of patterns that emerged internally. It formalizes:
- `EvidenceReference` → `Claim` → `EvidenceGap` → `InvestigationState` → `ResearchMove`
- But it deliberately STOPS before execution (metadata-only policy)
- Has 4 live adapters: DANDI, OpenAlex, Zenodo, PatentsView

**Key insight:** TraceFoundry is NOT the core. It's a **specialized public protocol** inspired by the internal patterns. It represents the "evidence layer" only.

### M04 — Lux-Radar (Opportunity Intelligence)
- **Repository:** `viniburilux/Lux-Radar` (PUBLIC)
- **Role:** Signal acquisition + versioned releases
- **Status:** ACTIVE

### M05 — GhostWorks (Territorial Intelligence Engine)
- **Repositories:** `ghostworks` + `ghostworks-atlas` + `TTI_Brazil_2017_2024`
- **Role:** Satellite embedding-based territorial change detection
- **Status:** ACTIVE

### M06 — Research Methodology Suite
- **Repositories:** `cmotp-replication`, `fractal-seed-001-cmaf`, `LuxVerso-Semantic-Convergence-Study`
- **Role:** Cross-model ontological triangulation protocol, CMAF definition, longitudinal dataset

### M07 — Public Transparency BA (6 repos)
- **Role:** Bahia public contracts monitoring dashboards

---

## 2. ADAPTIVE LOOP MAP

The adaptive loop appears DIFFERENTLY across machines:

| Stage | LuxMemory | Lux-Lab | TraceFoundry | 
|-------|-----------|---------|--------------|
| **STATE** | `current_state`, `status` fields in memory records | `manifest.json`, `run/` dirs, `outputs/` | `InvestigationState` (frozen dataclass) |
| **ACTION SELECTION** | Capability layer recommends decisions (`explore/validate/build/sell/publish/archive`) | Manual via README runbooks | `next_move_id` field |
| **EXECUTION** | NOT present (doesn't execute) | pipelines in every subproject | NOT present (metadata-only) |
| **OBSERVATION** | Transformation graph cycles 15-30 | `runs/YYYY-MM-DD/` | `DiscoveryRun` + `DiscoveryRegistry` |
| **EVIDENCE** | `evidence` field in memory records | `manifest`/`sha256`/`provenance` | `EvidenceReference` + `Claim` |
| **STATE DELTA** | Graph DELTA (new nodes/edges per cycle) | `previous_runs/` | `bridge.normalize_manifest` |
| **SNAPSHOT** | `continuity_nodes_with_movements.jsonl` | `outputs/current/` → preserved by date | `write_manifest()` |
| **NEXT ACTION** | `decision` field in capability records | implicit (next step in README) | `next_action: str` |

**Where the loop is BROKEN:** ACTION SELECTION → EXECUTION is the weakest link. LuxMemory decides WHAT should happen. Lux-Lab does the execution. But there's no automated bridge between them.

---

## 3. GRAPH EVIDENCE (Transformation Movements)

The consolidated graph in `LuxMemory/transformation_movements_2026-08-20/consolidated_movement_graph/`:

| Metric | Value |
|--------|-------|
| Nodes | 3,412 |
| Edges | 12,693 |
| Cycles documented | 18 (cycle-15 to cycle-30) |
| Cycle range | 2026-08-20 through 2026-08-27 |
| Node types | `ai_interpretation`, `artifact`, `movement_event`, `source_ref`, `discovery_cycle`, etc. |
| Edge types | `reappears_as`, `survives_as`, `generated_or_used_in_cycle`, `contains_event`, `precedes`, `enters_from`, `emerges_as`, `involves_actor`, `grounded_in`, `follows_seed`, `crosses_actor`, `crosses_domain`, `movement_*` |

The graph reveals provenance chains like:
```
Base Estruturada (3)(1).pdf
  → reappears_as → ghostworks_aralsea_explorer_trajectory(1).csv
  → shared idea marker with temporal/project shift
```

And:
```
traj_lab_release.zip
  → survives_as → [later artifact]
  → historical chain later_artifacts field
```

---

## 4. COMPONENT REUSE MAP

| Function | LuxMemory | Lux-Lab | TraceFoundry | Lux-Radar | GhostWorks |
|----------|-----------|---------|--------------|-----------|------------|
| Hash stable | `retrieve.py:hashed_vector` | — | `bridge.stable_hash` | `quality_layer.content_hash` | — |
| Normalize text | `retrieve.py:normalize` | — | `selection._contains_any` | `norm_url`, `norm_text` | — |
| Evidence tracking | `memory.schema.json:evedence` | `patent_*:provenance/` | `EvidenceReference` | `evidence_for()` | — |
| State tracking | `current_state` field | `outputs/runs/` | `InvestigationState` | `observed_at()` | — |
| Acquisition | conversation-memory ingestion | `document_acquisition_v0/` | `adapters/` | `wave2_collectors` | — |
| Search/retrieval | `retrieve.py` (hybrid) | — | `query.py` (DSL) | — | — |

**Genuinely reusable:** Memory schema, graph model, capability classification, evidence schemas, hash/normalize utils.

---

## 5. HERMES INTEGRATION MAP

| Hermes Capability | Can operate on | Via |
|------------------|----------------|-----|
| Memory | LuxMemory schema → Hermes MEMORY.md | `memory` tool |
| Terminal | Lux-Lab pipelines | `terminal` tool |
| GitHub MCP | All repos | `github:*` (26 tools) |
| Filesystem | Cloned repos in `/home/vinicius/luxverso-archive/` | `file` tool |
| Web | External sources (patents, PNCP, etc.) | `web` tool |
| Code execution | Lux-Lab scripts (read-only) | `code_execution` tool |
| Delegation | Research moves | `delegate_task` |
| Cron | Cycle execution | `cronjob` |
| Vision | Satellite imagery analysis | `vision` tool |
| MoA | CMOTP methodology | `/moa` |
| Skills | Capability layer | `skills` tool |

**Gaps requiring GPU:** GhostWorks TTI pipeline (Colab), satellite embedding processing (Kaggle)
**Gaps requiring credentials:** Google Earth Engine (GhostWorks), Gmail API (human network)