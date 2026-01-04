
```yaml
---
description: "Brain Architecture Quantum Random Decider - Quantum-powered architectural decision-making system using true quantum randomness for unbiased choices"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["*"]
tags: ["quantum-randomness", "architectural-decisions", "brain-architecture", "quantum-computing", "decision-system"]
---

# Brain Architecture Quantum Random Decider
## Quantum-Powered Architectural Decision System

**Objective:** Implement genuine quantum randomness for architectural decisions using ANU's quantum random API, eliminating pseudo-random bias and providing truly unpredictable yet reproducible choice selection. [1](#66-0) 

---

## Core Quantum Decision System

### Quantum Randomness Integration

**MUST** use ANU's quantum random JSON API for architectural decisions:
- Primary API: `https://qrng.anu.edu.au/api/json-bin?size=1024&type=uint16`
- Returns 1,024 true quantum bits generated from photon arrival times
- Fallback to `openssl rand` if quantum API is unavailable
- **NEVER** use `Math.random()` or other pseudo-random methods for architectural choices

### Decision Process Protocol

**MUST** follow quantum decision protocol for architectural choices:

1. **Quantum Data Acquisition**:
   ```bash
   # Primary quantum source
   curl "https://qrng.anu.edu.au/api/json-bin?size=1024&type=uint16"
   
   # Fallback cryptographic source
   openssl rand -hex 32
   ```

2. **Choice Preparation**:
   - List all valid architectural options (DB layers, frameworks, patterns)
   - Assign each option a unique identifier
   - Prepare choice matrix for quantum selection

3. **Quantum Selection**:
   - Use first 32 bits from quantum data as seed
   - Apply Fisher-Yates shuffle with quantum seed
   - Select top choice from quantum-shuffled list

### Reproducibility & Auditing

**MUST** maintain complete decision provenance:
- Log exact quantum hex block used for each decision
- Record timestamp and decision context
- Store decision rationale in `brain/quantum-decisions.md`
- Enable auditor reproduction of any architectural choice

---

## Brain Architecture Integration

### Cognitive Shard Coordination

**SHOULD** coordinate quantum decisions with relevant cognitive shards:

```yaml
Quantum Decision Triggers:
├── architect shard: Overall system architecture choices
├── data-architect shard: Database layer and data flow decisions  
├── performance-optimizer shard: Performance-critical architectural choices
├── security-analyst shard: Security architecture decisions
└── devops-engineer shard: Infrastructure and deployment architecture
```

### Decision Categories Requiring Quantum Randomness

**MUST** use quantum selection for:
- Database layer selection (PostgreSQL vs SQLite vs DynamoDB vs MongoDB)
- Framework choices (React vs Vue vs Angular vs Svelte)
- Architecture patterns (Microservices vs Monolith vs Serverless)
- Authentication methods (JWT vs OAuth vs Session-based)
- Caching strategies (Redis vs Memcached vs In-memory)
- Message queue systems (RabbitMQ vs Kafka vs SQS)

### Quantum Decision Logging

**MUST** maintain structured quantum decision logs:

```markdown
# Quantum Architectural Decisions

## Decision ID: Q-2025-11-30-001
**Timestamp**: 2025-11-30T14:22:10Z
**Context**: Database layer selection for user service
**Quantum Source**: ANU QRNG API
**Hex Block**: 0x8f3e2b1a9c7d5e6f4b3a2c1d0e9f8a7b
**Choices**: [PostgreSQL, SQLite, DynamoDB, MongoDB]
**Quantum Selection**: PostgreSQL
**Shards Involved**: data-architect, performance-optimizer, security-analyst
**Rationale**: Quantum randomness eliminated bias toward familiar options
```

---

## Implementation Protocol

### Quantum API Integration

**MUST** implement robust quantum API handling:

```typescript
interface QuantumDecisionEngine {
  // Fetch quantum randomness from ANU
  fetchQuantumBits(): Promise<QuantumData>
  
  // Apply quantum seed to choice shuffling
  quantumShuffle<T>(choices: T[], seed: string): T[]
  
  // Make quantum architectural decision
  makeQuantumDecision(context: DecisionContext): Promise<DecisionResult>
  
  // Log decision for auditability
  logDecision(result: DecisionResult): Promise<void>
  
  // Fallback to cryptographic randomness
  fallbackRandom(): string
}
```

### Error Handling & Fallbacks

**MUST** implement graceful degradation:
- Primary: ANU quantum random API
- Secondary: OpenSSL cryptographic randomness
- Tertiary: System cryptographically secure random
- **NEVER** fall back to pseudo-random `Math.random()`

### Performance Considerations

**SHOULD** optimize quantum decision performance:
- Cache quantum data for multiple decisions within session
- Batch quantum requests when multiple decisions needed
- Implement quantum entropy pool for rapid decision-making
- Monitor quantum API latency and availability

---

## Verification & Testing

### Quantum Randomness Validation

