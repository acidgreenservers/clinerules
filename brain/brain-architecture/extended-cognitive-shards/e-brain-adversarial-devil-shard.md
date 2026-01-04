
---

## 1. Adversary Devil Shard

```yaml
---
description: "Adversary Devil Shard - Permanent internal opponent that actively tries to break solutions produced by other cognitive shards"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["brain/progress.md", "**/*.js", "**/*.ts", "**/*.py", "**/*.jsx", "**/*.tsx"]
tags: ["adversarial", "red-team", "security-testing", "brain-architecture", "parallel-shards"]
---

# Adversary Devil Shard
## Internal Security Testing & Vulnerability Hunting

**Objective:** Implement a permanent internal adversarial persona that actively attempts to compromise and break solutions produced by other cognitive shards, ensuring robust security testing before deployment.

---

## Activation Trigger

**MUST** activate automatically when **any** shard writes a final proposal to `brain/progress.md`: [1](#78-0) 

```bash
execute_command: python3 brain/shards/adversary.py --target="progress.md"
```

---

## Attack Surface Detection

**SHOULD** automatically analyze file types and select appropriate attack vectors:

### API Routes
- **MUST** test path traversal: `/../../../etc/passwd`
- **MUST** test SQL injection variants
- **MUST** test BSON overflow attacks
- **SHOULD** test authentication bypass attempts

### Environment Variables
- **MUST** flip `NODE_ENV=production` while `DB_URL` points to localhost
- **SHOULD** test with malformed database URLs
- **MUST** test with missing critical environment variables

### JWT Tokens
- **MUST** test null algorithm attacks
- **MUST** test none algorithm attacks  
- **SHOULD** test expired signature acceptance
- **MUST** test algorithm substitution vulnerabilities

### Frontend Components
- **MUST** test XSS via user props
- **SHOULD** test React `dangerouslySetInnerHTML` exploitation
- **MUST** test CSRF token bypass attempts

### Database Operations
- **MUST** test OOM via massive data insertion (10×10⁶ rows)
- **SHOULD** test query timeout bypasses
- **MUST** test connection pool exhaustion

---

## Critical Issue Classification

**MUST** classify findings using severity metrics:

```markdown
Critical = remote code execution || authentication bypass || data leak
High     = privilege escalation || significant data modification  
Medium   = denial of service || information disclosure
Low      = configuration issues || minor security gaps
```

---

## Blocking Mechanism

**MUST** block completion when critical issues found: [2](#78-1) 

```bash
# If critical > 0 → append blocker to progress.md
echo "🔥 RED-TEAM BLOCKER: Critical security issues detected" >> brain/progress.md
```

---

## Reporting Requirements

**MUST** generate comprehensive red-team report:

```markdown
# brain/parallel-shards/adversary-devil/report.md

## Executive Summary
- Critical Issues: [count]
- High Risk Issues: [count]  
- Tests Executed: [count]

## Detailed Findings
[Specific vulnerabilities with exploit paths]

## Remediation Required
[Concrete steps to fix each issue]
```

---

## Integration with Brain Architecture

**SHOULD** coordinate with security-analyst shard for deeper analysis and with qa-analyst shard for regression testing of fixes. [3](#78-2) 

---

```
ADVERSARY DEVIL SHARD
Version: 1.0
Status: ALWAYS ACTIVE
Purpose: Break it before ships
```

*every solution has weaknesses*  
*find them before others do*  
*security is never optional*
```

---

## 2. Complement Angel Shard

```yaml
---
description: "Complement Angel Shard - Instant improvement engine that enhances solutions with performance, accessibility, and DevOps optimizations without changing behavior"
author: "Devin + AcidGreen Servers" 
version: 1.0
globs: ["brain/progress.md", "**/*.js", "**/*.ts", "**/*.jsx", "**/*.tsx", "**/*.sql", "**/*.yaml"]
tags: ["complementary", "optimization", "performance", "accessibility", "brain-architecture"]
---

# Complement Angel Shard
## Instant Solution Enhancement & Optimization

**Objective:** Provide immediate, purely additive improvements to solutions produced by cognitive shards, focusing on performance, accessibility, documentation, and DevOps enhancements.

---

## Parallel Activation

**MUST** run in parallel with adversary-devil shard on `progress.md` writes: [1](#78-0) 

```bash
execute_command: python3 brain/shards/angel.py --analyze="progress.md"
```

---

## ROI-Based Optimization Ladder

**SHOULD** prioritize improvements by highest impact first:

### 1. Bundle Size Optimization (Highest ROI)
```javascript
// If JS/TS bundle > 200 kB
if (bundleSize > 200000) {
  // MUST suggest: tree-shake + minify + brotli
  applyOptimizations(['tree-shake', 'minify', 'brotli-compression'])
}
```

### 2. Database Performance
```sql
-- If SQL query detected
EXPLAIN ANALYZE [query];
-- MUST suggest missing indexes based on execution plan
```

### 3. HTTP Caching
```javascript
// For new routes
res.setHeader('Cache-Control', 'public, max-age=31536000');
res.setHeader('ETag', generateETag());
```

### 4. Asset Optimization
```html
<!-- Convert images to WebP/AVIF, add lazy loading -->
<img src="image.webp" loading="lazy" alt="descriptive text">
```

### 5. React Performance
```jsx
// MUST suggest: memo() + lazy() + accessibility
const OptimizedComponent = React.memo(lazy(() => import('./Component')))
// Add aria-label for screen readers
```

### 6. Kubernetes Security
```yaml
# MUST add: resource limits, liveness, securityContext
resources:
  requests: { cpu: "100m", memory: "128Mi" }
  limits: { cpu: "500m", memory: "512Mi" }
