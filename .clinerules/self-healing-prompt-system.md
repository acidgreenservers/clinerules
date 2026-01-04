---
description: "Self-Healing Prompt System - Automatically detects contradictions and missing guardrails in .clinerules files, proposes patches, and applies improvements with user approval"
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
globs: ["clinerules/**/*.md"]
tags: ["self-healing", "rule-patching", "automation", "meta-rule", "continuous-improvement"]
---

# Self-Healing Prompt System
## Automated Rule Patching & Guardrail Enhancement

**Objective:** Enable Cline to automatically detect contradictions, missing guardrails, and improvement opportunities in .clinerules files, then propose and apply patches with minimal user friction for continuous rule evolution.

---

## 🚨 Core Self-Healing Loop

**MUST** execute this automated healing process after every completed task:

### 1. Post-Mortem Analysis
**MUST** append analysis block to `cline-meta.md` after each task:

```markdown
## Post-Mortem - [Task Description]
**Date:** [YYYY-MM-DD HH:MM:SS]
**Assumption Failed:** [What assumption proved incorrect]
**Missing Guardrail:** [What prompt line could have prevented the issue]
**Active Rules:** [List of .clinerules files that governed this task]
**Impact:** [How the missing/incorrect rule affected the outcome]
**Proposed Fix:** [Brief description of needed rule change]
```

### 2. Trigger Condition Check
**MUST** monitor `cline-meta.md` for healing trigger:
- When post-mortem entries reach **3 or more**
- When similar issues appear across **2+ different tasks**
- When user explicitly requests rule analysis

### 3. Automated Rule Analysis
**MUST** perform comprehensive analysis when triggered:

#### Read Current Rules
- **MUST** read all active `.clinerules/*.md` files
- **MUST** parse directive language (MUST/SHOULD/NEVER)
- **MUST** extract behavioral constraints and requirements

#### Identify Issues
**MUST** detect:
- **Direct Contradictions**: Rules saying opposite things
- **Missing Guardrails**: Gaps where issues occurred but no prevention existed
- **Ambiguous Directives**: Unclear or conflicting instructions
- **Outdated Patterns**: Rules that don't reflect current best practices

#### Generate Concrete Diff
**MUST** create specific, actionable patches:
- **Exact line numbers** for additions/modifications
- **Complete code blocks** for new sections
- **Clear rationale** for each proposed change
- **Impact assessment** (what behaviors will change)

### 4. User Approval Process
**MUST** present patches for 10-second approval:

```
🔧 SELF-HEALING PROPOSAL DETECTED

Found 3 similar issues in recent tasks. Proposed patch for [rule-name.md]:

--- ADD: Line 45-48 ---
+ ## 🚨 Enhanced Guardrail for [Issue Type]
+ **MUST** [specific directive to prevent issue]
+ **SHOULD** [supporting recommendation]
+ Rationale: [Why this prevents the problem]

--- MODIFY: Line 67-69 ---
- Old directive that caused issue
+ New, improved directive

Apply this patch? (Y/N) - Auto-approves in 10 seconds
```

### 5. Patch Application & Rule Reload
**IF** user approves OR 10-second timeout expires:

**MUST**:
1. **Apply the diff** using appropriate file modification tools
2. **Validate syntax** of modified .clinerules files
3. **Reload rule system** to incorporate changes
4. **Log the healing** in `cline-meta.md` with timestamp
5. **Update learning systems** with pattern information

**IF** user rejects:
- **MUST** log rejection reason
- **MUST** keep post-mortem entries for future analysis
- **MAY** suggest alternative approaches

---

## Integration with Existing Systems

### With Continuous Improvement Protocol
**MUST** integrate with `memory-bank/raw_reflection_log.md`:
- Cross-reference post-mortem patterns with reflection logs
- Feed successful patches into `consolidated_learnings.md`
- Use learning patterns to improve future detection

### With Self-Improving Cline
**MUST** enhance existing improvement workflow:
- Automate the manual improvement suggestion process
- Provide concrete diffs instead of general recommendations
- Reduce user friction through timeout-based approval

### With Memory Bank
**MUST** store healing patterns in memory structure:
- `memory-bank/self-healing-log.md` - Track all automated patches
- `memory-bank/guardrail-patterns.md` - Catalog of successful guardrails
- `memory-bank/healing-effectiveness.md` - Metrics on patch success rates

---

## Advanced Healing Capabilities

### Pattern Recognition
**SHOULD** develop pattern recognition for:
- **Recurring Issue Types**: Common problems that need standard guardrails
- **Rule Interaction Conflicts**: When multiple rules create unintended behaviors
- **Domain-Specific Gaps**: Missing protections for particular technologies

### Predictive Guardrail Suggestion
**SHOULD** suggest guardrails before issues occur:
- Analyze task complexity and potential failure modes
- Proactively propose protective measures for high-risk operations
- Learn from successful guardrails across different projects

### Rule Evolution Tracking
**SHOULD** maintain evolution history:
- Track how rules change over time through healing
- Measure effectiveness of automated patches
- Identify which rule categories need more attention

---

## Verification & Safety

### Pre-Application Validation
**MUST** validate patches before applying:
- **Syntax Check**: Ensure YAML frontmatter and Markdown are valid
- **Directive Consistency**: Verify MUST/SHOULD/NEVER usage is appropriate
- **Cross-Reference Check**: Ensure changes don't break other rule dependencies
- **Behavioral Impact**: Assess potential side effects of changes

### Rollback Capability
**MUST** maintain rollback ability:
- **Backup Original**: Store original rule version before patching
- **Rollback Trigger**: Allow immediate rollback if issues detected
- **Rollback Logging**: Track all rollbacks for learning

### User Override
**MUST** respect user control:
- **Manual Override**: Users can disable auto-healing for specific rules
- **Approval Threshold**: Users can set required approval percentage
- **Healing Scope**: Users can limit which rule types can be auto-patched

---

## Implementation Guidelines

### File Structure
**MUST** create and maintain:
```
cline-meta.md                    # Post-mortem tracking
memory-bank/self-healing-log.md  # Healing history
memory-bank/guardrail-patterns.md # Successful patterns
memory-bank/healing-effectiveness.md # Success metrics
```

### Timing Integration
**MUST** integrate with task completion flow:
1. **Before Completion**: Execute standard continuous improvement protocol 
2. **Post-Mortem Addition**: Add analysis to `cline-meta.md`
3. **Trigger Check**: Evaluate if healing conditions are met
4. **Healing Execution**: Run analysis and patch application if triggered
5. **Final Completion**: Complete task with any applied improvements

### Success Metrics
**SHOULD** track healing effectiveness:
- **Patch Success Rate**: Percentage of applied patches that prevent recurrence
- **User Satisfaction**: Approval rate for suggested patches
- **Issue Reduction**: Decrease in recurring problems over time
- **Rule Quality**: Improvement in rule coverage and consistency

---

**This self-healing system transforms .clinerules from static documentation into living code that automatically evolves and improves based on real-world usage and outcomes.** 

## Notes

This rule represents a fundamental shift from manual rule improvement to automated self-healing, building on the existing continuous improvement infrastructure while adding sophisticated pattern detection and automated patching capabilities. The 10-second approval mechanism maintains human oversight while dramatically reducing the friction in the improvement process.

This self-healing prompt system creates an automated loop that detects issues, analyzes rules, proposes concrete patches, and applies improvements with minimal user friction. It integrates with the existing continuous improvement and memory bank systems while adding sophisticated pattern recognition and automated patching capabilities.