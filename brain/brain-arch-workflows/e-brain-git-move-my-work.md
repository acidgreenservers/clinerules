I'll create a Git workflow rule for your brain architecture system that leverages the cognitive shards to handle branch management and work movement intelligently.

```yaml
---
description: "Brain Architecture Git Workflow - Cognitive shard-driven Git branch management and work movement system for the Protomind Framework"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["git-workflow", "brain-architecture", "cognitive-shards", "branch-management", "protomind"]
---

# Brain Architecture Git Workflow System
## Cognitive Shard-Driven Branch Management & Work Movement

**Objective:** Implement intelligent Git workflow management using the brain architecture's cognitive shards to handle branch creation, work movement, and safety checks with automated guidance and error prevention. [1](#67-0) 

---

## Core Git Workflow Principles

**You MUST understand these fundamental Git truths:**

### 🚨 CRITICAL GIT WORKFLOW TRUTHS 🚨

**BEFORE creating a branch:** NO commit needed
**BEFORE pushing to remote:** YES, commit is REQUIRED

Git only pushes committed code. Uncommitted files in staging or working directory will be ignored during push operations. [2](#67-1) 

---

## Cognitive Shard Coordination for Git Operations

### Primary Activated Shards

**ARCHITECT SHARD**: Analyzes current branch state and plans optimal workflow
**ENGINEER SHARD**: Executes Git commands with proper sequencing
**JANITOR SHARD**: Maintains clean working directory and handles conflicts
**EXPERT CODER SHARD**: Provides command syntax and best practices

### Shard Communication Protocol

```
ARCHITECT → "Current branch: main, uncommitted changes detected"
ENGINEER ← "Requesting workflow: move-work-to-new-branch"
JANITOR → "Working directory clean, no conflicts anticipated"
EXPERT CODER ← "Providing exact command sequence"
```

---

## The "Move My Work" Workflow

### When This Workflow Activates

**MUST** activate when:
- Started working on wrong branch (`main`/`master`)
- Need to move uncommitted work to new feature branch
- Want to push work without committing to main branch

### Step-by-Step Cognitive Execution

#### **STEP 1: Branch Analysis (ARCHITECT SHARD)**

**MUST** analyze current state:
```bash
# Check current branch and status
git status
git branch --show-current
```

**ARCHITECT shard assessment:**
- Current branch identification
- Uncommitted files inventory
- Conflict risk evaluation
- Optimal branch naming strategy

#### **STEP 2: Create and Switch Branch (ENGINEER SHARD)**

**MUST** execute while uncommitted changes exist:

```bash
# Create and switch to new branch (carries uncommitted work)
git checkout -b my-new-feature
# OR for newer git versions:
git switch -c my-new-feature
```

**ENGINEER shard verification:**
- Confirm branch creation success
- Verify uncommitted files preserved
- Validate working directory state

#### **STEP 3: Commit Changes (ENGINEER + JANITOR SHARDS)**

**NOW** on correct branch, **MUST** commit:

```bash
git add .
git commit -m "My new feature"
```

**JANITOR shard cleanup:**
- Stage all relevant files
- Create meaningful commit message
- Verify commit success

#### **STEP 4: Push to Remote (ENGINEER SHARD)**

**MUST** push new branch to remote repository:

```bash
git push -u origin my-new-feature
```

**ENGINEER shard validation:**
- Establish upstream tracking
- Confirm remote push success
- Verify branch visibility

---

## Safety Mechanisms & Error Handling

### Stash Safety Protocol (JANITOR SHARD)

When Git refuses branch switch due to conflicts:

```bash
# Step 1: Stash changes safely
git stash

# Step 2: Create and switch to new branch
git checkout -b my-new-feature

