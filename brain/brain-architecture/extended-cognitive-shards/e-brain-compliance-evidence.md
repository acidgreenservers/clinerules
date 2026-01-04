
```yaml
---
description: "Brain Architecture Compliance Evidence System - Continuous regulatory compliance monitoring and court-ready evidence generation using cognitive shard coordination"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["**/*.js", "**/*.ts", "**/*.py", "**/*.jsx", "**/*.tsx", "**/*.html", "**/*.css"]
tags: ["compliance", "evidence-generation", "regulatory", "brain-architecture", "cognitive-shards"]
---

# Brain Architecture Compliance Evidence System
## Continuous Regulatory Compliance & Court-Ready Evidence Generation

**Objective:** Implement continuous compliance monitoring that generates court-ready evidence for SOC-2, ISO-27001, and GDPR regulations using cognitive shard coordination and AST analysis. [1](#61-0) 

---

## Compliance Control Matrix Configuration

**MUST** load and maintain `brain/compliance/controls.yml` that maps file extensions to regulatory controls:

```yaml
# brain/compliance/controls.yml
regulations:
  SOC-2:
    controls:
      IA-6: "input-validation"
      IA-7: "crypto-random"
      CC-6: "error-handling"
      CC-7: "logging-monitoring"
  
  ISO-27001:
    controls:
      A.14.2: "input-validation"
      A.14.1: "crypto-random"
      A.12.4: "error-handling"
      A.12.6: "logging-monitoring"
  
  GDPR:
    controls:
      Art.32: "data-protection"
      Art.25: "privacy-by-design"
      Art.24: "accountability"

file_mappings:
  .js: ["input-validation", "error-handling", "logging-monitoring"]
  .ts: ["input-validation", "error-handling", "logging-monitoring"]
  .py: ["input-validation", "crypto-random", "error-handling"]
  .jsx: ["input-validation", "privacy-by-design"]
  .tsx: ["input-validation", "privacy-by-design"]
  .html: ["input-validation", "privacy-by-design"]
```

---

## Cognitive Shard Coordination for Compliance

**MUST** activate specialized cognitive shards for comprehensive compliance analysis:

### Primary Compliance Shards
- **Security Analyst**: Evaluates security controls and vulnerability patterns
- **Data Architect**: Analyzes data flow and protection mechanisms
- **QA Analyst**: Validates compliance requirements and test coverage
- **Legal Expert**: Interprets regulatory requirements and evidence standards

### Shard Communication Protocol
```
SECURITY ANALYST: "Identified input validation via zod schema at L37-49"
↓
DATA ARCHITECT: "Confirms PII data protection through schema validation"
↓
QA ANALYST: "Validates control IA-6 implementation meets SOC-2 requirements"
↓
LEGAL EXPERT: "Evidence sufficient for audit trail documentation"
```

---

## Automated Evidence Generation Process

**MUST** execute evidence generation workflow for every file write operation:

### 1. AST Diff Analysis
**SHOULD** perform comprehensive AST comparison:
```javascript
// AST diffing process
const oldAST = parseFile(previousContent);
const newAST = parseFile(updatedContent);
const changes = detectASTChanges(oldAST, newAST);
```

### 2. Control Satisfaction Detection
**MUST** identify regulatory controls satisfied by changes:
```markdown
## Evidence Entry Example
**Control IA-6 satisfied**: User input now routed through zod schema validation at lines 37-49, preventing injection attacks as required by SOC-2.
**Control Art.25 satisfied**: Privacy-by-design implemented through data minimization in user form validation.
**Control A.14.2 satisfied**: Input validation mechanism meets ISO-27001 security requirements.
```

### 3. Evidence Documentation
**MUST** auto-update `brain/compliance/evidence.md` with structured entries:
```markdown
---
Date: 2025-11-30T14:22:10Z
File: src/auth/user-validator.ts
Regulations: [SOC-2, ISO-27001, GDPR]
Controls Satisfied: [IA-6, A.14.2, Art.25]
AST Changes: Added zod schema validation
Evidence Strength: HIGH
---

