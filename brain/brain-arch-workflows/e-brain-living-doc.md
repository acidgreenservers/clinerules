
```yaml
---
description: "Brain Architecture Living Documentation Workflow - Executable documentation system that CI-guarantees README code snippets remain accurate and up-to-date"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["README.md", "**/*.md", "**/*.js", "**/*.ts", "**/*.jsx", "**/*.tsx"]
tags: ["living-documentation", "executable-docs", "ci-testing", "brain-architecture", "cognitive-shards"]
---

# Brain Architecture Living Documentation Workflow
## Executable Documentation & Anti-Rot System

**Objective:** Create an executable documentation system that automatically tests and validates all code snippets in README files, ensuring documentation never becomes outdated or inaccurate through continuous integration and automated updates. [1](#68-0) 

---

## Core Living Documentation Mechanism

**MUST** implement executable documentation that prevents "doc rot" through automated testing and validation: [2](#68-1) 

### 1. Live Code Block Detection

**SHOULD** parse README files for fenced code blocks marked with `<!--live-->`:

```markdown
<!--live-->
```javascript
console.log("Hello, World!");
// Expected output: Hello, World!
```
```

**MUST** identify all live blocks and create a test inventory before execution.

### 2. Cognitive Shard Coordination

**MUST** activate specialized cognitive shards for documentation testing:

#### Primary Shards
- **QA Analyst**: Designs and executes test frameworks for code snippets
- **Engineer**: Implements Jest/Mocha wrappers and execution environments  
- **Janitor**: Maintains documentation cleanliness and formatting standards
- **Architect**: Ensures proper documentation structure and testing patterns

#### Supporting Shards
- **Security Analyst**: Validates that code snippets don't expose vulnerabilities
- **Performance Optimizer**: Ensures snippet execution is efficient and non-blocking

### 3. Automated Test Wrapper Injection

**MUST** automatically inject hidden test wrappers around each live snippet:

```javascript
// Auto-generated wrapper for live documentation testing
describe('README Live Documentation: console.log example', () => {
  it('should output exactly "Hello, World!"', async () => {
    // Capture console output
    const originalLog = console.log;
    let capturedOutput = '';
    
    console.log = (...args) => {
      capturedOutput = args.join(' ');
    };
    
    // Execute the original snippet
    console.log("Hello, World!");
    
    // Restore console
    console.log = originalLog;
    
    // Validate exact output match
    expect(capturedOutput).toBe("Hello, World!");
  });
});
```

---

## Execution & Validation Pipeline

### Phase 1: Documentation Analysis

**MUST** perform comprehensive documentation scanning:

1. **Parse README Structure**: Identify all markdown files and code blocks
2. **Extract Live Blocks**: Create inventory of `<!--live-->` marked snippets
3. **Analyze Dependencies**: Determine required test frameworks and environments
4. **Generate Test Matrix**: Map each snippet to appropriate testing strategy

### Phase 2: Test Execution

**SHOULD** execute live documentation tests with strict validation:

```yaml
# Living Documentation Test Configuration
test_environments:
  javascript: jest
  typescript: jest + ts-jest
  python: pytest
  bash: shelltest

validation_rules:
  - exact_output_match: true
  - timeout_seconds: 30
  - memory_limit_mb: 512
  - network_access: false
```

**MUST** fail immediately if any snippet doesn't produce expected output.

### Phase 3: Documentation Synchronization

**SHOULD** update documentation when outputs change:

1. **Compare Expected vs Actual**: Identify output differences
2. **Update README**: Rewrite documentation with correct outputs
3. **Generate Diff Report**: Show exactly what changed
4. **Auto-Commit Changes**: Commit with `[skip ci]` to prevent loops

---

## Brain Architecture Integration

### Memory Storage

**MUST** store documentation test results in brain architecture:

```
brain/documentation-testing/
├── live-snippet-inventory.md    # Catalog of all live blocks
├── test-results.log             # Execution results and outputs  
├── doc-rot-detections.md        # History of caught documentation issues
└── synchronization-log.md       # Record of all documentation updates
```

### Cross-Shard Communication

**SHOULD** enable shard coordination for comprehensive testing:

- **QA Analyst → Engineer**: "Snippet X needs TypeScript environment setup"
- **Engineer → Janitor**: "Updated output for snippet Y, please format"
- **Security Analyst → Architect**: "Snippet Z contains potential security issue"
- **Performance Optimizer → All**: "Snippet A execution time exceeds threshold"

### Learning Integration

**MUST** capture documentation patterns for continuous improvement:

```markdown
## Documentation Pattern Learning
**Successful Patterns:**
- Console output validation with exact string matching
- API response testing with mock data
- Configuration file validation with schema checking