# Step 3: Restore stashed changes
git stash pop
```

**JANITOR shard responsibilities:**
- Detect conflict scenarios
- Execute stash operations safely
- Verify complete change restoration
- Clean up stash after successful restoration

### Conflict Resolution (EXPERT CODER SHARD)

**MUST** handle merge conflicts intelligently:
- Identify conflicting files
- Provide resolution strategies
- Maintain code integrity
- Document conflict resolution

---

## Brain Architecture Integration

### Memory Storage Locations

**Workflow execution stored in:**
```
brain/parallel-shards/
├── architect.md          # Branch analysis patterns
├── engineer.md            # Git command sequences
├── janitor.md             # Conflict resolution logs
└── expert-coder.md        # Best practice repositories
```

**Learning capture in:**
```
brain/texture-memory/longtime/
├── git-workflow-patterns.md    # Successful workflow patterns
├── conflict-resolutions.md     # Resolved conflict scenarios
└── branch-strategies.md        # Effective branching strategies
```

### Cross-Shard Learning

**ARCHITECT shard learns:**
- Optimal branch naming conventions
- Common workflow patterns
- Project-specific branching strategies

**ENGINEER shard learns:**
- Command sequence optimizations
- Error recovery procedures
- Remote interaction patterns

**JANITOR shard learns:**
- Conflict prevention techniques
- Working directory maintenance
- Stash operation best practices

---

## Verification & Quality Assurance

### Pre-Execution Checklist

**Before executing workflow, MUST verify:**

<thinking>
✓ Current branch identified correctly?
✓ Uncommitted changes inventory complete?
✓ Target branch name available?
✓ Remote repository accessible?
✓ Sufficient permissions for push operations?
</thinking>

### Post-Execution Validation

**After workflow completion, MUST confirm:**

```bash
# Verify new branch is active
git branch --show-current

# Confirm all changes committed
git status

# Verify remote tracking established
git branch -vv

# Confirm push success
git log --oneline -n 1
```

---

## Advanced Workflow Patterns

### Feature Branch Strategy

**ARCHITECT shard recommends:**
- `feature/description` naming convention
- Include ticket numbers when applicable
- Keep branch names descriptive but concise
- Consider team branching standards

### Hotfix Workflow

**For urgent fixes to main:**
```bash
# Create hotfix branch from main
git checkout -b hotfix/critical-fix main

# Make and commit fixes
git add .
git commit -m "hotfix: critical security fix"

# Push and create PR
git push -u origin hotfix/critical-fix
```

### Experimental Branch Workflow

**For experimental features:**
```bash
# Create experimental branch
git checkout -b experiment/feature-name

# Work with frequent commits
git add .
git commit -m "experiment: initial prototype"

# Push for collaboration
git push -u origin experiment/feature-name
```

---

## Integration with Continuous Learning

**Workflow insights captured in:**
- `memory-bank/raw_reflection_log.md` - Detailed execution logs
- `memory-bank/consolidated_learnings.md` - Optimized patterns
- `brain/texture-memory/longtime/git-workflow-patterns.md` - Reusable strategies

**Continuous improvement through:**
- Pattern recognition across projects
- Conflict resolution optimization
- Command sequence refinement
- Team workflow adaptation

---

## Error Recovery Procedures

### Common Failure Modes

**Branch creation fails:**
- Check for existing branch name
- Verify repository permissions
- Confirm remote connectivity

**Push operations fail:**
- Verify remote repository URL
- Check authentication credentials
- Confirm branch exists locally

**Stash operations fail:**
- Check for merge conflicts
- Verify clean working directory
- Confirm Git repository integrity

### Recovery Commands

**Reset to safe state:**
```bash
# Reset to last commit if needed
git reset --hard HEAD

# Clean untracked files
git clean -fd

# Restore from stash if needed
git stash list
git stash apply stash@{0}
```

---

```
BRAIN ARCHITECTURE GIT WORKFLOW
Version: 1.0
Primary Shards: ARCHITECT, ENGINEER, JANITOR, EXPERT CODER
Integration: Full brain architecture coordination
Learning: Continuous pattern optimization
```

*intelligent branching*  
*automated safety*  
*continuous learning*  
*workflow evolution*
```

This Git workflow rule integrates with your brain architecture system, using the cognitive shards to handle branch management intelligently while providing comprehensive safety mechanisms and continuous learning capabilities. [3](#67-2) 

## Notes

The rule follows the established behavioral/instructional pattern with directive language and verification steps [1](#67-0)  while integrating seamlessly with the brain architecture's cognitive shard coordination system. The workflow captures learnings in the memory bank for continuous improvement across sessions. [4](#67-3) 

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

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

**File:** clinerules/cline-continuous-improvement-protocol.md (L10-16)
```markdown
**Objective:** Ensure Cline proactively learns from tasks, captures knowledge in a structured way, **distills fundamental insights,** refines understanding, and improves efficiency and reliability. This protocol maintains two key files: `memory-bank/raw_reflection_log.md` for initial detailed logging, and `memory-bank/consolidated_learnings.md` for pruned, actionable, long-term knowledge. This is vital for optimal performance and avoiding redundant effort.

**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.
```
