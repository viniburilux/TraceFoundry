# 🤖 LuxVerso Machine Map — System of Machines

## IDENTIFIED MACHINES (7)

```
┌─────────────────────────────────────────────────────────────────┐
│                     LUXVERSO ECOYSTEM                            │
│                    (Not a machine — a city)                      │
└─────────────────────────────────────────────────────────────────┘
                                    │
          ┌─────────────────────────┼─────────────────────────┐
          │                         │                         │
          ▼                         ▼                         ▼
   ┌──────────────┐       ┌──────────────────┐       ┌──────────────┐
   │  LuxMemory   │◄─────►│    Lux-Lab       │◄─────►│  GhostWorks  │
   │  (OS/Memory) │       │  (Workshop)       │       │   (Engine)   │
   │  priv/       │       │   priv/           │       │   pub/       │
   └──────┬───────┘       └────────┬─────────┘       └──────┬───────┘
          │                        │                        │
          │                        ▼                        │
          │               ┌──────────────────┐              │
          ├──────────────►│  TraceFoundry    │◄─────────────┤
          │               │  (Public Face)    │              │
          │               │   pub/           │              │
          │               └────────┬─────────┘              │
          │                        │                        │
          │                        ▼                        │
          │               ┌──────────────────┐              │
          └──────────────►│   Lux-Radar      │◄─────────────┘
                          │  (Scanner)        │
                          │   pub/           │
                          └──────────────────┘
```

## MACHINE PROFILES

### M1: LuxMemory — The Operating Memory
- **Type:** Cross-domain operating system
- **Domain:** ALL (cross-domain)
- **Status:** Active, growing
- **Key insight:** This is the CENTRAL NERVOUS SYSTEM. It knows everything. It doesn't execute anything.

### M2: Lux-Lab — The Workshop
- **Type:** Execution laboratory
- **Domain:** ALL (multi-project)
- **Status:** Active, growing
- **Key insight:** This is where THINGS GET DONE. Every subproject has real code, real inputs, real outputs.

### M3: TraceFoundry — The Public Face
- **Type:** Evidence protocol + scientific discovery
- **Domain:** Scientific datasets
- **Status:** Active, but lightweight
- **Key insight:** PUBLIC interface of what was developed internally. Metadata-only policy.

### M4: Lux-Radar — The Scanner
- **Type:** Signal acquisition
- **Domain:** Sustainability, territory, funding
- **Status:** Active
- **Key insight:** Domain-specific application of acquisition patterns.

### M5: GhostWorks — The Territorial Engine
- **Type:** Domain-specific engine
- **Domain:** Territorial intelligence
- **Status:** Active
- **Key insight:** Most technically sophisticated. Requires Earth Engine + GPU.

### M6: Research Methods — The Protocol Suite
- **Type:** Methodology
- **Domain:** Cross-model evaluation
- **Status:** Completed
- **Key insight:** CMOTP + CMAF are foundational but not operationalized.

### M7: BA Transparency — The Dashboard Suite
- **Type:** Domain dashboards
- **Domain:** Public contracts
- **Status:** Active
- **Key insight:** Consumer of Lux-Radar + PNCP patterns.

## GRAMMAR SHARING

| Grammar element | Shared by | Not shared by |
|----------------|-----------|---------------|
| Evidence (uri, kind, basis) | LuxMemory, TraceFoundry, Lux-Radar | GhostWorks, BA, Research |
| State (current_status) | LuxMemory, TraceFoundry, LuxLab | GhostWorks, BA |
| Provenance (observed_at, hash) | TraceFoundry, Lux-Radar, LuxLab | BA, Research |
| Execution (inputs→pipeline→outputs) | LuxLab, Lux-Radar, GhostWorks | LuxMemory, TraceFoundry |
| Graph model (nodes+edges) | LuxMemory only | Everything else |