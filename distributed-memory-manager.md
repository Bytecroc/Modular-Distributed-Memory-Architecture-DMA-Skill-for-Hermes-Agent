---
name: distributed-memory-manager
category: productivity
description: Manages project-specific data (DMA) using a file-based distributed architecture with chunked retrieval and state persistence.
---

# Distributed Memory Architecture (DMA)

## Overview
[cite_start]This skill manages specific "Project Data" (DMA). [cite_start]It ensures that large amounts of project information are stored in a structured way on the disk and retrieved efficiently without overloading the context window[cite: 4].

## Core Conventions
- [cite_start]**Storage Path:** `~/data/project_memory/` (Adjust to your local path) [cite: 5]
- [cite_start]**Session State:** Uses files in `~/session_memory/` to maintain "Context Bridges"[cite: 5].
- [cite_start]**Chunking Strategy:** Information is retrieved in chunks to avoid context bloat[cite: 6].

## Procedures

### 1. Data Offloading (DMA Write)
When new project facts, technical specs, or structure data are identified:
1. [cite_start]Determine the appropriate sub-folder based on topic[cite: 7].
2. [cite_start]Format the content as a clean Markdown entry[cite: 8].
3. [cite_start]Use `write_file` to save it[cite: 8].
4. [cite_start]Update the `index.md` in the root of the DMA folder to include the new fact/path[cite: 9].

### 2. Context Bridge (Retrieval)
When switching tasks or needing deep context:
1. [cite_start]Identify the relevant "State File" for the current project phase[cite: 10].
2. [cite_start]Use `read_file` with a specific `offset` and `limit` to pull only the necessary chunk[cite: 11].
3. [cite_start]Inject this into the prompt as a "Context Bridge"[cite: 12].

### 3. Checkpointing
After significant progress (e.g., completing a functional module or a text section):
1. [cite_start]Create a summary of the current state[cite: 13].
2. [cite_start]Save it as `Checkpoint_YYYYMMDD_Topic.md`[cite: 14].
3. [cite_start]Update the main `Project_Summary.md` or global status files if applicable[cite: 14].

## Pitfalls
- [cite_start]Do not save temporary TODOs to DMA; use session memory for that[cite: 15].
- [cite_start]Ensure all file paths are absolute to avoid ambiguity across different sessions[cite: 16].
