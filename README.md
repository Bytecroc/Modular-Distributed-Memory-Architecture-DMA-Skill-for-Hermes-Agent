### 🧱 Modular Distributed Memory Architecture (DMA) for Hermes Agent

This suite consists of three specialized procedural skills designed to efficiently offload, organize, and retrieve information on local high-performance hardware environments without blowing up the active LLM context window. It works flawlessly with local backends like `llama.cpp` and inference engines running models like Gemma 4 12B.

### ⚙️ Installation Guide

To implement these skills into your local Hermes installation, follow these steps:

1. **Create the Skills Directory:**
    
    Navigate to your local Hermes Agent directory and create a dedicated folder for your customs skills if it doesn't already exist:
    
    Bash
    
    ```
    mkdir -p ~/hermes/skills/
    ```
    
2. **Save the Skill Files:**
    
    Save the three code blocks provided below into your `~/hermes/skills/` directory using the exact filenames specified:
    
    - `distributed-memory-manager.md`
        
    - `user-profile-dma.md`
        
    - `narrative-consistency.md`
        
3. **Configure Your Local Absolute Paths:**
    
    Open each markdown file and locate the **Core Conventions** section. Replace the placeholder paths (e.g., `~/data/...`) with your actual, absolute storage directories on your machine.
    
    > ⚠️ **Pitfall:** Avoid relative paths; absolute paths prevent context confusion across different terminal sessions.
    
4. **Initialize and Multi-Profile Setup (Optional but Recommended):**
    
    Restart your Hermes Agent. The engine will automatically register the new files as procedural skills.
    
    - **Pro-Tip for Power Users:** If you want to use these skills across different distinct work scopes (e.g., _System Maintenance_, _Software Development_, and _Creative Writing/RPGs_), combine them with a routing plugin like `multi-memory-plugin`. This allows you to sandbox your memories into isolated data banks, ensuring that code snippets never leak into your creative storytelling context.
        
### 📜 Clear Skill Scripts

#### Skill 1: `distributed-memory-manager.md`

Markdown

```
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
```

#### Skill 2: `user-profile-dma.md`

Markdown

```
---
name: user-profile-dma
category: productivity
description: Manages persistent user preferences (DMU) and offloads them to a dedicated profile file.
---

# User Profile Distributed Memory Architecture (DMU)

## Overview
[cite_start]This skill manages the "User Profile" (DMU)[cite: 19]. [cite_start]It ensures that your personal preferences, technical constraints, hardware configurations, and interaction styles are always available but kept out of the primary project context.

## Core Conventions
- [cite_start]**Primary Source:** `~/data/user_profile/User_Profile_Offloaded.md` [cite: 21]
- [cite_start]**Update Rule:** Any new preference or system-level correction must be added here immediately[cite: 21].

## Procedures

### 1. Fact Extraction & Offloading
When the user expresses a specific structural or tool preference:
1. [cite_start]Extract the core technical rule or preference[cite: 22, 23].
2. [cite_start]Check if it already exists in `User_Profile_Offloaded.md`[cite: 23].
3. [cite_start]If not, append it to the relevant section (e.g., #Backend, #Style, #Tools)[cite: 23].
4. [cite_start]Use `write_file` to update the master file[cite: 24].

### 2. Profile Retrieval
At the start of a new session or when a profile switch is requested:
1. [cite_start]Read the `User_Profile_Offloaded.md`[cite: 24].
2. [cite_start]Filter for the relevant sections (e.g., hardware samplers, inference constraints)[cite: 25].
3. [cite_start]Inject these as system-level instructions to define the agent's behavior[cite: 26].

## Pitfalls
- [cite_start]Never delete entries from the DMU; only replace them if they are completely outdated[cite: 26, 27].
- [cite_start]Keep descriptions concise to save context tokens[cite: 27].
```

#### Skill 3: `narrative-consistency.md`

Markdown

```
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
```

### 💡 Why are these skills useful? 

- **Context-Bloat Prevention:** Standard memory setups force the agent to read entire conversation logs or complete code repositories over and over. These skills introduce a strict file-based pagination mechanism (`offset` and `limit`). Hermes only reads what it _actually_ needs right now.
    
- **Deterministic Agent Control:** Instead of letting a background database guess what information matters based on messy semantic similarity, these skills turn memory management into an _explicit instruction_. The LLM intelligently triggers a manual disk-write or disk-read operation via Markdown procedures.
    
- **Separation of Concerns:** By keeping backend constraints/hardware preferences in the DMU and project files in the DMA, the model never gets confused by overlapping data. It keeps your primary prompt clean, fast, and highly predictable.
