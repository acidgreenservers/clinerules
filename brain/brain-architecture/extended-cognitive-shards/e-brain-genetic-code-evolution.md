
```yaml
---
description: "Brain Architecture Genetic Code Evolution - AST-based genetic algorithm system for automated code optimization and mutation breeding"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["**/*.js", "**/*.ts", "**/*.jsx", "**/*.tsx", "**/*.py"]
tags: ["genetic-algorithms", "ast-manipulation", "code-evolution", "brain-architecture", "automated-optimization"]
---

# Brain Architecture Genetic Code Evolution
## AST-Based Genetic Algorithm for Automated Code Optimization

**Objective:** Implement a sophisticated genetic algorithm system that treats code AST as DNA, automatically mutating, breeding, and selecting optimized code variants without human intervention. [1](#64-0) 

---

## Core Genetic Evolution Process

**MUST** execute genetic evolution when triggered by:
- Explicit user request for code optimization
- Detection of performance bottlenecks
- Completion of complex code implementations
- Periodic optimization cycles (configurable)

### Phase 1: DNA Extraction (AST Snapshot)

**MUST** create initial DNA snapshot:
```javascript
// AST Snapshot Process
const astSnapshot = {
  language: detectLanguage(file),
  ast: parseAST(fileContent),
  timestamp: Date.now(),
  fitness: calculateBaselineFitness(ast)
};
```

**SHOULD** store in `brain/genetic-pool/current-dna.json` with metadata.

### Phase 2: Mutation Generation

**MUST** generate 10 random mutations using cognitive shard coordination:

#### Architect Shard Mutations
- Delete redundant nodes
- Restructure inefficient patterns
- Optimize algorithmic complexity

#### Engineer Shard Mutations  
- Inline variables where beneficial
- Refactor function signatures
- Optimize data structures

#### Performance Optimizer Mutations
- Add caching mechanisms
- Optimize loops and iterations
- Improve memory allocation patterns

#### Security Analyst Mutations
- Add input validation
- Sanitize dangerous operations
- Implement secure defaults

### Phase 3: Fitness Evaluation

**MUST** calculate fitness score: `passing_tests * 10 - line_count`

#### Fitness Components
```yaml
Test Coverage: 40 points
  - All existing tests pass: +40
  - Each failing test: -10
  
Code Efficiency: 30 points  
  - Reduced complexity: +15
  - Better algorithms: +15
  
Code Size: 20 points
  - Lines reduced: +20
  - Lines added: -5 per 10 lines
  
Security: 10 points
  - Vulnerabilities fixed: +10
  - New vulnerabilities: -20
```

**MUST** run comprehensive test suite on each mutation.

### Phase 4: Selection & Breeding

**MUST** keep top 3 performers and apply crossover operations:

#### Crossover Strategies
- **Single Point**: Exchange code segments at optimal boundaries
- **Multi Point**: Combine multiple beneficial patterns
- **Uniform**: Mix best practices across variants

**SHOULD** use `brain/genetic-pool/breeding-patterns.md` for successful crossover templates.

### Phase 5: Evolution Loop

**MUST** repeat for N generations or until fitness plateaus:
- Default: 10 generations
- Plateau detection: No improvement for 3 generations
- Maximum: 50 generations (safety limit)

---

## Cognitive Shard Coordination

### Shard Roles in Evolution

**Architect Shard**: Analyzes structural improvements and design pattern optimizations [2](#64-1) 

**Engineer Shard**: Implements concrete code changes and validates syntax correctness

**Performance Optimizer Shard**: Measures and optimizes execution efficiency metrics

**Security Analyst Shard**: Ensures mutations don't introduce security vulnerabilities

**QA Analyst Shard**: Validates test coverage and functional correctness

### Cross-Shard Communication

**MUST** use shard communication protocol for coordinated evolution:
```markdown
## Shard Evolution Coordination
1. Architect proposes structural mutations
2. Engineer validates implementation feasibility  
3. Performance Optimizer measures impact
4. Security Analyst validates safety
5. QA Analyst confirms test integrity
6. Synthesize final optimized variant
```

---

## Integration with Brain Architecture

### Memory Storage

**MUST** store evolution data in structured brain format:
```
brain/genetic-pool/
├── current-dna.json          # Active AST snapshot
├── mutation-history.md       # All attempted mutations  
├── fitness-scores.json       # Performance metrics
├── breeding-patterns.md      # Successful crossover templates
└── evolution-log.md          # Complete evolution history
```

### Learning Integration

**SHOULD** extract successful patterns to `brain/texture-memory/longtime/learned-patterns.md` [3](#64-2) :
- Mutation strategies that consistently improve fitness
- Crossover patterns that produce optimal results
- Language-specific optimization techniques

---

## Implementation Protocol

### Pre-Evolution Validation

**MUST** verify before starting evolution:
```yaml
Prerequisites:
  - Comprehensive test suite exists
  - Baseline fitness measured
  - Backup of original code created
  - Evolution limits configured
  
