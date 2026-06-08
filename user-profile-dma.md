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
