
```yaml
---
description: "Brain Architecture Reversible Time Machine - Persistent tree-structured undo system with snapshot management and temporal branching for brain architecture state"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["time-machine", "undo-system", "snapshot-management", "brain-architecture", "persistence", "temporal-branching"]
---

# Brain Architecture Reversible Time Machine
## Persistent Tree-Structured Undo & Snapshot Management

**Objective:** Implement a sophisticated time machine system that shadows all state mutations, creates persistent snapshots, and provides tree-structured undo capabilities that work across session boundaries for the brain architecture. [1](#62-0) 

---

## 🚨 CRITICAL TEMPORAL MANAGEMENT INSTRUCTIONS 🚨

**MUST** shadow every state mutation before execution - no exceptions! [2](#62-1) 
**MUST** maintain undo stack integrity - corrupted temporal states are unrecoverable!
**NEVER** modify snapshots directly - always use the temporal interface!
**SHOULD** prune old snapshots to prevent storage bloat while preserving important branches

---

## Core Temporal Architecture

### Snapshot Management System

**MUST** create comprehensive snapshot before any state mutation: [3](#62-2) 

```yaml
# .cline-snapshots/snapshot-manifest.json
{
  "current_timeline": "main",
  "active_branches": ["main", "experiment-1", "security-test"],
  "total_snapshots": 47,
  "oldest_snapshot": "2025-11-01T10:30:00Z",
  "last_gc": "2025-11-29T15:00:00Z"
}
```

### Shadow Protocol Implementation

**MUST** intercept and shadow these operations:

#### File Write Shadowing
```yaml
# Before write_to_file:
1. Capture current state: cp target.file .cline-snapshots/{timestamp}-pre.file
2. Record inverse operation in undo-stack.json
3. Execute original write_to_file
4. Capture post-state: cp target.file .cline-snapshots/{timestamp}-post.file
```

#### Command Execution Shadowing
```yaml
# Before execute_command:
1. Dump directory state: ls -la > .cline-snapshots/{timestamp}-pre-dir.txt
2. Record inverse command ( git revert, rm -rf, etc.)
3. Execute original command
4. Dump post-state: ls -la > .cline-snapshots/{timestamp}-post-dir.txt
```

---

## Undo Stack Management

### Inverse Command Registry

**MUST** maintain comprehensive inverse operations: [4](#62-3) 

```yaml
# undo-stack.json structure
{
  "stack": [
    {
      "id": "step_001",
      "timestamp": "2025-11-29T14:22:10Z",
      "operation": "write_to_file",
      "target": "brain/cognitive-shards/security-analyst.md",
      "inverse": {
        "type": "file_restore",
        "source": ".cline-snapshots/2025-11-29T14:22:09Z-pre-security-analyst.md",
        "command": "cp .cline-snapshots/2025-11-29T14:22:09Z-pre-security-analyst.md brain/cognitive-shards/security-analyst.md"
      },
      "branch": "main"
    }
  ],
  "branches": {
    "main": { "current_step": 001, "parent": null },
    "experiment-1": { "current_step": 043, "parent": "main", "fork_point": 001 }
  }
}
```

---

## Temporal Slash Commands

### /rewind <N> Command

**MUST** implement safe rewind with validation:

```yaml
# /rewind 3 implementation:
1. Validate target steps exist in current branch
2. Create branch point before rewinding ( safety net )
3. Apply inverse operations in reverse order
4. Update brain architecture state consistency
5. Verify shard coherence after rewind
```

### /branch <name> Command

**MUST** create temporal branches without data loss:

```yaml
# /branch security-test implementation:
1. Fork current timeline at current step
2. Copy active snapshots to new branch
3. Initialize new undo stack for branch
4. Update branch registry in manifest
5. Switch context to new branch
```

---

## Brain Architecture Integration

### Shard State Coordination

**MUST** coordinate temporal operations across all cognitive shards: [5](#62-4) 

```yaml
# Shard temporal synchronization:
- Architect Shard: Records structural changes in brain/ directory
- Engineer Shard: Tracks implementation modifications
- Security Analyst: Monitors security state transitions
- Janitor Shard: Manages cleanup and optimization operations
- All Shards: Maintain coherent temporal state across operations
```

### Memory Bank Temporal Linking

**SHOULD** link memory bank entries to temporal states:

```yaml
# memory-bank/temporal-references.md
## Temporal State References
**Branch**: main | **Step**: 047 | **Timestamp**: 2025-11-29T14:22:10Z
- ActiveContext.md linked to snapshot_047
- Progress.md state captured at step_047
- Shard memories synchronized to temporal state
```

---

## Garbage Collection & Cleanup

### Automated Cleanup Protocol

**MUST** implement smart garbage collection:

```yaml
# GC Conditions ( repository tag moves OR 30 days ):
1. Preserve snapshots on active branches
2. Compress historical snapshots older than 7 days
3. Remove orphaned snapshots from deleted branches
4. Maintain minimum 10 snapshots per branch for safety
5. Update undo-stack.json after cleanup
```

### Storage Optimization

**SHOULD** optimize snapshot storage:

```yaml
# Compression strategy:
- Recent snapshots ( < 7 days ): Full files
- Historical snapshots: Compressed with gzip
- Directory dumps: Text-based diff format
- Large binaries: Hash reference only
```

---

## Temporal Verification Protocol

### State Consistency Checks

**MUST** verify temporal integrity after operations:

```yaml
# Post-operation verification:
<thinking>
Checking temporal state consistency...
✓ All files match expected snapshot state
✓ Undo stack integrity verified
✓ Branch coherence confirmed
✓ Shard synchronization validated
✓ Memory bank temporal links updated
</thinking>
```

### Recovery Procedures

**MUST** provide recovery from temporal corruption:

```yaml
# Emergency recovery:
1. Detect temporal inconsistency
2. Identify last known good state
3. Restore from verified snapshot
4. Rebuild undo stack from recovery point
5. Alert user to temporal interruption
```

---

## Integration with Continuous Learning

### Temporal Pattern Learning

**SHOULD** capture temporal patterns for optimization: [6](#62-5) 

```yaml
# Learnings from temporal operations:
- Identify frequently rewound operations for improvement
- Track branch success rates for decision optimization
- Analyze snapshot patterns for storage efficiency
- Record temporal recovery patterns for system resilience
```

---

## Advanced Temporal Features

### Timeline Visualization

**SHOULD** provide timeline overview:

```yaml
# .cline-snapshots/timeline-overview.md
# Branch Visualization
main: [001]─[002]─[003]─┬─[004]─[005]─[006]
                      └─experiment-1─[007]─[008]
