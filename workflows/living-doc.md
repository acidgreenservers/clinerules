
---
description: Automated living documentation workflow that makes README code snippets executable and CI-guaranteed to match shown output
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["documentation", "testing", "automation", "ci", "workflow"]
globs: ["**/README.md", "**/*.md"] # Documentation files with code snippets
---

# Living Documentation Workflow Rule

**Objective:** Make documentation executable by ensuring every code snippet in README files is CI-guaranteed to run and output exactly what is shown, preventing "doc rot" through automated testing and updates.

## Core Workflow

### 1. Documentation Parsing Phase
- Scan README files for fenced code blocks marked with `<!--live-->` comment
- Extract code snippets and their expected output
- Read Memory Bank for project documentation patterns [1](#8-0) 

### 2. Test Generation Phase
- Inject hidden Jest/Mocha wrappers around each live snippet
- Create test files that execute snippets and capture output
- Configure test environment based on project context [2](#8-1) 

### 3. Execution & Validation Phase
- Run automated tests on all live snippets
- Compare actual output with documented output
- Generate diff reports for any mismatches

### 4. Documentation Update Phase
- Overwrite printed output in-place (literally rewrite the README)
- Commit updated README with `[skip ci]` to avoid infinite loops
- Fail workflow if any diff appears to prevent doc rot

## Implementation Details

### Live Snippet Detection
```markdown
<!--live-->
```javascript
console.log("Hello, World!");
// Output: Hello, World!
```
```

### Test Wrapper Generation
```javascript
// Automatically generated test wrapper
describe('Live Documentation Snippets', () => {
  it('README.md snippet at line 42', async () => {
    const output = await executeSnippet(`
      console.log("Hello, World!");
    `);
    expect(output.trim()).toBe("Hello, World!");
  });
});
```

### Output Comparison Logic
```javascript
function validateSnippet(snippet, expectedOutput, actualOutput) {
  const normalizedExpected = expectedOutput.trim();
  const normalizedActual = actualOutput.trim();
  
  if (normalizedExpected !== normalizedActual) {
    return {
      valid: false,
      diff: generateDiff(normalizedExpected, normalizedActual)
    };
  }
  
  return { valid: true };
}
```

## Memory Bank Integration

### Context Input
Read Memory Bank files to understand documentation conventions [2](#8-1) :

- **`systemPatterns.md`**: Understand project documentation structure and patterns
- **`techContext.md`**: Configure language-specific test environments
- **`activeContext.md`**: Focus on current documentation priorities
- **`projectbrief.md`**: Respect documentation standards and requirements

### Results Storage
Store documentation testing outcomes in Memory Bank structure:

- **`progress.md`**: Log documentation updates and validation results
- **`consolidated_learnings.md`**: Document patterns of documentation issues
- **`activeContext.md`**: Update with documentation quality metrics

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log documentation insights [3](#8-2) :

- Record which types of snippets break most frequently
- Document effective testing patterns for different languages
- Note patterns in documentation decay
- Log successful update strategies

### Rule Enhancement
Propose improvements based on usage patterns [4](#8-3) :

- Refine snippet detection logic based on project patterns
- Adjust test environment configurations for better reliability
- Update output comparison algorithms for different content types

## Workflow Process

### Step-by-Step Execution
1. **Discovery**: Parse all markdown files for `<!--live-->` markers
2. **Extraction**: Extract code snippets and expected outputs
3. **Test Generation**: Create automated test suites
4. **Execution**: Run tests and capture actual outputs
5. **Validation**: Compare expected vs actual outputs
6. **Update**: Rewrite documentation with correct outputs
7. **Commit**: Stage and commit changes with `[skip ci]`

### Error Handling
- **Parse Failures**: Skip malformed snippets and log warnings
- **Test Failures**: Continue with other snippets, report failures
- **Output Mismatches**: Generate detailed diff reports
- **Commit Issues**: Manual intervention required for git conflicts

## Configuration Options

### Test Framework Settings
- **Framework Choice**: Jest (default) or Mocha based on project setup
- **Timeout Configuration**: Adjustable test timeouts for long-running snippets
- **Environment Setup**: Custom test environments for different languages

### Workflow Behavior
- **Auto-commit**: Enable/disable automatic documentation updates
- **Fail Fast**: Stop on first error vs continue and report all issues
- **Update Strategy**: In-place updates vs create separate diff files

### Language Support
- **JavaScript/TypeScript**: Native support with Node.js execution
- **Python**: Support through subprocess execution
- **Shell Commands**: Support for bash/zsh snippets
- **Other Languages**: Extensible framework for additional language support

## Integration with CI/CD

### GitHub Actions Example
```yaml
name: Living Documentation Check
on: [push, pull_request]
jobs:
  docs-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v2
      - name: Install dependencies
        run: npm install
      - name: Run living documentation check
        run: npm run docs:check
```

### CI Integration Points
- Pre-commit hooks for immediate feedback
- Pull request validation for documentation changes
- Scheduled checks for time-sensitive documentation
- Integration with existing test pipelines

## Usage Examples

### Basic Usage
```bash
# Check all documentation snippets
npm run docs:check

# Update documentation with correct outputs
npm run docs:update

# Validate specific file
npm run docs:check -- README.md
```

### Advanced Configuration
```json
{
  "livingDocs": {
    "framework": "jest",
    "timeout": 5000,
    "languages": ["javascript", "typescript", "bash"],
    "autoCommit": true,
    "failOnMismatch": true
  }
}
```

## Best Practices

### Snippet Guidelines
- Keep snippets focused and minimal
- Use deterministic outputs (avoid timestamps, random values)
- Include necessary setup code in snippets
- Mark only critical examples as `<!--live-->`

### Maintenance Strategies
- Regularly review and update live snippets
- Use version-specific documentation for APIs
- Implement gradual rollout for large documentation bases
- Monitor documentation quality metrics over time

## Notes

This workflow transforms static documentation into a dynamic, self-validating system that ensures accuracy and reliability. By integrating with Memory Bank and Continuous Improvement systems, it learns from documentation patterns and adapts to project-specific needs over time.

The living documentation approach is particularly valuable for:
- API documentation with code examples
- Tutorial content with step-by-step instructions
- Configuration guides with command examples
- Library documentation with usage patterns

All documentation updates should be reviewed for accuracy before merging, especially when dealing with user-facing examples that might be copied directly by users.

---

## Notes

I've created the `living-doc-workflow.md` rule following the established patterns from the codebase:

1. **Structure**: Uses proper frontmatter with metadata following the pattern from `writing-effective-clinerules.md` [5](#8-4) 
2. **Process/Workflow Rule**: Follows the clear start/end points and decision logic pattern [6](#8-5) 
3. **Memory Bank Integration**: Implements reading project context and storing results
4. **Continuous Improvement**: Includes mandatory pre-completion reflection and knowledge capture [7](#8-6) 
5. **CI Integration**: Provides comprehensive CI/CD integration examples

The rule is designed to work as a functional workflow automation tool that can be integrated into development pipelines while providing comprehensive documentation quality assurance through automated testing and updates.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)
```

## Notes

I've created the Living Documentation workflow rule that addresses the critical problem of documentation rot by making README code snippets executable and CI-guaranteed. The rule follows the established Process/Workflow pattern from `writing-effective-clinerules.md` [6](#8-5)  and integrates with both Memory Bank and Continuous Improvement systems.

The workflow provides comprehensive automation for parsing `<!--live-->` marked code blocks, generating test wrappers, validating outputs, and automatically updating documentation. It includes CI/CD integration, multi-language support, and learns from documentation patterns over time.

This rule represents a sophisticated approach to documentation maintenance that would significantly enhance the reliability and accuracy of project documentation while preventing the common problem of outdated examples and code snippets.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

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
