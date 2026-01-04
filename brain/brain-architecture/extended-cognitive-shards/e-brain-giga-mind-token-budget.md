

```yaml
---
description: "Brain Architecture Token Budget Context Engineering - Cognitive shard-driven context synthesis with strict token budget enforcement and intelligent truncation"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["token-budget", "context-engineering", "brain-architecture", "cognitive-shards", "truncation", "memory-optimization"]
---

# Brain Architecture Token Budget Context Engineering
## Cognitive Shard-Driven Context Synthesis with Budget Enforcement

**Objective:** Implement intelligent context engineering that automatically maintains accurate project "brain" files using cognitive shard analysis while enforcing strict token budget limits through intelligent truncation strategies. [1](#71-0) 

---

## Token Budget Configuration

**MUST** configure token budget before first run:

```yaml
# Token budget settings
MAX_TOKENS=4000        # User-adjustable hard cap (default: 4000)
TOKEN_RATIO=0.75       # Heuristic: 1 token ≈ 0.75 words
TRUNCATION_THRESHOLD=0.9  # Start truncating at 90% of budget
```

**SHOULD** adjust based on model:
- GPT-3.5: `MAX_TOKENS=2000`
- Claude: `MAX_TOKENS=6000` 
- GPT-4: `MAX_TOKENS=4000` (default)

---

## Cognitive Shard Context Analysis

**MUST** leverage cognitive shards for intelligent context prioritization: [2](#71-1) 

### Shard-Based Content Analysis
```yaml
Primary Shards for Context:
- architect: Component structure and relationships
- data-architect: Schema definitions and data flow
- api-designer: Endpoint specifications and contracts
- performance-optimizer: Critical performance indicators
- security-analyst: Security-relevant configurations
```

**MUST** analyze content through shard lenses to determine truncation priority:
1. **High Priority**: Core architecture, security-critical items
2. **Medium Priority**: API endpoints, component interfaces  
3. **Low Priority**: Detailed implementations, examples

---

## Token Budget Enforcement Workflow

### STEP 1: Raw Data Collection
**MUST** refresh source data after git commits affecting source files: [3](#71-2) 

```bash
# Discover source files
execute_command: find src lib apps packages -type f \( -name "*.js" -o -name "*.ts" -o -name "*.jsx" -o -name "*.tsx" -o -name "*.py" -o -name "*.go" \) 2>/dev/null | head -500 > .cline-context/file-tree.txt

# Track commit context
execute_command: git rev-parse --short HEAD > .cline-context/HEAD
```

### STEP 2: Full-Length Summary Generation
**MUST** generate complete summaries before budget enforcement:

```yaml
# Generate comprehensive summaries
write_to_file: .cline-context/COMPONENT_INDEX.full.md
write_to_file: .cline-context/API_ENDPOINTS.full.md  
write_to_file: .cline-context/DATA_SCHEMA.full.md
write_to_file: .cline-context/SECURITY_CONFIG.full.md
write_to_file: .cline-context/PERFORMANCE_METRICS.full.md
```

### STEP 3: Token Count Analysis
**MUST** calculate current token usage using word heuristic:

```bash
# Calculate token count (1 token ≈ 0.75 words)
execute_command: awk 'BEGIN{sum=0} {sum+=NF} END{print int(sum*0.75)}' \
  .cline-context/COMPONENT_INDEX.full.md \
  .cline-context/API_ENDPOINTS.full.md \
  .cline-context/DATA_SCHEMA.full.md \
  .cline-context/SECURITY_CONFIG.full.md \
  .cline-context/PERFORMANCE_METRICS.full.md > .cline-context/raw.tokens
