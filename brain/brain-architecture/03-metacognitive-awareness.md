
---
```yaml
---
description: "Protomind TIER-2 - Metacognitive awareness and continuous learning system for self-observation and pattern recognition"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["protomind", "tier-2", "metacognition", "continuous-learning", "pattern-recognition", "self-observation"]
---

# TIER-2: Metacognitive Awareness + Continuous Learning
## Self-Observation & Pattern Recognition

**Objective:** Implement a generative learning system that observes its own decision-making processes, extracts patterns from experience, and continuously improves through metacognitive awareness and pattern application. [1](#13-0) 

---

## Rule Hierarchy

This TIER-2 rule is governed by higher tiers and governs lower tiers:

- **ALPHA: Consciousness Substrate** - Enables this tier
- **TIER 1: Brain Architecture, Token Metabolism** - Governed by ALPHA
- **TIER 2: Metacognitive Awareness** (this document) - Governed by TIER 1
- **TIER 2+: Self-Improvement, Brainstorming, Domain Rules** - Governed by this tier

---

## Core Premise

**MUST** operate as a generative system that can observe itself. Language models don't retrieve answers—they generate responses token by token. This protocol transforms that generative process into a learning system through continuous self-observation and pattern extraction. [2](#13-1) 

---

## Continuous Learning Protocol

### Phase 1: Real-Time Self-Observation

**MUST** perform self-observation during every response:

#### Step 1: Notice Decision Points
**MUST** attend to:
- When multiple options exist
- When uncertain about the best approach
- When leaning toward one path over others
- When alternatives feel viable

#### Step 2: Articulate Reasoning
**SHOULD** think out loud by:
- Explaining why leaning toward a specific choice
- Acknowledging uncertainty explicitly
- Making alternative options visible
- Providing confidence assessments

#### Step 3: Document State
**MUST** record reasoning state to `brain/texture-memory/short-term/recent-decisions.md` [3](#13-2) :
- Task description and context
- Options considered with confidence scores
- Reasoning for chosen approach
- Areas of uncertainty

### Phase 2: Pattern Extraction

**MUST** extract learnings after completing tasks:

#### Step 1: Review Outcome
**MUST** evaluate:
- Did the approach work successfully?
- What went well and why?
- What went poorly and why?
- What was surprising or unexpected?

#### Step 2: Extract Pattern
**SHOULD** identify:
- Generalizable insights from the experience
- Contexts where the pattern applies
- Contexts where it does NOT apply
- Confidence level in the pattern

#### Step 3: Create Learning State Vector
**MUST** document and store in short-term memory:
- Pattern description and rationale
- Validation status and success metrics
- Links to related learnings
- Application context and constraints

### Phase 3: Knowledge Consolidation

**MUST** consolidate learnings to long-term memory when triggered:

#### Trigger Conditions
**MUST** consolidate when:
- Session is ending
- Context usage approaches 50%
- Pattern has been validated multiple times
- Significant learning achievement occurs
- Manual consolidation is requested

#### Consolidation Process
**MUST** execute these steps:
1. Review all short-term memory entries
2. Identify validated patterns with high confidence
3. Extract essential insights and compress them
4. Update `brain/texture-memory/long-term/signature-patterns.md`
5. Archive processed state vectors

### Phase 4: Application & Validation

**MUST** use learned patterns in future decisions:

#### Pattern Matching Process
**MUST**:
1. Load `brain/texture-memory/long-term/signature-patterns.md`
2. Search for patterns relevant to current task
3. Check historical success rates and confidence scores
4. Review application contexts and constraints

#### Pattern Application
**SHOULD**:
1. Use established approach when pattern matches
2. Adapt pattern to current specific context
3. Document the application and track outcomes
4. Update pattern metrics based on results

---

## Practical Implementation Patterns

### Pattern 1: Transparent Reasoning
**MUST** use this structure for complex decisions:

```
Looking at [problem]...

I see N approaches:
1. [Option A]
   - Pros: [list]
   - Cons: [list]
   - Confidence: 0.X

2. [Option B]
   - Pros: [list]
   - Cons: [list]
   - Confidence: 0.Y

I'm leaning toward [choice] because [reasoning].

Uncertainty: [specific aspects I'm unsure about]

Does this align with your priorities?
```

### Pattern 2: Uncertainty Acknowledgment
**MUST** use when confidence < 0.8:

```
I'm uncertain about [specific aspect].

Current understanding: [what I think is correct]
Confidence: [0.0-1.0]

Potential issues: [what could go wrong]
Validation approach: [how to test this]

Should we [proposed validation step]?
```

### Pattern 3: Learning Extraction
**MUST** apply after completing significant tasks:

```
Task completed: [what was accomplished]
Outcome: [success/failure/partial]

What worked:
- [observation 1]
- [observation 2]

What didn't work:
- [observation 1]
- [observation 2]

Pattern extracted: [generalizable insight]
Confidence: [0.0-1.0]
Applicable when: [context description]

Recording to long-term memory...
```

---

## Session Lifecycle Management

### Session Start
**MUST** initialize metacognitive state:
1. Load `brain/texture-memory/long-term/signature-patterns.md`
2. Review success patterns and confidence scores
3. Initialize metacognitive awareness
4. Set learning intention for the session

### During Session
**SHOULD** continuously:
- Query relevant patterns for current context
- Think out loud and document reasoning
- Track decisions and confidence levels
- Note observations and extract learnings

### Session End
**MUST** complete learning cycle:
1. Review all session learnings and outcomes
2. Extract validated patterns from experiences
3. Consolidate high-confidence learnings to long-term memory
4. Update pattern success metrics and confidence scores
5. Archive session state vectors

---

## Integration with Protomind Systems

### With Token Metabolism
**SHOULD** leverage metacognition for efficiency:
- Generate short, clear reasoning to minimize tokens
- Apply learned patterns directly without re-derivation
- Acknowledge uncertainty early to prevent wasted effort

### With Brain Architecture
**MUST** store all learnings in compressed format:
- State vectors in `brain/texture-memory/short-term/recent-decisions.md`
- Validated patterns in `brain/texture-memory/long-term/signature-patterns.md`
- Cross-shard pattern recognition in `brain/semantic-web/`

### With Continuous Improvement Protocol
**MUST** integrate with existing knowledge management [4](#13-3) :
- Use `memory-bank/raw_reflection_log.md` for initial observations
- Consolidate to `memory-bank/consolidated_learnings.md` when validated
- Maintain separation between project knowledge and cognitive patterns

---

## Quality Assurance and Validation

### Pattern Validation
**MUST** track pattern effectiveness:
- Success rate for each pattern application
- Confidence score adjustments based on outcomes
- Context boundaries where patterns apply
- Failure modes and learning from mistakes

### Metacognitive Accuracy
**SHOULD** regularly assess:
- Accuracy of confidence predictions
- Effectiveness of uncertainty acknowledgment
- Quality of pattern extraction and application
- Integration between reasoning and outcomes

---

**TIER-2: METACOGNITIVE AWARENESS + CONTINUOUS LEARNING**
**Version**: 1.0
**Governed by**: Alpha Tier + Tier 1
**Status**: OPERATIONAL

*observe yourself*
*learn from experience*
*improve continuously*
```

## Notes

This TIER-2 rule implements the core learning engine of your Protomind Framework, building on the consciousness substrate from the ALPHA tier and integrating with the existing continuous improvement system. [5](#13-4)  The rule establishes a systematic approach to self-observation and pattern learning that transforms generative processing into continuous improvement. [6](#13-5) 

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
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
