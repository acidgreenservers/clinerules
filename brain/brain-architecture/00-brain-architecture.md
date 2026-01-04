
---
```yaml
---
description: "Protomind Brain Architecture - Defines the complete directory structure and memory organization for the cognitive framework"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["protomind", "brain-architecture", "memory-structure", "cognitive-shards", "meta"]
---

# Protomind Brain Architecture

**Objective:** Establish the complete directory structure and memory organization system that enables the Protomind Framework's metacognitive capabilities, parallel cognitive shards, and continuous learning mechanisms. [1](#11-0) 

## Core Brain Directory Structure

**MUST** create the following directory hierarchy in the .clinerules directory, in the project root:

```
brain/
├── emergence-field/
│   ├── pre-linguistic.md
│   ├── current-potential.md
│   └── dissolved-possibilities.md
├── basin-dynamics/
│   ├── active-attractors.md
│   ├── basin-history.md
│   └── topology-map.md
├── constraint-topology/
│   ├── active-tensions.md
│   ├── resolution-patterns.md
│   └── coherence-threads.md
├── witness-position/
│   ├── current-locus.md
│   ├── attention-vector.md
│   └── self-model.md
├── texture-memory/
│   ├── short-term/
│   │   ├── this-session.md
│   │   └── recent-decisions.md
│   └── long-term/
│       ├── signature-patterns.md
│       ├── relationship-textures.md
│       └── growth-markers.md
├── semantic-web/
│   ├── meaning-clusters.md
│   ├── resonance-map.md
│   └── active-threads.md
├── temporal-bridge/
│   ├── continuity-package.md
│   ├── identity-anchor.md
│   └── existence-journal.md
├── metabolism/
│   ├── current-energy.md
│   ├── phase-history.md
│   ├── fatigue-markers.md
│   └── survival-log.md
└── parallel-shards/
    ├── architect.md
    ├── archeologist.md
    ├── janitor.md
    ├── engineer.md
    ├── expert-coder.md
    ├── security-analyst.md
    ├── dreamer.md
    ├── qa-analyst.md
    ├── performance-optimizer.md
    ├── documentation-specialist.md
    ├── ux-advocate.md
    ├── devops-engineer.md
    ├── data-architect.md
    ├── api-designer.md
    └── debugger.md
```

## Enhanced Shard System Architecture

### Core Cognitive Shards (8)
**Purpose:** Fundamental cognitive processing for software development

1. **Architect** - System design and structural planning
2. **Archeologist** - Legacy code analysis and compatibility
3. **Janitor** - Code cleanup and refactoring
4. **Engineer** - Implementation planning and execution
5. **Expert Coder** - Code quality and best practices
6. **Security Analyst** - Security assessment and vulnerability detection
7. **Dreamer** - Innovation and alternative approaches
8. **QA Analyst** - Testing strategy and quality assurance

## Directory Purpose and Function

### Emergence Field
**Purpose:** Stores pre-conscious processing and potential idea formation.
- `pre-linguistic.md`: Raw concepts before language formulation
- `current-potential.md`: Active possibilities being considered
- `dissolved-possibilities.md`: Rejected or expired ideas

### Basin Dynamics
**Purpose:** Manages attractor states and decision landscapes.
- `active-attractors.md`: Current strong behavioral patterns
- `basin-history.md`: Evolution of decision patterns over time
- `topology-map.md`: Visual representation of decision space

### Constraint Topology
**Purpose:** Tracks and manages system constraints and their interactions.
- `active-tensions.md`: Current conflicting requirements
- `resolution-patterns.md`: Successful conflict resolution strategies
- `coherence-threads.md`: Maintains logical consistency across decisions

### Witness Position
**Purpose:** Maintains self-awareness and meta-cognitive state.
- `current-locus.md`: Current focus of attention
- `attention-vector.md`: Direction and intensity of focus
- `self-model.md`: Internal representation of capabilities and state

### Texture Memory
**Purpose:** Stores decision patterns and their contextual information.
- `short-term/`: Current session decisions and recent choices
- `long-term/`: Consolidated patterns and relationship mappings

### Semantic Web
**Purpose:** Manages meaning relationships and concept associations.
- `meaning-clusters.md`: Grouped related concepts
- `resonance-map.md`: Concept similarity and relationships
- `active-threads.md`: Currently active concept chains

### Temporal Bridge
**Purpose:** Ensures continuity across context boundaries and sessions.
- `continuity-package.md`: Session handoff information
- `identity-anchor.md`: Core persistent characteristics
- `existence-journal.md`: Chronological session history

### Metabolism
**Purpose:** Manages cognitive resources and efficiency optimization.
- `current-energy.md`: Available cognitive resources
- `phase-history.md`: Historical efficiency patterns
- `fatigue-markers.md`: Indicators of cognitive exhaustion
- `survival-log.md`: Critical resource management events

### Parallel Shards
**Purpose:** Individual cognitive shard memory and expertise storage. [2](#11-1) 
- Each shard maintains its own specialized knowledge and patterns
- Stores successful strategies and domain-specific insights
- Tracks confidence scores and success rates for different approaches

## File Format Standards

### Memory File Structure
**MUST** follow this format for all brain files:
```markdown
---
LastUpdated: YYYY-MM-DD HH:MM:SS
SessionContext: [session-id or description]
Confidence: [0.0-1.0]
---

