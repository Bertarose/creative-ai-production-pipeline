# Workflow Diagram

## Visual Pipeline Flow

```
┌─────────────────────────────────────────────────────────────────┐
│                     CLIENT BRIEF / PROJECT START                │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 1: BRIEF ANALYSIS & CONCEPTUAL DIRECTION                 │
│  ──────────────────────────────────────────────────────         │
│  • Deconstruct brief                                            │
│  • Gather references                                            │
│  • Define creative direction                                    │
│  • Map technical requirements                                   │
│                                                                 │
│  HUMAN DECISIONS:                                               │
│  → Visual language selection                                    │
│  → Tool selection strategy                                      │
│  → Feasibility assessment                                       │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │  TOOL SELECTION       │
                    │  ───────────────      │
                    │  Midjourney? ────┐    │
                    │  Firefly? ───────┤    │
                    │  ComfyUI? ───────┘    │
                    └───────────┬───────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 2: VISUAL EXPLORATION & ITERATION                        │
│  ──────────────────────────────────────────                     │
│  • Initial prompt engineering                                   │
│  • Style testing                                                │
│  • Composition experiments                                      │
│  • Stakeholder feedback loops                                   │
│                                                                 │
│  HUMAN DECISIONS:                                               │
│  → Style approval                                               │
│  → Composition selection                                        │
│  → Iteration direction                                          │
│                                                                 │
│  OUTPUT: 3-5 approved visual directions                         │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
                        ┌───────────────┐
                        │ Style locked? │
                        │      │        │
                        │   No │ Yes    │
                        │      │        │
                        └──┬───┴───┬────┘
                           │       │
                 ┌─────────┘       └────────┐
                 │                           │
                 ▼                           ▼
        [Loop back to                  [Proceed to
         Stage 2]                       Stage 3]
                                            │
                                            ▼
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 3: CONTROLLED GENERATION                                 │
│  ────────────────────────────────                               │
│  • Production prompt optimization                               │
│  • Batch generation workflows                                   │
│  • Consistency maintenance                                      │
│  • Quality control screening                                    │
│                                                                 │
│  HUMAN DECISIONS:                                               │
│  → Parameter tuning                                             │
│  → Quality approval                                             │
│  → Consistency check                                            │
│                                                                 │
│  VOLUME: 100+ generations → 20 candidates                       │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Quality sufficient?   │
                    │       │               │
                    │    No │ Yes           │
                    │       │               │
                    └───┬───┴───┬───────────┘
                        │       │
              ┌─────────┘       └────────┐
              │                           │
              ▼                           ▼
    [Refine prompts,              [Select finals,
     regenerate]                   proceed]
                                        │
                                        ▼
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 4: SELECTION & POST-PRODUCTION                           │
│  ───────────────────────────────────────                        │
│  • Final asset curation                                         │
│  • Professional retouching (Photoshop/AE)                       │
│  • Composition refinement                                       │
│  • Text/brand integration                                       │
│  • Format adaptation (web, print, social)                       │
│                                                                 │
│  TRADITIONAL TOOLS:                                             │
│  → Photoshop (retouching, compositing)                          │
│  → Illustrator (vector elements)                                │
│  → After Effects (motion)                                       │
│                                                                 │
│  HUMAN DECISIONS:                                               │
│  → Final curation (20 → 5 assets)                               │
│  → Retouching extent                                            │
│  → Brand integration approval                                   │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Client approval?      │
                    │       │               │
                    │    No │ Yes           │
                    │       │               │
                    └───┬───┴───┬───────────┘
                        │       │
              ┌─────────┘       └────────┐
              │                           │
              ▼                           ▼
    [Revisions needed]            [Proceed to
     (loop back to Stage 3        delivery]
      or Stage 4 based on                │
      scope of changes)                  │
                                        ▼
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 5: DELIVERY & DOCUMENTATION                              │
│  ────────────────────────────────────                           │
│  • File organization & naming                                   │
│  • Delivery package assembly                                    │
│  • Usage rights documentation                                   │
│  • Process documentation                                        │
│  • Client handoff                                               │
│                                                                 │
│  DELIVERABLES:                                                  │
│  → Production-ready assets                                      │
│  → Source files                                                 │
│  → Regeneration instructions                                    │
│  → Licensing documentation                                      │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
                        ┌───────────────┐
                        │  PROJECT      │
                        │  COMPLETE     │
                        └───────────────┘
```