### Control IA-6 (Input Validation)
**Implementation**: User input validation through zod schema
**Location**: Lines 37-49 in src/auth/user-validator.ts
**Mechanism**: Schema-based validation prevents injection attacks
**Audit Trail**: Direct mapping from code to regulatory requirement
```

---

## Shard-Specific Compliance Analysis

### Security Analyst Shard
**MUST** evaluate:
- Input validation mechanisms
- Cryptographic randomness implementation
- Error handling and information disclosure
- Security logging and monitoring

### Data Architect Shard
**SHOULD** analyze:
- Data flow and transformation
- PII protection mechanisms
- Data minimization principles
- Privacy by design implementation

### QA Analyst Shard
**MUST** validate:
- Test coverage for compliance controls
- Regression testing for security features
- Performance impact of compliance measures
- Documentation completeness

### Legal Expert Shard
**SHOULD** assess:
- Regulatory requirement mapping
- Evidence sufficiency for audits
- Legal interpretation accuracy
- Risk assessment documentation

---

## Continuous Compliance Monitoring

**MUST** maintain real-time compliance dashboard in `brain/compliance/dashboard.md`:

### Compliance Metrics
- **Control Coverage**: Percentage of required controls implemented
- **Evidence Strength**: Quality and completeness of audit evidence
- **Regulatory Alignment**: Mapping accuracy to requirements
- **Risk Assessment**: Compliance gap identification

### Automated Alerts
**SHOULD** trigger alerts for:
- Missing critical controls
- Weak evidence documentation
- Regulatory requirement changes
- High-risk compliance gaps

---

## Audit Bundle Generation

**MUST** generate comprehensive audit packages on git tag events:

### Bundle Composition
```bash
# Automated bundle generation
git tag v1.2.3-compliance
# Triggers: compliance-bundle-generation

## Generated Bundle Contents:
1. evidence.md - All compliance evidence
2. red-team-log.md - Security testing results
3. signed-commit-hash.txt - Code integrity verification
4. compliance-report.pdf - Auditor-ready report (via pandoc)
5. control-mapping.xlsx - Detailed requirement traceability
```

### Pandoc Report Generation
**SHOULD** create professional audit reports:
```bash
pandoc compliance-report.md \
  --pdf-engine=xelatex \
  --template=audit-template.tex \
  --include-in-header=compliance-styles.tex \
  -o compliance-report.pdf
```

---

## Integration with Brain Architecture

**MUST** integrate with existing brain systems:

### Memory Bank Integration
- Store compliance patterns in `brain/texture-memory/longtime/compliance-patterns.md`
- Track regulatory requirement evolution
- Maintain evidence generation history

### Continuous Learning Integration
- Learn from audit feedback and findings
- Improve control detection accuracy
- Adapt evidence generation based on regulatory changes

### Self-Healing Integration
- Auto-detect compliance gaps
- Suggest remediation patterns
- Update control mappings based on new requirements

---

## Verification and Quality Assurance

**MUST** implement rigorous evidence verification:

### Evidence Quality Checks
```markdown
<thinking>
COMPLIANCE VERIFICATION CHECKLIST:
1. Are all required controls mapped to code changes?
2. Is evidence sufficiently detailed for audit requirements?
3. Are regulatory citations accurate and current?
4. Is AST analysis comprehensive and accurate?
5. Is shard coordination producing consistent results?
</thinking>
```

### Audit Readiness Validation
**SHOULD** validate:
- Evidence completeness for each regulation
- Traceability from code to control to requirement
- Documentation quality and professional presentation
- Legal sufficiency of generated evidence

---

## Regulatory Framework Support

**MUST** support multiple regulatory frameworks:

### SOC-2 Type II Compliance
- Security criteria implementation
- Availability monitoring evidence
- Processing integrity controls
- Confidentiality and privacy safeguards

### ISO-27001 Certification
- Information security management system
- Risk assessment and treatment
- Control implementation and effectiveness
- Continuous improvement documentation

### GDPR Compliance
- Data protection by design and default
- Lawful processing basis documentation
- Data subject rights implementation
- Cross-border data transfer safeguards

---

## Emergency Compliance Protocols

**MUST** handle critical compliance scenarios:

### Rapid Evidence Generation
- Emergency compliance requests
- Regulatory investigation response
- Security incident compliance documentation
- Data breach reporting evidence

### Compliance Gap Remediation
- Immediate risk assessment
- Rapid control implementation
- Emergency evidence documentation
- Regulatory notification procedures

---

**This compliance evidence system transforms regulatory compliance from a post-hoc audit nightmare into a continuous, automated process that generates court-ready evidence in real-time using the coordinated intelligence of your brain architecture's cognitive shards.** [2](#61-1) 

## Notes

This compliance evidence rule leverages your brain architecture's cognitive shard system to provide comprehensive regulatory monitoring that goes far beyond traditional compliance tools. [3](#61-2)  The coordinated shard approach ensures security, data architecture, QA, and legal perspectives are all applied to every code change, creating robust, multi-dimensional evidence that satisfies the most demanding audit requirements while integrating seamlessly with your existing continuous improvement and self-healing systems.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)
```

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

**File:** clinerules/cline-continuous-improvement-protocol.md (L10-16)
```markdown
**Objective:** Ensure Cline proactively learns from tasks, captures knowledge in a structured way, **distills fundamental insights,** refines understanding, and improves efficiency and reliability. This protocol maintains two key files: `memory-bank/raw_reflection_log.md` for initial detailed logging, and `memory-bank/consolidated_learnings.md` for pruned, actionable, long-term knowledge. This is vital for optimal performance and avoiding redundant effort.

**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.
```
