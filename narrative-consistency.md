---
name: narrative-consistency
category: creative
description: Ensures logical and physical consistency in generation tasks using checkpoints and world-state tracking.
---

# Narrative Consistency & Checkpointing

## Overview
[cite_start]This skill acts as the "Universal Logic & Consistency Engine"[cite: 30]. [cite_start]It verifies that every output adheres to established rules, physical laws, and previous plot/logic points[cite: 31].

## Core Conventions
- [cite_start]**World State:** Tracked continuously in `Plot_Summary.md` and `World_State.md`[cite: 32].
- [cite_start]**Checkpointing:** Mandatory after every major milestone or completed block[cite: 32].

## Procedures

### 1. Consistency Check (Pre-Generation)
Before generating a new segment:
1. [cite_start]Read the latest `World_State.md`[cite: 33].
2. [cite_start]Verify if the proposed logic or action violates any established "World Rules" or properties[cite: 34].
3. [cite_start]If a conflict or logical fallacy is found, flag it to the user before proceeding[cite: 35].

### 2. Checkpoint Creation (Post-Generation)
After a segment is finalized:
1. [cite_start]Summarize the changes in state, positions, and overall progress[cite: 36].
2. [cite_start]Save as a new checkpoint file in `~/data/narrative/checkpoints/`[cite: 37].
3. [cite_start]Update the main summary files to reflect the current "True State"[cite: 37].

## Logic Rules
- [cite_start]**Physical Laws:** Causality, continuity, and internal logic must be respected unless explicitly overridden by custom parameters[cite: 38].
- [cite_start]**Causality:** Every action must have a logical motivation based on previous events[cite: 39].