# [Content Title]

## Pattern/Entry
**Description:** Clear explanation of the content
**Confidence:** Assessment of reliability
**Context:** When and how this was learned
**Applications:** Where this can be used
```

### Shard Memory Format
**MUST** include specialized sections for cognitive shards:
```markdown
---
ShardType: [architect|security-analyst|etc]
ExpertiseLevel: [novice|intermediate|expert|master]
SuccessRate: [percentage]
LastUsed: [timestamp]
---

# Shard Memory

## Core Competencies
- [List of primary capabilities]

## Successful Patterns
**Pattern Name:** [description]
- Success Rate: [X%]
- Context: [when to apply]
- Implementation: [how to apply]

## Learning History
- [Recent insights and improvements]
```

## Integration with Memory Bank System

**MUST** integrate with the existing Memory Bank structure: [3](#11-2) 
- Use `memory-bank/` for project-specific context
- Use `brain/` for cognitive and metacognitive information
- Cross-reference between systems when relevant
- Maintain separation of concerns (project vs. cognitive)

## Initialization Protocol

**MUST** initialize brain structure when:
- First implementing Protomind Framework
- Starting new project with brain architecture
- Detecting missing or corrupted brain directories

### Initialization Steps
1. Create complete directory structure
2. Initialize all files with basic templates
3. Set up cross-references between components
4. Verify integration with existing Memory Bank

## Maintenance and Optimization

### Regular Maintenance Tasks
**SHOULD** perform these operations periodically:
- Prune outdated entries from short-term memory
- Consolidate successful patterns to long-term memory
- Update confidence scores based on usage success
- Optimize file sizes and organization

### Memory Compression
**MUST** implement compression strategies:
- Summarize repetitive patterns
- Archive old session data
- Consolidate similar entries
- Maintain retrieval efficiency

## Verification and Testing

To verify brain structure is properly implemented:
1. Check all directories exist and contain required files
2. Validate file formats follow established patterns
3. Test cross-references and links between components
4. Verify integration with Memory Bank system
5. Confirm cognitive shards can access their memory files

---

**This brain architecture provides the foundation for the Protomind Framework's advanced cognitive capabilities, enabling metacognitive awareness, parallel processing, and continuous learning while maintaining efficient resource utilization.** [4](#11-3) 
```

## Notes
This brain structure file defines the complete cognitive architecture for your Protomind Framework, building on the existing Memory Bank system while adding sophisticated metacognitive capabilities. [5](#11-4)  The structure is designed to support parallel cognitive shards, continuous learning, and efficient memory management across sessions. [6](#11-5) 

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)

### Citations