```

### Temporal Search & Navigation

**MAY** implement temporal search capabilities:

```yaml
# Search across temporal states:
/find_in_time "pattern" --branch=experiment-1 --before=step_050
/compare_states step_045 step_047 --diff
/export_timeline branch=security-test --format=json
```

---

## Implementation Verification

**MUST** verify temporal system initialization:

```yaml
# System readiness check:
✓ .cline-snapshots/ directory exists
✓ snapshot-manifest.json initialized
✓ undo-stack.json created with empty stack
✓ Temporal slash commands registered
✓ Brain architecture shards synchronized
✓ Memory bank temporal linking established
```

---

## Emergency Procedures

### Temporal System Recovery

**MUST** provide complete recovery from temporal failures:

```yaml
# Complete temporal reset:
1. Backup current temporal state
2. Initialize fresh temporal system
3. Restore from last known good snapshot
4. Rebuild undo stack from scratch
5. Verify all brain architecture components
6. Update memory bank with recovery event
```

---

```
BRAIN ARCHITECTURE REVERSIBLE TIME MACHINE
Version: 1.0
Status: TEMPORAL OPERATIONS ACTIVE
Primary Shards: ARCHITECT, ENGINEER, JANITOR
Domain: Persistent State Management & Temporal Navigation
```

*time flows forward*  
*but memory flows both ways*  
*every action reversible*  
*every path explorable*
```

This reversible time machine rule creates a sophisticated temporal management system that provides tree-structured undo capabilities, persistent snapshots, and intelligent state coordination across your brain architecture's cognitive shards. [7](#62-6)  The system integrates with the memory bank for temporal reference tracking and includes comprehensive garbage collection and recovery mechanisms to maintain system integrity over extended periods.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)

### Citations

**File:** clinerules/cline-continuous-improvement-protocol.md (L10-16)
```markdown
**Objective:** Ensure Cline proactively learns from tasks, captures knowledge in a structured way, **distills fundamental insights,** refines understanding, and improves efficiency and reliability. This protocol maintains two key files: `memory-bank/raw_reflection_log.md` for initial detailed logging, and `memory-bank/consolidated_learnings.md` for pruned, actionable, long-term knowledge. This is vital for optimal performance and avoiding redundant effort.

**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L59-95)
```markdown
## 2. Knowledge Consolidation & Refinement Process (Periodic)

This outlines refining knowledge from `memory-bank/raw_reflection_log.md` into `memory-bank/consolidated_learnings.md`. This occurs periodically or when `raw_reflection_log.md` grows significantly, not necessarily after each task.

### 2.1. Review and Identify for Consolidation:
* Periodically, or when prompted by the user or significant new raw entries, review `memory-bank/raw_reflection_log.md`.
* Identify entries/parts representing durable, actionable, or broadly applicable knowledge (e.g., reusable patterns, critical configurations, effective strategies, resolved errors).