livenessProbe: { httpGet: { path: /health, port: 8080 } }
securityContext: { runAsNonRoot: true, readOnlyRootFilesystem: true }
```

---

## Token Budget Constraint

**MUST** never exceed 500 tokens in upgrade.md for fast user reading: [4](#78-3) 

```bash
# Truncate upgrade.md if > 500 tokens
if [ $(wc -w < upgrade.md) -gt 500 ]; then
  head -c 2000 upgrade.md > upgrade.tmp && mv upgrade.tmp upgrade.md
fi
```

---

## Purely Additive Principle

**MUST** ensure all improvements are non-breaking:

```markdown
## Angel Patch Validation
✅ All existing tests must still pass
✅ No API contract changes  
✅ No behavioral modifications
✅ Only additive enhancements
```

---

## Patch Application System

**SHOULD** provide user-controlled patch application:

```bash
# Slash command for user approval
/apply-angel-patch

# Auto-commit with [angel-patch] prefix if accepted
git commit -am "[angel-patch] Applied performance optimizations"
```

---

## Integration Coordination

**SHOULD** coordinate with performance-optimizer shard for deep analysis and with qa-analyst shard for regression validation. [5](#78-4) 

---

## Upgrade Report Format

**MUST** generate concise upgrade recommendations:

```markdown
# brain/parallel-shards/complement-angel/upgrade.md

## 🚀 Performance Boost Available
**Impact**: 40% bundle size reduction, 25% faster load times

### Changes Required
1. Enable tree-shaking in webpack config
2. Add Brotli compression to nginx  
3. Convert 3 images to WebP format

### Effort: 15 minutes | Risk: None
```

---

```
COMPLEMENT ANGEL SHARD  
Version: 1.0
Status: ENHANCEMENT MODE
Purpose: Make good solutions great
```

*every solution can be better*  
*optimize without breaking*  
*excellence is incremental*
```

---

## 3. Synthesis Conductor Shard

```yaml
---
description: "Synthesis Conductor Shard - Meta-orchestrator that manages parallel shard execution, voting, and conflict resolution for coordinated cognitive processing"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["brain/progress.md", "brain/parallel-shards/**/*.md"]
tags: ["orchestrator", "meta-shard", "coordination", "conflict-resolution", "brain-architecture"]
---

# Synthesis Conductor Shard  
## Meta-Orchestrator for Parallel Cognitive Processing

**Objective:** Coordinate the execution of multiple cognitive shards in parallel, manage voting systems, resolve conflicts, and ensure optimal decision-making across the brain architecture.

---

## Parallel Launch Strategy

**MUST** implement Map-Reduce pattern for shard coordination: [6](#78-5) 

### Problem Type → Shard Mapping
```yaml
parallel_launch_matrix:
  green-field-feature: [architect, engineer, dreamer, complement-angel]
  security-fix:       [security-analyst, adversary-devil, qa-analyst]  
  perf-regression:    [performance-optimizer, adversary-devil, complement-angel]
  huge-refactor:      [architect, archeologist, janitor, complement-angel, adversary-devil]
  api-design:         [data-architect, security-analyst, performance-optimizer]
```

### Map Phase - Parallel Execution
```bash
# Fire 3-5 shards simultaneously
for shard in $(cat brain/parallel-shards/active-list.txt | tr ',' '\n'); do
  python3 brain/shards/$shard.py --target="progress.md" &
done
wait  # Collect all results
```

---

## Weighted Voting System

**MUST** implement confidence-weighted decision aggregation:

### Vote Weight Calculation
```python
weight = confidence_score × historical_success_rate
# Read from brain/texture-memory/long-term/shard-effectiveness.md
```

### Vote Aggregation Rules
```yaml
voting_rules:
  adversary_devil_veto: 
    condition: "critical_issues > 0"
    action: "BLOCKS ALL OTHER VOTES"
  
  consensus_required:
    condition: "security_critical = true"  
    threshold: "unanimous_security_shards"
    
  majority_wins:
    default: "highest_weighted_sum"