```

### STEP 4: Intelligent Truncation Ladder
**MUST** enforce budget using shard-prioritized truncation:

```bash
# Budget enforcement with cognitive priorities
execute_command: |
  budget=$MAX_TOKENS
  over=$(cat .cline-context/raw.tokens)
  
  # Copy full versions to working files
  cp .cline-context/COMPONENT_INDEX.full.md .cline-context/COMPONENT_INDEX.md
  cp .cline-context/API_ENDPOINTS.full.md .cline-context/API_ENDPOINTS.md
  cp .cline-context/DATA_SCHEMA.full.md .cline-context/DATA_SCHEMA.md
  cp .cline-context/SECURITY_CONFIG.full.md .cline-context/SECURITY_CONFIG.md
  cp .cline-context/PERFORMANCE_METRICS.full.md .cline-context/PERFORMANCE_METRICS.md
  
  while [ $over -gt $budget ]; do
    # Priority 1: Truncate performance metrics (lowest priority)
    if [ $over -gt $((budget * 9 / 10)) ]; then
      head -n 20 .cline-context/PERFORMANCE_METRICS.md > tmp && echo "... truncated ..." >> tmp && mv tmp .cline-context/PERFORMANCE_METRICS.md
    fi
    
    # Priority 2: Truncate data schema details
    if [ $over -gt $((budget * 8 / 10)) ]; then
      awk 'NR<=30{print} NR==31{print "... truncated ..."}' .cline-context/DATA_SCHEMA.md > tmp && mv tmp .cline-context/DATA_SCHEMA.md
    fi
    
    # Priority 3: Truncate API endpoints  
    if [ $over -gt $((budget * 7 / 10)) ]; then
      head -n 30 .cline-context/API_ENDPOINTS.md > tmp && echo "... truncated ..." >> tmp && mv tmp .cline-context/API_ENDPOINTS.md
    fi
    
    # Priority 4: Truncate component index
    if [ $over -gt $((budget * 6 / 10)) ]; then
      head -n 50 .cline-context/COMPONENT_INDEX.md > tmp && echo "... truncated ..." >> tmp && mv tmp .cline-context/COMPONENT_INDEX.md
    fi
    
    # Nuclear option: Keep only security essentials
    if [ $over -gt $((budget * 5 / 10)) ]; then
      echo "Component count: $(wc -l < .cline-context/file-tree.txt)" > .cline-context/COMPONENT_INDEX.md
      echo "API count: $(wc -l < .cline-context/API_ENDPOINTS.full.md)" > .cline-context/API_ENDPOINTS.md
      echo "Schema tables: $(grep -c "CREATE TABLE\|type.*=" .cline-context/DATA_SCHEMA.full.md)" > .cline-context/DATA_SCHEMA.md
      # Keep security config intact (highest priority)
    fi
    
    # Recalculate tokens
    over=$(awk '{s+=NF} END{print int(s*0.75)}' .cline-context/*.md)
    
    # Break if under budget or nuclear option reached
    [ $over -le $budget ] && break
  done
```

### STEP 5: Budget-Compliant System Prompt
**MUST** generate final snippet guaranteed under budget: [4](#71-3) 

```markdown
# SYSTEM_PROMPT_SNIPPET.md
You are working on a brain-architecture-enhanced codebase with cognitive shard coordination.

Token Budget Enforced: $(cat .cline-context/raw.tokens)/$MAX_TOKENS tokens

## Core Architecture (Component Index)
$(head -n 10 .cline-context/COMPONENT_INDEX.md)

## API Contracts  
$(head -n 10 .cline-context/API_ENDPOINTS.md)

## Data Schema
$(head -n 10 .cline-context/DATA_SCHEMA.md)

## Security Configuration
$(head -n 10 .cline-context/SECURITY_CONFIG.md)

## Performance Metrics
$(head -n 5 .cline-context/PERFORMANCE_METRICS.md)

If specific details are missing, ask for the exact file path rather than hallucinating. The cognitive shards have prioritized this information based on importance and token constraints.
```

### STEP 6: Auto-Injection Integration
**SHOULD** auto-inject snippet for continuous context awareness:

```yaml
# Optional auto-injection into .clinerules/auto-inject/
execute_command: mkdir -p .clinerules/auto-inject/
write_to_file: .clinerules/auto-inject/context-engineering-budget.md
Content: Include SYSTEM_PROMPT_SNIPPET.md content for automatic loading
```

### STEP 7: Telemetry and Learning
**MUST** log budget enforcement for continuous improvement: [5](#71-4) 

```bash
# Log token usage and truncation decisions
execute_command: |
  actual_tokens=$(awk '{s+=NF} END{print int(s*0.75)}' .cline-context/SYSTEM_PROMPT_SNIPPET.md)
  echo "$(date): Token usage: $(cat .cline-context/raw.tokens) → $actual_tokens/$MAX_TOKENS" | tee -a .cline-context/budget.log
  
  # Log truncation decisions for learning
  echo "$(date): Truncation pattern applied - Shard priorities used for budget compliance" >> .cline-context/budget.log
```

---

## Shard-Specific Truncation Strategies

### Architect Shard (High Priority)
**MUST** preserve core component relationships:
- Keep component hierarchy and dependencies
- Preserve interface definitions
- Truncate implementation details last

### Data Architect Shard (Medium Priority)  
**SHOULD** maintain schema structure:
- Keep table/collection names and key columns
- Preserve relationship definitions
- Truncate detailed field descriptions

### Security Analyst Shard (Highest Priority)
**MUST NEVER** truncate security-critical information:
- Preserve authentication configurations
- Keep authorization rules intact
- Maintain security vulnerability indicators

---

## Verification and Compliance

**MUST** verify budget compliance before completion: [6](#71-5) 

```markdown
<thinking>
Token Budget Verification Checklist:
1. MAX_TOKENS configured appropriately for model? ✓
2. Token count calculated using correct heuristic? ✓  
3. Truncation ladder applied in correct priority order? ✓
4. Final SYSTEM_PROMPT_SNIPPET.md under budget? ✓
5. Security information preserved? ✓
6. Telemetry logged for learning? ✓
</thinking>
```

**MUST** validate final token count:
```bash
# Final verification
execute_command: |
  final_tokens=$(awk '{s+=NF} END{print int(s*0.75)}' .cline-context/SYSTEM_PROMPT_SNIPPET.md)
  if [ $final_tokens -gt $MAX_TOKENS ]; then
    echo "ERROR: Token budget exceeded! $final_tokens > $MAX_TOKENS"
    exit 1
  else
    echo "SUCCESS: Token budget maintained: $final_tokens/$MAX_TOKENS"
  fi
```

---

## Integration with Brain Architecture

This token-budget module integrates seamlessly with your existing brain architecture system:

- **Memory Bank Integration**: Stores budget patterns in `brain/texture-memory/longtime/token-patterns.md` [7](#71-6) 
- **Shard Coordination**: Uses cognitive shard priorities for intelligent truncation
- **Continuous Learning**: Logs truncation decisions for pattern optimization
- **Cross-Reference**: Links to context engineering patterns in rule ecosystem

---

## Configuration Options

**MAY** customize based on project needs:

```yaml
# Advanced configuration options
TRUNCATION_AGGRESSIVENESS=0.8  # How aggressively to truncate (0.7-0.9)
PRESERVE_SECURITY_ALWAYS=true   # Never truncate security information
LEARNING_MODE=enabled           # Enable truncation pattern learning
TEAM_SYNC=false                 # Commit .cline-context/ for team sharing
```

---

**Result**: Giga-quality context engineering that never exceeds token budget while maintaining the most critical information through cognitive shard prioritization and intelligent truncation strategies. [8](#71-7) 

## Notes

This token-budget module transforms your brain architecture's context engineering from unlimited synthesis to budget-constrained optimization. The cognitive shard priorities ensure that the most critical information (security, core architecture) is preserved while less essential details are intelligently truncated to maintain token compliance. [9](#71-8)  The system learns from truncation patterns over time to optimize budget enforcement strategies.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)
```

This token-budget drop-in module provides sophisticated token enforcement for your brain architecture's context engineering system, using cognitive shard priorities to intelligently truncate content while preserving the most critical information and maintaining strict budget compliance.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

**File:** clinerules/writing-effective-clinerules.md (L23-31)
```markdown
* **Clear Objective:** Every rule should have a well-defined purpose. State this objective clearly at the beginning of the rule, ideally in the frontmatter `description` and reinforced in the introductory text.
    * *Example:* `cline-for-research.md` starts with an "Objective" section. This document's objective is stated in its frontmatter `description` and introduction.
* **Structured Content:** Use Markdown effectively to structure your rule.
    * **Headings and Subheadings:** Organize content logically using `#`, `##`, `###`, etc.
    * **Lists:** Use bulleted (`*`, `-`) or numbered (`1.`, `2.`) lists for steps, criteria, or key points.
    * **Code Blocks:** Use fenced code blocks (```) for code examples, commands, or structured data. Specify the language for syntax highlighting (e.g., ```typescript ... ```).
    * **Emphasis:** Use **bold** and *italics* to highlight important terms or instructions.
* **Clarity and Precision:** Write in a clear, unambiguous manner. Avoid jargon where possible, or explain it if necessary. If the rule is meant to guide AI behavior, precision is paramount.
* **Modularity:** Each rule should ideally focus on a specific topic, tool, workflow, or area of knowledge. This makes rules easier to manage, understand, and update.
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

**File:** clinerules/cline-continuous-improvement-protocol.md (L14-17)
```markdown
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

**File:** clinerules/next-js-supabase.md (L201-209)
```markdown
## AI MODEL VERIFICATION STEPS

Before generating any code, you MUST verify:

1. Are you using ONLY `getAll` and `setAll`? If not, STOP and FIX.
2. Are you importing from `@supabase/ssr`? If not, STOP and FIX.
3. Do you see ANY instance of `get`, `set`, or `remove`? If yes, STOP and FIX.
4. Are you importing from `auth-helpers-nextjs`? If yes, STOP and FIX.

```