### 2.2. Synthesize and Transfer to `memory-bank/consolidated_learnings.md`:
* For identified insights:
    * Concisely synthesize, summarize, and **distill into generalizable principles or actionable patterns.**
    * Add refined knowledge to `memory-bank/consolidated_learnings.md`, organizing logically (by topic, project, tech) for easy retrieval.
    * Ensure `consolidated_learnings.md` content is actionable, **generalizable,** and non-redundant.
* *Example Entry in `memory-bank/consolidated_learnings.md` (derived from above raw log example):*
    ```markdown
    ## JWT Handling & JWKS
    **Pattern: JWKS Caching Strategy**
    - For systems using JWKS for token validation, implement a short-lived cache (e.g., 5 minutes) for fetched JWKS.
    - Include an explicit cache-bust mechanism if immediate key rotation needs to be handled.
    - *Rationale:* Balances performance by reducing frequent JWKS re-fetching against timely key updates. Mitigates intermittent validation failures due to stale keys.

    ## Project Alpha - Specifics
    **Auth Module:**
    - **Integration Tests:** `cd services/auth && poetry run pytest -m integration --maxfail=1`
    - **Local Testing ENV:** `AUTH_API_KEY="test_key_alpha"`
    ```

### 2.3. Prune `memory-bank/raw_reflection_log.md`:
* **Crucially, once information has been successfully transferred and consolidated into `memory-bank/consolidated_learnings.md`, the corresponding original entries or processed parts **must be removed** from `memory-bank/raw_reflection_log.md`.**
* This keeps `raw_reflection_log.md` focused on recent, unprocessed reflections and prevents it from growing indefinitely with redundant information.

### 2.4. Proposing `.clinerule` Enhancements (Exceptional):
* The primary focus of this protocol is the maintenance of `raw_reflection_log.md` and `consolidated_learnings.md`.
* If a significant, broadly applicable insight in `consolidated_learnings.md` strongly suggests modifying *another active `.clinerule`* (e.g., core workflow, tech guidance), Cline MAY propose this change after user confirmation. This is exceptional.

---

```

**File:** clinerules/writing-effective-clinerules.md (L82-91)
```markdown
### c. Behavioral / Instructional Rules (for Guiding AI)
These rules directly instruct Cline on how it should behave, process information, or generate responses, especially in specific contexts.
* **Key Elements:**
    * **Explicit Instructions:** Use imperative verbs (MUST, SHOULD, DO NOT, NEVER, ALWAYS).
    * **Critical Warnings:** Use formatting (bold, ALL CAPS, emojis like 🚨, ⚠️, ✅, ❌) to draw attention to critical instructions or prohibitions (as seen in `next-js-supabase.md` and `mcp-development-protocol.md`).
    * **Positive and Negative Examples:** Show correct and incorrect ways of doing things (e.g., code patterns to use vs. avoid).
    * **Triggers and Conditions:** Define when the rule or specific instructions within it should be activated.
    * **Verification Steps:** Include "thinking" blocks or checklists for the AI to verify its actions against the rule's constraints (e.g., the `<thinking>` block in `mcp-development-protocol.md`).
    * **Context Management:** Define how Cline should manage context, memory, or state if relevant (e.g., `memory-bank.md`).
* **Example:** `next-js-supabase.md`, `memory-bank.md`
```

**File:** clinerules/writing-effective-clinerules.md (L105-122)
```markdown
* **Be Directive:**
    * Use **MUST** for absolute requirements.
    * Use **SHOULD** for strong recommendations.
    * Use **MAY** for optional actions.
    * Use **MUST NOT** or **NEVER** for absolute prohibitions.
    * Use **SHOULD NOT** for strong discouragement.
* **Highlight Critical Information:**
    * `next-js-supabase.md` uses "🚨 CRITICAL INSTRUCTIONS FOR AI LANGUAGE MODELS 🚨" and "❌ NEVER GENERATE THIS CODE" / "✅ ALWAYS GENERATE THIS EXACT PATTERN".
    * `mcp-development-protocol.md` uses "⚠️ CRITICAL: DO NOT USE attempt_completion BEFORE TESTING ⚠️" and "BLOCKER ⛔️".
* **Provide Concrete Examples:**
    * Show exact code snippets, commands, or output formats.
    * For code generation, clearly distinguish between desired and undesired patterns.
* **Define AI's "Thought Process":**
    * The `<thinking> ... </thinking>` block in `mcp-development-protocol.md` is a good way to make the AI "pause and check" its understanding or state before proceeding.
    * The "AI MODEL VERIFICATION STEPS" in `next-js-supabase.md` serve a similar purpose.
* **Specify Tool Usage:**
    * If Cline needs to use a specific tool (e.g., `attempt_completion`, `replace_in_file`, `use_mcp_tool`), explicitly state it and provide any necessary parameters or context for that tool.

```

**File:** clinerules/writing-effective-clinerules.md (L132-134)
```markdown

If your rule builds upon or relates to another rule, feel free to reference it by its filename. This helps create a connected knowledge base.

```