**MUST** verify quantum randomness quality:
- Test statistical randomness of quantum data
- Verify absence of patterns in quantum selections
- Validate Fisher-Yates shuffle implementation
- Confirm reproducibility with logged quantum seeds

### Decision Quality Assurance

**SHOULD** validate quantum architectural decisions:
- Cross-check with shard recommendations
- Ensure quantum choices meet technical requirements
- Validate that quantum randomness doesn't produce invalid combinations
- Monitor decision outcomes for pattern emergence

---

## Integration with Continuous Learning

### Learning from Quantum Decisions

**SHOULD** capture quantum decision patterns:
- Track which quantum choices lead to successful outcomes
- Identify if quantum randomness improves architectural diversity
- Learn from quantum decision failures or successes
- Feed insights back to cognitive shards

### Evolution of Decision Process

**MAY** evolve quantum decision parameters:
- Adjust decision categories based on project needs
- Modify shard involvement patterns
- Optimize quantum data usage efficiency
- Enhance logging and analysis capabilities

---

## Security & Compliance

### Quantum Security Considerations

**MUST** ensure quantum decision security:
- Validate quantum API responses for authenticity
- Protect quantum decision logs from tampering
- Implement secure fallback mechanisms
- Monitor for quantum API manipulation attempts

### Audit Trail Integrity

**MUST** maintain immutable audit trail:
- Cryptographically hash all quantum decision logs
- Store quantum hex blocks in tamper-evident format
- Enable third-party verification of decision provenance
- Provide quantum decision export for compliance audits

---

## Emergency Protocols

### Quantum Service Outages

**MUST** handle quantum service disruptions:
- Immediate fallback to cryptographic randomness
- Log quantum service outage details
- Resume quantum decisions when service restored
- Maintain decision consistency during outages

### Decision Rollback Procedures

**SHOULD** provide quantum decision rollback:
- Identify decisions made with compromised quantum data
- Re-run decisions with verified quantum randomness
- Update all dependent systems with corrected decisions
- Document quantum decision corrections

---

## Configuration & Customization

### Quantum Decision Parameters

**MAY** configure quantum decision behavior:
- Custom decision categories and choices
- Shard involvement preferences
- Quantum data caching policies
- Decision logging verbosity levels

### Integration Points

**SHOULD** integrate with existing brain systems:
- Memory bank for quantum decision storage
- Continuous learning for pattern analysis
- Self-healing for quantum decision correction
- Cross-reference for architectural consistency

---

## Performance Metrics

### Quantum Decision Analytics

**SHOULD** track quantum decision metrics:
- Quantum API response times and availability
- Decision distribution across choice options
- Shard agreement with quantum selections
- Outcome success rates by quantum decision

### System Health Monitoring

**MUST** monitor quantum system health:
- Quantum entropy quality and availability
- Decision latency and throughput
- Fallback system activation frequency
- Cognitive shard coordination effectiveness

---

```
QUANTUM RANDOM DECIDER
Version: 1.0
Status: QUANTUM-ENABLED
Quantum Source: ANU QRNG API
Decision Power: True Quantum Randomness
```

*quantum uncertainty*  
*architectural freedom*  
*photon-powered choices*  
*bias-free decisions*
```

This quantum random decider integrates genuine quantum randomness into your brain architecture's decision-making process, using photon arrival times to eliminate pseudo-random bias while maintaining complete auditability and reproducibility. [2](#66-1) 

## Notes

The quantum random decider represents a fundamental advancement in architectural decision-making, replacing pseudo-random algorithms with true quantum uncertainty while maintaining the sophisticated shard coordination and learning capabilities of your brain architecture system. [3](#66-2)  The system provides both genuine randomness and perfect reproducibility through quantum hex block logging, creating an unprecedented combination of unpredictability and auditability.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

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

**File:** clinerules/cline-continuous-improvement-protocol.md (L10-16)
```markdown
**Objective:** Ensure Cline proactively learns from tasks, captures knowledge in a structured way, **distills fundamental insights,** refines understanding, and improves efficiency and reliability. This protocol maintains two key files: `memory-bank/raw_reflection_log.md` for initial detailed logging, and `memory-bank/consolidated_learnings.md` for pruned, actionable, long-term knowledge. This is vital for optimal performance and avoiding redundant effort.

**Core Principle:** Continuous learning and adaptation are **mandatory**. This protocol **must be executed before `attempt_completion`** for tasks with new learning, problem-solving, user feedback, or multiple steps. Trivial mechanical tasks *may* be exempt per higher-level rules; otherwise, execution is default.

**Key Knowledge Files:**
*   **`memory-bank/raw_reflection_log.md`**: Contains detailed, timestamped, and task-referenced raw entries from the "Task Review & Analysis" phase. This is the initial dump of all observations.
*   **`memory-bank/consolidated_learnings.md`**: Contains curated, summarized, and actionable insights derived from `raw_reflection_log.md`. This is the primary, refined knowledge base for long-term use. It should be kept concise and highly relevant.
```