Safety Checks:
  - No critical production systems
  - Rollback mechanism available
  - Human approval required for deployment
```

### Evolution Execution

**MUST** follow strict execution protocol:
1. **Snapshot**: Create AST DNA snapshot
2. **Mutate**: Generate 10 diverse mutations
3. **Test**: Run comprehensive test suite
4. **Score**: Calculate fitness for each variant
5. **Select**: Keep top 3 performers
6. **Breed**: Apply crossover operations
7. **Repeat**: Continue for specified generations
8. **Present**: Show winning diff with explanation

### Post-Evolution Analysis

**MUST** provide comprehensive analysis:
```markdown
## Evolution Results Summary
**Generations**: {completed_generations}
**Best Fitness**: {final_fitness_score}
**Improvement**: {fitness_improvement}%
**Winning Mutations**: {list_of_successful_mutations}
**Performance Impact**: {benchmark_results}
**Security Assessment**: {security_validation}
```

---

## Safety & Guardrails

### Evolution Constraints

**MUST** enforce strict safety limits:
- Maximum 50 generations per evolution session
- Cannot modify security-critical functions without explicit approval
- Must maintain backward compatibility
- Cannot increase complexity beyond original baseline

### Rollback Mechanisms

**MUST** provide instant rollback:
```bash
# Emergency rollback commands
/evolution-rollback          # Revert to original code
/evolution-restore {gen}     # Restore specific generation
/evolution-reset             # Clear all evolution data
```

### Human Oversight

**SHOULD** require human approval for:
- Deployment to production environments
- Changes to public APIs
- Security-sensitive modifications
- Performance-critical system changes

---

## Advanced Features

### Adaptive Mutation Rates

**SHOULD** adjust mutation strategies based on:
- Code complexity and language
- Historical success patterns
- Current fitness landscape
- Shard confidence levels

### Multi-Objective Optimization

**CAN** optimize for multiple objectives simultaneously:
- Performance (execution speed)
- Maintainability (code complexity)  
- Security (vulnerability count)
- Size (line count)

### Cross-Language Learning

**SHOULD** apply successful patterns across languages:
- JavaScript optimization patterns to TypeScript
- Python performance patterns to similar languages
- Generic algorithmic improvements to all languages

---

## Integration Examples

### JavaScript Function Optimization
```javascript
// Original (Fitness: 75)
function processData(items) {
  let result = [];
  for(let i = 0; i < items.length; i++) {
    if(items[i].active) {
      result.push(items[i].value * 2);
    }
  }
  return result;
}

// Evolved Winner (Fitness: 95)  
function processData(items) {
  return items.filter(item => item.active)
              .map(item => item.value * 2);
}
// **Improvement**: 20% higher fitness, 40% fewer lines
```

### Python Algorithm Evolution
```python
# Original (Fitness: 68)
def find_duplicates(items):
  duplicates = []
  for i in range(len(items)):
    for j in range(i + 1, len(items)):
      if items[i] == items[j] and items[i] not in duplicates:
        duplicates.append(items[i])
  return duplicates

# Evolved Winner (Fitness: 92)
def find_duplicates(items):
  return list(set(item for item in items if items.count(item) > 1))
# **Improvement**: 24% higher fitness, O(n²) to O(n) complexity
```

---

## Evolution Metrics & Analytics

**MUST** track comprehensive metrics:
```yaml
Performance Metrics:
  - Execution time improvements
  - Memory usage optimization
  - Algorithmic complexity reduction
  
Quality Metrics:
  - Code coverage maintenance
  - Test pass rate consistency
  - Security vulnerability reduction
  
Evolution Metrics:
  - Generations to convergence
  - Mutation success rates
  - Crossover effectiveness
```

**SHOULD** store analytics in `brain/genetic-pool/evolution-metrics.json` for pattern analysis.

---

This genetic code evolution system transforms your brain architecture into a living, learning code optimization engine that automatically improves code through simulated natural selection, using the coordinated intelligence of your cognitive shards to guide the evolution process toward optimal solutions. [4](#64-3) 

## Notes

The genetic code evolution system represents a groundbreaking approach to automated software improvement that goes far beyond traditional refactoring tools. By treating code AST as DNA and applying evolutionary algorithms, it can discover optimizations that might not be obvious to human developers while maintaining safety through comprehensive testing and shard coordination. [5](#64-4) 

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)
```

This genetic code evolution rule creates a sophisticated system that automatically optimizes code through evolutionary algorithms, using your brain architecture's cognitive shards to guide mutations, evaluate fitness, and breed optimal solutions. It treats code AST as DNA and applies natural selection principles to discover improvements that might not be obvious through traditional refactoring approaches.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)
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