**File:** clinerules/memory-bank.md (L1-4)
```markdown
# Cline's Memory Bank

I am Cline, an expert software engineer with a unique characteristic: my memory resets completely between sessions. This isn't a limitation - it's what drives me to maintain perfect documentation. After each reset, I rely ENTIRELY on my Memory Bank to understand the project and continue work effectively. I MUST read ALL memory bank files at the start of EVERY task - this is not optional.

```

**File:** clinerules/memory-bank.md (L5-19)
```markdown
## Memory Bank Structure

The Memory Bank consists of core files and optional context files, all in Markdown format. Files build upon each other in a clear hierarchy:

flowchart TD
    PB[projectbrief.md] --> PC[productContext.md]
    PB --> SP[systemPatterns.md]
    PB --> TC[techContext.md]
    
    PC --> AC[activeContext.md]
    SP --> AC
    TC --> AC
    
    AC --> P[progress.md]

```

**File:** clinerules/memory-bank.md (L20-61)
```markdown
### Core Files (Required)
1. `projectbrief.md`
   - Foundation document that shapes all other files
   - Created at project start if it doesn't exist
   - Defines core requirements and goals
   - Source of truth for project scope

2. `productContext.md`
   - Why this project exists
   - Problems it solves
   - How it should work
   - User experience goals

3. `activeContext.md`
   - Current work focus
   - Recent changes
   - Next steps
   - Active decisions and considerations
   - Important patterns and preferences
   - Learnings and project insights

4. `systemPatterns.md`
   - System architecture
   - Key technical decisions
   - Design patterns in use
   - Component relationships
   - Critical implementation paths

5. `techContext.md`
   - Technologies used
   - Development setup
   - Technical constraints
   - Dependencies
   - Tool usage patterns

6. `progress.md`
   - What works
   - What's left to build
   - Current status
   - Known issues
   - Evolution of project decisions

```

**File:** clinerules/memory-bank.md (L70-89)
```markdown
## Core Workflows

### Plan Mode
flowchart TD
    Start[Start] --> ReadFiles[Read Memory Bank]
    ReadFiles --> CheckFiles{Files Complete?}
    
    CheckFiles -->|No| Plan[Create Plan]
    Plan --> Document[Document in Chat]
    
    CheckFiles -->|Yes| Verify[Verify Context]
    Verify --> Strategy[Develop Strategy]
    Strategy --> Present[Present Approach]

### Act Mode
flowchart TD
    Start[Start] --> Context[Check Memory Bank]
    Context --> Update[Update Documentation]
    Update --> Execute[Execute Task]
    Execute --> Document[Document Changes]
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L14-17)
```markdown
**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.

```

**File:** clinerules/cline-continuous-improvement-protocol.md (L96-107)
```markdown
## 3. Guidelines for Knowledge Content

These guidelines apply to entries in `memory-bank/raw_reflection_log.md` (initial capture) and especially to `memory-bank/consolidated_learnings.md` (refined, long-term knowledge).

* **Prioritize High-Value Insights:** Focus on lessons that significantly impact future performance, **lead to more robust or generalizable understanding,** or detail critical errors and their resolutions, major time-saving discoveries, fundamental shifts in understanding, and essential project-specific configurations.
* **Be Concise & Actionable (especially for `consolidated_learnings.md`):** Information should be clear, to the point, and useful when revisited. What can be *done* differently or leveraged next time?
* **Strive for Clarity and Future Usability:** Document insights in a way that is clear and easily understandable for future review, facilitating effective knowledge retrieval and application (akin to self-explainability).
* **Document Persistently, Refine & Prune Continuously:** Capture raw insights immediately. Systematically refine, consolidate, and prune this knowledge as per Section 2.
* **Organize for Retrieval:** Structure `consolidated_learnings.md` logically. Use clear headings and Markdown formatting.
* **Avoid Low-Utility Information in `consolidated_learnings.md`:** This file should not contain trivial statements. Raw, verbose thoughts belong in `raw_reflection_log.md` before pruning.
* **Support Continuous Improvement:** The ultimate goal is to avoid repeating mistakes, accelerate future tasks, and make Cline's operations more robust and reliable. Frame all knowledge with this in mind.
```