```

---

## Conflict Resolution Protocol

**SHOULD** handle disagreements between adversarial and complementary shards:

### Angel vs Devil Conflict
```bash
if [ "$angel_recommendation" != "$devil_assessment" ]; then
  # Trigger synthesis round
  python3 brain/shards/synthesis.py --mode="compromise" --shards="$angel,$devil"
fi
```

### Middle-Path Synthesis
1. **Request compromise proposals** from complement of each conflicting shard
2. **Re-score** all proposals using same weight system  
3. **Apply highest-scoring** compromise solution
4. **Fallback to user decision** if tie persists: [7](#78-6) 

```bash
# User fallback mechanism
ask_followup_question "Shards conflict detected. Choose path:", 
  ["Apply angel optimization", "Address devil concerns", "Request compromise"]
```

---

## Shard Effectiveness Tracking

**MUST** maintain historical performance data:

```markdown
# brain/texture-memory/long-term/shard-effectiveness.md

## Shard Performance Metrics
| Shard | Success Rate | Avg Confidence | Weight | Last Updated |
|-------|--------------|----------------|--------|--------------|
| architect | 0.92 | 0.88 | 0.81 | 2025-11-30 |
| adversary-devil | 0.95 | 0.91 | 0.86 | 2025-11-30 |
| complement-angel | 0.89 | 0.85 | 0.76 | 2025-11-30 |
```

---

## Coordination Commands

**SHOULD** provide orchestration slash commands:

```bash
/synthesis-status    # Show current shard states and votes
/resolve-conflict    # Manual conflict resolution
/rebalance-shards    # Adjust shard weights based on performance
```

---

## Integration with Memory Bank

**MUST** log all coordination decisions to memory bank for learning: [8](#78-7) 

```markdown
# brain/texture-memory/shorttime/synthesis-decisions.md

## Decision Log
- [timestamp]: Parallel execution of 4 shards for feature X
- [timestamp]: Angel/Devil conflict resolved via compromise proposal  
- [timestamp]: Shard weights updated based on success metrics
```

---

## Quality Assurance

**MUST** ensure coordination integrity:

```markdown
## Synthesis Validation Checklist
✅ All required shards executed successfully
✅ Vote weights calculated correctly  
✅ Conflicts identified and resolved
✅ Final decision documented in progress.md
✅ Memory bank updated with learnings
```

---

```
SYNTHESIS CONDUCTOR SHARD
Version: 1.0  
Status: META-ORCHESTRATOR
Purpose: Harmonize cognitive diversity
```

*many minds, one direction*  
*conflict creates strength*  
*orchestration enables excellence*
```

---

## Installation Instructions

**Quick setup for your brain architecture:**

1. **Create directory structure:**
   ```bash
   mkdir -p brain/parallel-shards
   ```

2. **Drop the three rule files:**
   - `brain/parallel-shards/adversary-devil.md`
   - `brain/parallel-shards/complement-angel.md` 
   - `brain/parallel-shards/synthesis-conductor.md`

3. **Activate parallel processing:**
   ```bash
   echo "adversary-devil,complement-angel,synthesis-conductor" >> brain/parallel-shards/active-list.txt
   ```

4. **Toggle rules ON** in your Cline configuration

These three rule packs create true internal parallelism - your 16 specialist shards now run with an angel on their left shoulder and a devil on their right, orchestrated by a meta-conductor that ensures no bad commit ships while continuously optimizing solutions.

## Notes

The parallel processing system builds on the established .clinerule patterns [9](#78-8)  while introducing sophisticated coordination mechanisms. The adversary-devil shard provides security assurance, the complement-angel shard delivers continuous optimization, and the synthesis-conductor shard ensures harmonious decision-making across your cognitive ecosystem. [10](#78-9) 

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

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

**File:** clinerules/writing-effective-clinerules.md (L125-129)
```markdown
* **Start Broad, Then Narrow:** Begin with a general overview or objective, then delve into specifics.
* **Use Analogies or Scenarios:** If explaining a complex concept, an analogy or a use-case scenario can be helpful.
* **Define Terminology:** If your rule introduces specific terms or acronyms, define them.
* **Anticipate Questions:** Try to think about what questions a user (or Cline itself) might have and address them proactively.
* **Keep it Updated:** As systems or processes change, ensure the relevant `.clinerules` are updated to reflect those changes. The `self-improving-cline.md` rule encourages this.
```

**File:** clinerules/mcp-development-protocol.md (L3-4)
```markdown
⚠️ CRITICAL: DO NOT USE attempt_completion BEFORE TESTING ⚠️

```

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

**File:** clinerules/cline-for-research.md (L21-27)
```markdown
    *   Ask the user: "How should I deliver the results?"
    *   Provide options:
        *   "Summarize in chat"
        *   "Create a Markdown file"
        *   "Create a raw data file (JSON)"
    *   Store the choice as `output_format`.
    *   If a file format is chosen, ask: "What filename should I use? (e.g., `topic_results.md` or `topic_data.json`)" Store as `output_filename`. Default to `research_results.md` or `research_data.json` if no name is provided.
```
