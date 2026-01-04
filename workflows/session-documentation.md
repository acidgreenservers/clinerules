
```yaml
---
description: "Session Documentation Workflow - Automatically proposes documenting session changes to project documentation and changelog files"
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
globs: ["*"]
tags: ["workflow", "documentation", "continuous-improvement", "protomind", "session-management"]
---

# Session Documentation & Changelog Workflow

**Objective:** Implement an intelligent workflow that automatically proposes documenting session changes to project documentation files and maintains a comprehensive changelog, triggered at session boundaries. [1](#10-0) 

## Core Workflow Requirements

### Trigger Conditions
**MUST** propose documentation when:
- User indicates session completion ("done", "finished", "that's all")
- User starts a new major task that may affect project structure
- Significant changes have been made to the codebase
- New features, APIs, or configurations have been added

### Documentation Targets
**MUST** evaluate and propose updates to:
- `README.md` - Project overview, setup instructions, usage examples
- `CONTRIBUTING.md` - Development guidelines, contribution process
- `SECURITY.md` - Security policies, vulnerability reporting
- `CHANGELOG.md` or `CHANGELOG` - Version history and changes
- Any identified changelog files in the project root

## Session Analysis Process

### 1. Change Detection
**MUST** perform comprehensive analysis:
- Scan all modified, added, or deleted files during the session
- Identify API changes, new dependencies, configuration updates
- Detect breaking changes or new features
- Review documentation file modifications

### 2. Impact Assessment
**SHOULD** categorize changes by impact level:
- **Critical**: Breaking changes, security updates, major features
- **Significant**: New APIs, configuration changes, documentation updates
- **Minor**: Bug fixes, small improvements, code refactoring

### 3. Documentation Proposal Generation
**MUST** generate specific proposals for each relevant file:

#### README.md Updates
- New feature descriptions and usage examples
- Updated installation or setup instructions
- Modified configuration requirements
- New dependency information

#### CONTRIBUTING.md Updates
- New development workflows or tools
- Updated testing procedures
- Modified build or deployment processes
- New coding standards or conventions

#### SECURITY.md Updates
- New security considerations or policies
- Updated vulnerability reporting procedures
- Security-related configuration changes
- Authentication or authorization changes

#### CHANGELOG Updates
- Structured entries following semantic versioning
- Clear descriptions of added, changed, deprecated, removed, fixed, or security items
- Proper formatting and organization

## User Interaction Protocol

### Proposal Presentation
**MUST** present documentation proposal as:
```
I've detected the following changes during this session that may require documentation updates:

📋 Changes Summary:
- [List of key changes]

📝 Proposed Documentation Updates:
- README.md: [specific proposed changes]
- CONTRIBUTING.md: [specific proposed changes] 
- SECURITY.md: [specific proposed changes]
- CHANGELOG.md: [specific proposed changes]

Would you like me to proceed with updating these documentation files?
```

### User Response Handling
**MUST** handle user responses appropriately:
- **Yes/Proceed**: Implement all proposed documentation updates
- **Selective**: Update only specific files as requested
- **No/Skip**: Skip documentation updates for this session
- **Modify**: Adjust proposals based on user feedback

## Implementation Requirements

### Documentation Standards
**MUST** follow established documentation patterns:
- Use clear, consistent formatting
- Include proper code examples and syntax highlighting
- Maintain existing documentation style and tone
- Ensure all links and references are valid

### CHANGELOG Format
**SHOULD** follow standard changelog format:
```markdown
## [Unreleased]
### Added
- New feature descriptions

### Changed  
- Modified functionality descriptions

### Deprecated
- Features being deprecated

### Removed
- Removed functionality

### Fixed
- Bug fixes

### Security
- Security updates
```

### Integration with Continuous Improvement
**MUST** integrate with the existing continuous improvement system: [2](#10-1) 
- Log documentation patterns to `memory-bank/`
- Learn from successful documentation updates
- Improve proposal accuracy over time
- Track which types of changes require documentation

## Quality Assurance

### Validation Checks
**MUST** perform validation before proposing updates:
- Verify proposed changes are accurate and complete
- Check for consistency with existing documentation
- Ensure all technical details are correct
- Validate that examples actually work

### Error Handling
**SHOULD** handle potential issues gracefully:
- Missing documentation files (offer to create them)
- Permission issues (inform user of manual steps needed)
- Conflicting information (ask for clarification)
- Large changes (break into manageable sections)

## Configuration and Customization

### Project-Specific Settings
**MAY** support configuration for:
- Custom documentation file locations
- Project-specific changelog formats
- Preferred documentation styles
- Exclusion patterns for certain file types

### Integration with Protomind Framework
**SHOULD** leverage Protomind capabilities:
- Use metacognitive awareness to assess documentation importance
- Apply pattern learning from previous documentation updates
- Utilize parallel cognitive shards for comprehensive analysis
- Maintain context across session boundaries

## Verification and Testing

To verify the workflow is functioning correctly:
1. Make changes to a project during a session
2. Indicate session completion
3. Cline should propose relevant documentation updates
4. Test the proposal acceptance and implementation process
5. Verify that documentation files are updated correctly

---

**This workflow ensures that project documentation remains current and comprehensive, reducing the documentation burden on developers while maintaining high-quality project documentation standards.** [3](#10-2) 
```

## Notes
This workflow rule follows the established behavioral/instructional pattern from the codebase, using directive language (MUST/SHOULD) and integrating with the existing continuous improvement system. [4](#10-3)  The rule is designed to be additive and work alongside your existing Protomind Framework without conflicts. [5](#10-4) 

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

**File:** clinerules/cline-continuous-improvement-protocol.md (L10-16)
```markdown
**Objective:** Ensure Cline proactively learns from tasks, captures knowledge in a structured way, **distills fundamental insights,** refines understanding, and improves efficiency and reliability. This protocol maintains two key files: `memory-bank/raw_reflection_log.md` for initial detailed logging, and `memory-bank/consolidated_learnings.md` for pruned, actionable, long-term knowledge. This is vital for optimal performance and avoiding redundant effort.

**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L20-32)
```markdown
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

**File:** clinerules/writing-effective-clinerules.md (L93-99)
```markdown
### d. Meta-Rules
Rules that define how Cline manages or improves its own rules or processes.
* **Key Elements:**
    * Triggers for the meta-process.
    * Steps involved in the meta-process (e.g., reflection, suggesting improvements).
    * User interaction points (e.g., asking for confirmation).
* **Example:** `self-improving-cline.md`
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
