---
name: meta-path-discovery
description: Use to automatically locate the Foundry (Core Library) root directory using recursive upward searching for .gemini/global_standard.md.
---

# Meta Path Discovery (Foundry Locator)

## Overview
This meta-skill provides the algorithm for AI agents to locate the **Foundry Root** in any environment. It eliminates the need for hardcoded absolute paths by using recursive filesystem discovery.

## When to Use
- When any skill needs to reference a file in the Foundry (e.g., `patterns/`, `schemas/`).
- During initialization to establish the `link.json` stub.
- When `{{FOUNDRY_ROOT}}` placeholder is encountered in instructions.

## The Discovery Algorithm

To find `{{FOUNDRY_ROOT}}`, follow these steps in order:

1. **Check Workspace Config**:
   Read `.gemini/config.json` in the current working directory. If `skillPaths` points to a directory containing `.gemini/global_standard.md`, that is your **Foundry Root**.

2. **Recursive Search (The Climb)**:
   Starting from the current working directory, search upwards for a directory containing `.gemini/global_standard.md`.
   - **Step A**: Is `.gemini/global_standard.md` in the current dir? If yes, stop.
   - **Step B**: Move to parent dir. Repeat Step A.
   - **Limit**: Stop at the drive root (e.g., `C:\` or `/`).

3. **Link Stub Check**:
   Read `.gemini/link.json`. Use the `motherBasePath` value as the **Foundry Root**.

## Output Standard
Once located, the agent MUST cache this path in the current session context and use it to replace all `{{FOUNDRY_ROOT}}` instances.

## Red Flags
- Using an absolute path (e.g., `D:\code\...`) without attempting discovery.
- Failing to verify the existence of `global_standard.md` at the target path.
