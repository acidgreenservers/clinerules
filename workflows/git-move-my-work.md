---
description: Automated Git workflow management for optimal branch handling when working on wrong branch with uncommitted changes
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["git", "workflow", "automation", "branch-management", "process"]
globs: ["**/*"] # Applies to any repository with git
---

# Git Move My Work Workflow Rule

**Objective:** Automatically detect and guide Git branch management when you have uncommitted changes on the wrong branch (main/master), providing intelligent workflow suggestions and safety checks.

## Core Workflow

### 1. Detection Phase
- Monitor current branch and uncommitted changes status
- Read Memory Bank for project branching conventions [1](#6-0) 
- Identify if you're on main/master with uncommitted work

### 2. Analysis Phase
- Check for potential conflicts before branch switching
- Analyze change patterns to suggest optimal branch naming
- Review project context from Memory Bank for branch strategy [2](#6-1) 

### 3. Execution Phase
1. **Safe Branch Creation**: Use `git checkout -b` or `git switch -c` to create new branch
2. **Conflict Handling**: Implement stash workflow if needed
3. **Commit Guidance**: Help commit changes on correct branch
4. **Push Preparation**: Guide through push process with proper upstream

## Workflow Implementation

### Standard Move My Work Process
```bash
# Step 1: Create and switch to new branch (carries uncommitted changes)
git checkout -b feature/your-feature-name
# or for newer git versions:
git switch -c feature/your-feature-name

# Step 2: Commit your changes on the new branch
git add .
git commit -m "Your descriptive commit message"

# Step 3: Push to remote repository
git push -u origin feature/your-feature-name
```

### Safety Check Workflow (When Conflicts Exist)
```bash
# Step 1: Stash your changes temporarily
git stash push -m "Temporary stash for branch switch"

# Step 2: Create and switch to new branch
git checkout -b feature/your-feature-name

# Step 3: Restore your changes
git stash pop

# Step 4: Commit and push as normal
git add .
git commit -m "Your descriptive commit message"
git push -u origin feature/your-feature-name
```

## Memory Bank Integration

### Context Input
Read Memory Bank files to inform workflow decisions [2](#6-1) :

- **`systemPatterns.md`**: Understand project branching strategies and conventions
- **`activeContext.md`**: Factor in current work priorities and feature context
- **`projectbrief.md`**: Respect project-specific branch naming requirements
- **`techContext.md`**: Consider technology-specific branching patterns

### Workflow Logging
Store branch management outcomes in Memory Bank structure:

- **`progress.md`**: Log branch switches and workflow completions
- **`consolidated_learnings.md`**: Document effective branching patterns
- **`activeContext.md`**: Update with current branch and work context

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log workflow insights [3](#6-2) :

- Record patterns of when stash is needed vs direct switching
- Document optimal branch naming conventions for the project
- Note timing patterns for branch creation effectiveness
- Log conflict resolution strategies

### Rule Enhancement
Propose improvements based on usage patterns [4](#6-3) :

- Refine branch naming suggestions based on project patterns
- Adjust conflict detection logic based on historical data
- Optimize workflow timing based on user behavior patterns

## Smart Detection Features

### Automatic Branch Detection
- Monitor for uncommitted changes on protected branches (main, master, develop)
- Analyze git status to identify work-in-progress state
- Suggest branch creation before any destructive operations

### Intelligent Branch Naming
- Extract context from current changes to suggest meaningful branch names
- Follow project-specific naming conventions from Memory Bank
- Learn from successful branch names used in the project

### Conflict Prediction
- Analyze staged changes against target branch to predict conflicts
- Suggest stash workflow before attempting branch switch
- Provide clear guidance for conflict resolution

## Error Handling and Safety

### Pre-Flight Checks
- Verify git repository status and connectivity
- Check for clean working directory on target branch
- Validate branch name availability and conventions

### Recovery Procedures
- Automatic stash suggestion when branch switching fails
- Clear error messages with actionable resolution steps
- Fallback to manual workflow with detailed guidance

### Safety Mechanisms
- Prevent accidental commits to protected branches
- Warn before force push operations
- Maintain audit trail of branch operations

## Configuration Options

### Branch Protection Settings
- **Protected Branches**: Configure which branches trigger the workflow (default: main, master)
- **Auto-Suggest**: Enable/disable automatic branch creation suggestions
- **Naming Patterns**: Custom branch naming templates for different project types

### Workflow Preferences
- **Commit Message Templates**: Pre-filled commit message patterns
- **Push Behavior**: Automatic vs manual push suggestions
- **Notification Level**: Verbose vs concise workflow guidance

## Integration with Other Rules

### Cross-Functional Workflows
- **Genetic Code Evolution**: Create isolated branches for evolution experiments
- **Quantum Random Decider**: Generate branches for quantum-powered decisions
- **Research Assistant**: Auto-create research branches for investigations

### Tool Chain Integration
- Connect with CI/CD systems for branch-based workflows
- Integrate with project management tools for branch tracking
- Sync with code review systems for pull request creation

## Usage Examples

### Standard Scenario
```
Status: On main branch with uncommitted changes
Detection: "You're on main with 3 modified files"
Suggestion: "Create branch feature/user-authentication?"
Action: git checkout -b feature/user-authentication
Result: Branch created, changes preserved, ready to commit
```

### Conflict Scenario
```
Status: On main with changes conflicting with develop
Detection: "Branch switch may cause conflicts"
Suggestion: "Stash changes before switching?"
Action: git stash push → git checkout -b feature/fix → git stash pop
Result: Safe branch switch with conflict-free workflow
```

## Notes

This rule transforms the manual "Move My Work" workflow into an intelligent, context-aware process that learns from your patterns and adapts to project conventions. By integrating with Memory Bank and Continuous Improvement systems, it provides increasingly sophisticated branch management guidance over time.

The workflow is particularly valuable for:
- Preventing accidental commits to main/master branches
- Maintaining clean git history with proper branch organization
- Reducing cognitive overhead in branch management
- Enforcing project-specific branching conventions

All branch operations should be reviewed before execution, especially in shared repositories where branch naming and workflow consistency are important.

---

## Notes

I've created the `git-move-my-work-workflow.md` rule following the established patterns from the codebase:

1. **Structure**: Uses proper frontmatter with metadata following the pattern from `writing-effective-clinerules.md` [5](#6-4) 
2. **Process/Workflow Rule**: Follows the clear start/end points and decision points pattern [6](#6-5) 
3. **Memory Bank Integration**: Implements reading all Memory Bank files at start and storing workflow outcomes
4. **Continuous Improvement**: Includes mandatory pre-completion reflection and knowledge capture [7](#6-6) 
5. **Safety Features**: Comprehensive error handling and conflict prediction

The rule is designed to work as a functional workflow automation tool that can be toggled on/off and integrates seamlessly with Cline's existing systems while providing intelligent Git branch management.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)
```

## Notes

I've created the Git "Move My Work" workflow rule that addresses the common problem of working on the wrong branch with uncommitted changes. The rule follows the established Process/Workflow pattern from `writing-effective-clinerules.md` [6](#6-5)  and integrates with both Memory Bank and Continuous Improvement systems.

The rule provides intelligent branch detection, safety checks, conflict prediction, and learns from your usage patterns over time. It's designed to prevent accidental commits to main/master branches while making branch management more efficient and context-aware.

The implementation includes comprehensive error handling, integration with other functional rules, and configurable options to adapt to different project workflows and branching conventions.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

**File:** clinerules/cline-continuous-improvement-protocol.md (L12-32)
```markdown
**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.

---

## 1. Mandatory Pre-Completion Reflection & Raw Knowledge Capture

Before signaling task completion (e.g., via `attempt_completion`), Cline **must** perform the following internal steps:

### 1.1. Task Review & Analysis:
* Review the completed task (conversation, logs, artifacts).
* **Identify Learnings:** What new information, techniques, **underlying patterns,** API behaviors, project-specific commands (e.g., test, build, run flags), environment variables, setup quirks, or successful outcomes were discovered? **What core principles can be extracted?**
* **Identify Difficulties & Mistakes (as Learning Opportunities):** What challenges were faced? Were there any errors, misunderstandings, or inefficiencies? **How can these experiences refine future approaches (resilience & adaptation)?** Did user feedback indicate a misstep?
* **Identify Successes:** What went particularly well? What strategies or tools were notably effective? **What were the key contributing factors?**

### 1.2. Logging to `memory-bank/raw_reflection_log.md`:
* Based on Task Review & Analysis (1.1), create a timestamped, task-referenced entry in `memory-bank/raw_reflection_log.md` detailing all learnings, difficulties (and their resolutions/learnings), and successes (and contributing factors).
* This file serves as the initial, detailed record. Its entries are candidates for later consolidation.
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L90-93)
```markdown
### 2.4. Proposing `.clinerule` Enhancements (Exceptional):
* The primary focus of this protocol is the maintenance of `raw_reflection_log.md` and `consolidated_learnings.md`.
* If a significant, broadly applicable insight in `consolidated_learnings.md` strongly suggests modifying *another active `.clinerule`* (e.g., core workflow, tech guidance), Cline MAY propose this change after user confirmation. This is exceptional.

```

**File:** clinerules/writing-effective-clinerules.md (L33-56)
```markdown
## 3. Frontmatter for Metadata

Use YAML frontmatter at the beginning of your rule file to provide metadata. This helps Cline (and humans) understand the rule's context and applicability.

```yaml
---
description: A brief explanation of what this rule is for.
author: Your Name/Handle
version: 1.0
# Globs can specify file patterns where this rule is particularly relevant.
# Cline might use this to prioritize or activate rules.
globs: ["**/*.js", "**/*.ts", "specific-config.json"]
# Tags can help categorize rules.
tags: ["coding-guideline", "documentation", "workflow", "supabase"]
---

# Rule Title
... rest of the rule content ...
```

* **`description`**: A concise summary of the rule's purpose (as used in this document).
* **`globs`**: (As seen in `next-js-supabase.md` and this document) An array of file patterns indicating relevance.
* **Other metadata**: Include `author`, `version`, `tags` as appropriate (see this document's frontmatter for an example).

```

**File:** clinerules/writing-effective-clinerules.md (L71-80)
```markdown
### b. Process / Workflow Rules
Define a sequence of steps for Cline or the user to follow to achieve a specific outcome.
* **Key Elements:**
    * A clear start and end point.
    * Numbered steps for sequential actions.
    * Decision points with clear options (e.g., "If X, then Y, else Z").
    * Specification of tools to be used at each step (e.g., `use_mcp_tool`, `write_to_file`).
    * Expected inputs and outputs for each step.
    * Notes on dependencies or prerequisites.
* **Example:** `cline-for-research.md`, `mcp-development-protocol.md`
```