**Common Issues Detected:**
- Outdated version numbers in installation commands
- Changed API endpoints in example code
- Modified configuration syntax in newer versions
```

---

## Implementation Workflow

### 1. README Parsing Engine

**MUST** implement robust markdown parsing:

```javascript
// Living Documentation Parser
class LivingDocParser {
  parseLiveBlocks(readmeContent) {
    const liveBlocks = [];
    const regex = /<!--live-->\s*```(\w+)\n([\s\S]*?)\n```/g;
    
    let match;
    while ((match = regex.exec(readmeContent)) !== null) {
      liveBlocks.push({
        language: match[1],
        code: match[2].trim(),
        expectedOutput: this.extractExpectedOutput(match[2])
      });
    }
    
    return liveBlocks;
  }
}
```

### 2. Test Execution Framework

**SHOULD** create automated test runners:

```yaml
# Test Execution Configuration
living_docs_tests:
  setup_commands:
    - npm install --save-dev jest ts-jest @types/jest
    - pip install pytest
  
  execution_pipeline:
    1. Parse README for live blocks
    2. Generate test files for each block
    3. Execute tests in isolated environment
    4. Compare actual vs expected outputs
    5. Update documentation if needed
    6. Commit changes with [skip ci]
```

### 3. Continuous Integration Integration

**MUST** integrate with CI/CD pipelines:

```yaml
# GitHub Actions Workflow
name: Living Documentation Tests
on: [push, pull_request]

jobs:
  test-documentation:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm install
      - name: Test living documentation
        run: npm run test:living-docs
      - name: Update documentation if needed
        run: npm run update:living-docs
```

---

## Verification & Quality Assurance

### Pre-Execution Checklist

**MUST** verify before running living documentation tests:

```markdown
## Living Documentation Verification Checklist
□ All README files scanned for <!--live--> blocks
□ Test environments properly configured
 Expected outputs extracted and validated
□ CI pipeline integration confirmed
□ Memory bank storage paths created
□ Shard communication channels established
```

### Post-Execution Validation

**SHOULD** validate results after documentation testing:

1. **Test Coverage**: 100% of live blocks tested
2. **Output Accuracy**: All snippets produce expected results
3. **Documentation Sync**: README files updated if needed
4. **Memory Storage**: Results logged to brain architecture
5. **Pattern Learning**: New documentation patterns captured

---

## Error Handling & Recovery

### Documentation Rot Detection

**MUST** immediately identify and flag documentation issues:

```markdown
## Documentation Rot Alert
**File**: README.md
**Snippet**: Installation command (line 45)
**Issue**: Expected output "v1.2.3" but got "v1.3.0"
**Action**: Auto-updating documentation with new version
**Severity**: MEDIUM - Version mismatch detected
```

### Recovery Mechanisms

**SHOULD** implement automatic recovery for common issues:

- **Version Mismatches**: Auto-update version numbers in examples
- **API Changes**: Flag for manual review of deprecated endpoints
- **Configuration Updates**: Update sample configs with new syntax
- **Dependency Changes**: Update installation commands

---

## Advanced Features

### Multi-Repository Documentation Testing

**MAY** extend living documentation across multiple repositories:

```yaml
cross_repo_testing:
  enabled: true
  repositories:
    - main-docs: ./README.md
    - api-docs: ./docs/api.md
    - examples: ./examples/**/*.md
  
  synchronization:
    - Shared snippet validation
    - Cross-repo dependency checking
    - Unified documentation versioning
```

### Interactive Documentation Updates

**MAY** provide interactive documentation improvement:

```markdown
## Documentation Enhancement Suggestions
Based on recent test failures, the QA Analyst shard suggests:
1. Add error handling examples to API documentation
2. Include environment setup prerequisites
3. Update deprecated method calls in examples
4. Add troubleshooting section for common issues

**Approval Required**: [ ] Apply suggestions automatically
```

---

## Integration with Brain Architecture Systems

### Continuous Learning Integration

**MUST** feed documentation insights into continuous improvement: [3](#68-2) 

```markdown
## Documentation Learning Insights
**Pattern Identified**: Console.log examples frequently become outdated
**Learning**: API response formats change more often than expected
**Improvement**: Add version-specific documentation sections
**Rule Enhancement**: Consider version pinning in example code
```

### Memory Bank Integration

**SHOULD** store documentation testing history in memory bank: [4](#68-3) 

```
memory-bank/documentation-testing/
├── living-docs-history.md      # Complete test execution history
├── pattern-library.md          # Reusable documentation patterns
├── failure-analysis.md         # Analysis of documentation failures
└── improvement-suggestions.md  # Auto-generated documentation improvements
```

---

```
LIVING DOCUMENTATION WORKFLOW
Version: 1.0
Status: OPERATIONAL
Primary Shards: QA ANALYST, ENGINEER, JANITOR, ARCHITECT
Integration: Continuous Learning, Memory Bank, CI/CD
```

*documentation lives*  
*examples stay current*  
*knowledge remains accurate*
```

This living documentation workflow creates an executable documentation system that automatically tests and validates README code snippets, preventing documentation rot through continuous integration and automated updates while integrating seamlessly with your brain architecture's cognitive shards. [5](#68-4) 

## Notes

The living documentation workflow transforms static README files into dynamic, tested documentation that evolves with your codebase. By leveraging the brain architecture's cognitive shards, it provides comprehensive testing, automatic updates, and continuous learning about documentation patterns, ensuring your documentation never becomes outdated or inaccurate. [6](#68-5) 

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

**File:** clinerules/mcp-development-protocol.md (L88-97)
```markdown
## Step 3: Testing (BLOCKER ⛔️)

<thinking>
BEFORE using attempt_completion, I MUST verify:
□ Have I tested EVERY tool?
□ Have I confirmed success from the user for each test?
□ Have I documented the test results?

If ANY answer is "no", I MUST NOT use attempt_completion.
</thinking>
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