---

## Decision Point Matrix

| Decision Point | Timing | Stakeholders | Impact if Wrong |
|---------------|--------|--------------|-----------------|
| Tool Selection | Stage 1 | Creative Tech + AD | Wasted exploration time, incompatible outputs |
| Style Approval | Stage 2 | Client + CD | Major rework in Stage 3 |
| Generation Quality | Stage 3 | Producer + Designer | Client rejection, late delivery |
| Post-Production Extent | Stage 4 | CD + Account | Over/under polish, budget overrun |
| Final Approval | Stage 4 | Client | Delivery delays, additional costs |

---

## Tool Selection Guide

```
PROJECT NEEDS ASSESSMENT
│
├─ Need artistic exploration? ──→ START WITH: Midjourney
│  High stylization?              BACKUP: ComfyUI for control
│  Rapid iteration?
│
├─ Need commercial safety? ────→ START WITH: Firefly
│  Brand compliance critical?     BACKUP: Stock + AI enhancement
│  Legal risk aversion?
│
├─ Need precise control? ───────→ START WITH: ComfyUI
│  Batch consistency?             BACKUP: Midjourney for style ref
│  Technical specifications?
│
└─ Need all of the above? ──────→ HYBRID APPROACH:
   Large scale project?            Stage 2: Midjourney (exploration)
   Complex requirements?           Stage 3: ComfyUI (production)
                                  Stage 4: Firefly (safe variations)
```

---

## Timing Variations by Project Scale

### Fast Track Mode (48-72 hours)
```
Stage 1: 4 hours  ──┐
Stage 2: 12 hours ──┤
Stage 3: 8 hours  ──┼─→ 32 hours total
Stage 4: 6 hours  ──┤
Stage 5: 2 hours  ──┘
```
*Use for: Client pitches, concept explorations, internal needs*

### Standard Mode (1-2 weeks)
```
Stage 1: 1-2 days  ──┐
Stage 2: 3-5 days  ──┤
Stage 3: 2-3 days  ──┼─→ 10-14 days total
Stage 4: 2-3 days  ──┤
Stage 5: 1 day     ──┘
```
*Use for: Most client projects, campaign assets, social media*

### Comprehensive Mode (3-4 weeks)
```
Stage 1: 3-5 days   ──┐
Stage 2: 1-2 weeks  ──┤
Stage 3: 1 week     ──┼─→ 3-4 weeks total
Stage 4: 1 week     ──┤
Stage 5: 2-3 days   ──┘
```
*Use for: Complex campaigns, R&D projects, new visual systems*

---

## Iteration Loops: When to Go Back

### Minor Issues (1-2 hours to resolve)
- **Loop:** Within Stage 3 → regenerate with adjusted prompts
- **Trigger:** Minor quality issues, small composition changes
- **Decision:** Producer/Designer level

### Medium Issues (1-2 days to resolve)
- **Loop:** Stage 4 → Stage 3 → Stage 4
- **Trigger:** Need different variations, format requirements changed
- **Decision:** Creative Director approval required

### Major Issues (3-5 days to resolve)
- **Loop:** Stage 4 → Stage 2 → Stage 3 → Stage 4
- **Trigger:** Style doesn't match brief, brand misalignment
- **Decision:** Client + CD + Account team alignment

### Complete Pivot (restart project)
- **Loop:** Back to Stage 1
- **Trigger:** Fundamental strategic shift, brand change, budget cut
- **Decision:** Senior leadership + client

---

## Parallel Workflow Option

For large projects, run exploration and production in parallel:

```
Team A: Stages 1-2 (Direction setting)
           │
           └──→ Hand off approved direction
                           │
Team B: ←──────────────────┘
        Stages 3-4-5 (Production execution)

While Team B produces Batch 1,
Team A explores concepts for Batch 2
```

*Requires strong documentation and communication protocols*

---

## Quality Gates

Each stage ends with a formal quality gate:

1. **Gate 1:** Creative brief approved by stakeholders
2. **Gate 2:** Visual direction selected and documented
3. **Gate 3:** Generated assets pass quality control
4. **Gate 4:** Post-production finals approved by Creative Director
5. **Gate 5:** Client sign-off and delivery confirmation

**Do not proceed past a gate without formal approval.**

This prevents costly downstream rework and maintains project momentum.
