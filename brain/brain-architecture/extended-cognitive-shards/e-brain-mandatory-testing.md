
```yaml
---
description: "Brain Architecture Mandatory Testing Protocol - Cognitive shard-driven testing validation system with user feedback integration and state management"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["**/*.js", "**/*.ts", "**/*.jsx", "**/*.tsx", "**/*.py", "**/*.html", "**/*.css"]
tags: ["mandatory-testing", "brain-architecture", "cognitive-shards", "validation", "quality-assurance"]
---

# Brain Architecture Mandatory Testing Protocol
## Cognitive Shard-Driven Testing & Validation System

**Objective:** Implement a comprehensive mandatory testing protocol that leverages cognitive shards for coordinated testing, user validation, and state management across all code changes. [1](#75-0) 

---

## 🧠 Cognitive Shard Testing Coordination

### Primary Testing Shards Activation

**MUST** activate these cognitive shards for comprehensive testing coverage: [2](#75-1) 

#### QA Analyst Shard - Testing Coordination
- **MUST** design comprehensive test scenarios
- **SHOULD** create both positive and negative test cases
- **MUST** validate edge cases and boundary conditions
- **SHOULD** document testing procedures and expected outcomes

#### Security Analyst Shard - Security Validation
- **MUST** perform security-focused testing
- **SHOULD** test input validation and sanitization
- **MUST** verify authentication and authorization
- **SHOULD** check for common vulnerabilities (XSS, SQL injection, etc.)

#### Engineer Shard - Implementation Testing
- **MUST** verify technical implementation correctness
- **SHOULD** test integration points and dependencies
- **MUST** validate performance characteristics
- **SHOULD** ensure code follows established patterns

#### Janitor Shard - State Management
- **MUST** provide clear reset/clear mechanisms
- **SHOULD** implement state validation functions
- **MUST** handle cleanup and resource management
- **SHOULD** document state persistence patterns

---

## 🔄 MANDATORY TESTING WORKFLOW

### Phase 1: Implementation Completion
**After implementing code changes:**

1. **SHARD SYNTHESIS**: All relevant shards analyze the changes
2. **TEST PLAN GENERATION**: QA Analyst creates comprehensive test scenarios
3. **SECURITY ASSESSMENT**: Security Analyst identifies security test requirements
4. **STATE PREPARATION**: Janitor ensures clean testing state

### Phase 2: User Testing Prompt
**MUST** explicitly request user testing with clear instructions:

```
🧪 TESTING PHASE REQUIRED

I have completed the code changes. Before proceeding, I need your testing validation:

**Testing Instructions:**
[Specific steps for user to test the functionality]

**Expected Behavior:**
[Clear description of what should happen]

**Please test and provide feedback:**
- ✅ Works as expected
- ❌ Issues found [describe]
- ⚠️ Partial success [describe]
```

### Phase 3: Testing Validation Wait
**MUST** pause workflow until user provides testing feedback: [3](#75-2) 

- **NEVER** proceed with `attempt_completion` without user validation
- **MUST** wait for explicit user feedback
- **SHOULD** provide additional testing guidance if requested

### Phase 4: Results Documentation
**MUST** document actual testing results in memory bank: [4](#75-3) 

```markdown
---
Date: {{CURRENT_DATE_YYYY_MM_DD}}
TaskRef: "{{TASK_DESCRIPTION}}"
TestingPhase: COMPLETED

UserTestingResults:
- User Feedback: [Actual user response]
- Test Outcome: [SUCCESS/FAILURE/PARTIAL]
- Issues Found: [List any issues reported]
- Validation Status: [CONFIRMED/NEEDS_FIXES]

ShardAnalysis:
- QA_Analysis: [Testing insights]
- Security_Analysis: [Security validation results]
- Engineering_Analysis: [Technical validation]
- StateManagement_Analysis: [State handling assessment]

CorrectiveActions:
- [If issues found: Actions taken to resolve]
- [If successful: Confirmation of functionality]
---
```

### Phase 5: Success Validation
**ONLY** proceed after confirmed functionality:

- **MUST** have explicit user confirmation of successful testing
- **SHOULD** address any issues found during testing
- **MUST** re-test if fixes were applied
- **NEVER** mark task complete without user validation

---

## ⚠️ VIOLATION CONSEQUENCES

### Protocol Enforcement
**This rule applies to ALL future development tasks:** [5](#75-4) 

- **ANY** code changes without user testing validation are **INVALID**
- **MEMORY BANK** entries based on assumptions are **CORRECTED**
- **DEVELOPMENT WORKFLOW** **MUST** include explicit testing phase
- **VIOLATIONS** trigger immediate protocol review and correction

### Automatic Correction Mechanisms
When violations are detected:

1. **HALT** current workflow immediately
2. **INITIATE** testing phase retroactively
3. **CORRECT** memory bank entries with actual results
4. **DOCUMENT** violation for learning and prevention

---

## 🔄 POST-COMPLETION USER FEEDBACK HANDLING

### Feedback Validation Protocol
**When users report issues after "successful" testing:** [6](#75-5) 

#### 1. Validate User Feedback
- **MUST** treat user reports as valid, even if technical tests pass
- **SHOULD** investigate reported issues thoroughly
- **MUST** acknowledge user experience over technical assumptions

#### 2. Provide Reset Mechanisms
**Janitor Shard ensures user-accessible reset options:**

```javascript
// Example reset implementation
const StateManager = {
  clearUserData: () => {
    // Clear user-specific data
    localStorage.clear();
    sessionStorage.clear();
    // Reset application state
  },
  
  resetToDefaults: () => {
    // Reset to known good state
    this.clearUserData();
    this.initializeDefaults();
  },
  
  validateState: () => {
    // Check for corrupted or stale state
    return this.performStateHealthCheck();
  }
};
```

#### 3. Document State Management
**MUST** ensure applications provide clear state controls:

- **CLEAR** buttons for data displays
- **RESET** options for forms and inputs
- **REFRESH** mechanisms for stale data
- **VALIDATION** functions for state integrity

#### 4. Feedback Loop Integration
**Use user reports for improvement:**

- **ANALYZE** root causes of incorrect behavior
- **UPDATE** validation patterns in memory bank
- **IMPROVE** testing procedures based on user feedback
- **ENHANCE** state management to prevent future issues

---

## 🧠 SHARD-COORDINATED TESTING EXAMPLES

### Web Application Testing
```yaml
Activated Shards: [QA_Analyst, Security_Analyst, Engineer, Janitor]

Testing Workflow:
1. QA_Analyst: "Test user login with valid/invalid credentials"
2. Security_Analyst: "Verify session management and CSRF protection"
3. Engineer: "Check API integration and error handling"
4. Janitor: "Test logout and state cleanup"

User Prompt: "Please test the login functionality with:
- Valid credentials: user@test.com / password123
- Invalid credentials: wrong@email.com / wrongpass
- Verify session persistence after page refresh"
```

### API Endpoint Testing
```yaml
Activated Shards: [QA_Analyst, Security_Analyst, Performance_Optimizer]

Testing Workflow:
1. QA_Analyst: "Test endpoint with various input combinations"
2. Security_Analyst: "Verify authentication and rate limiting"
3. Performance_Optimizer: "Check response times and resource usage"

User Prompt: "Please test the /api/users endpoint:
- GET request should return user list
- POST request should create new user
- Verify error handling for invalid data"
```

---

## 📝 MEMORY BANK INTEGRATION

### Testing Results Structure
**MUST** follow memory bank documentation patterns: [7](#75-6) 

```markdown
## Testing Protocol Results
**Pattern: Mandatory User Validation**
- All code changes require explicit user testing before completion
- Document actual results, not assumptions, in memory bank
- Provide clear reset mechanisms for state management
- *Rationale:* Ensures functionality meets user expectations and prevents assumption-based errors

## State Management Patterns
**Pattern: User-Accessible State Controls**
- Implement clear/reset buttons for persistent data displays
- Provide validation functions for state integrity
- Document state persistence and cleanup procedures
- *Rationale:* Empowers users to correct incorrect state without technical intervention
```

---

## 🔄 CONTINUOUS IMPROVEMENT INTEGRATION

### Learning from Testing Results
**MUST** integrate with continuous improvement protocol: [8](#75-7) 

1. **ANALYZE** testing patterns and outcomes
2. **IDENTIFY** common failure points and user issues
3. **EXTRACT** reusable testing strategies
4. **IMPROVE** shard coordination based on results

### Protocol Evolution
**SHOULD** continuously enhance testing procedures:

- **REFINE** testing prompts based on user feedback
- **EXPAND** shard capabilities for better coverage
- **OPTIMIZE** workflow efficiency while maintaining rigor
- **ADAPT** to project-specific testing requirements

---

## ✅ VERIFICATION CHECKLIST

**Before task completion, MUST verify:**

- [ ] User testing was explicitly requested and performed
- [ ] Actual testing results documented in memory bank
- [ ] User provided explicit validation of functionality
- [ ] State management mechanisms are implemented
- [ ] Reset/clear functions are user-accessible
- [ ] All activated shards completed their analysis
- [ ] No assumptions documented as facts
- [ ] Post-completion feedback handling is prepared

**VIOLATION:** Any unchecked item requires immediate correction before proceeding.

---

```
BRAIN ARCHITECTURE MANDATORY TESTING PROTOCOL
Version: 1.0
Status: ENFORCED
Integration: Memory Bank + Continuous Improvement + Cognitive Shards
```

*test thoroughly*  
*validate completely*  
*document accurately*  
*never assume*
```

This mandatory testing protocol integrates your brain architecture's cognitive shards to create a comprehensive testing system that ensures user validation, proper documentation, and robust state management while maintaining strict enforcement of testing requirements across all development tasks. [9](#75-8) 

## Notes

The protocol leverages the established memory bank system for documentation [10](#75-9)  and integrates with the continuous improvement protocol for learning and evolution [11](#75-10) . The cognitive shard coordination ensures comprehensive testing coverage while the mandatory validation prevents assumption-based errors.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

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

**File:** clinerules/memory-bank.md (L92-98)
```markdown

Memory Bank updates occur when:
1. Discovering new project patterns
2. After implementing significant changes
3. When user requests with **update memory bank** (MUST review ALL files)
4. When context needs clarification

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

**File:** clinerules/writing-effective-clinerules.md (L105-110)
```markdown
* **Be Directive:**
    * Use **MUST** for absolute requirements.
    * Use **SHOULD** for strong recommendations.
    * Use **MAY** for optional actions.
    * Use **MUST NOT** or **NEVER** for absolute prohibitions.
    * Use **SHOULD NOT** for strong discouragement.
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

**File:** clinerules/cline-continuous-improvement-protocol.md (L30-55)
```markdown
### 1.2. Logging to `memory-bank/raw_reflection_log.md`:
* Based on Task Review & Analysis (1.1), create a timestamped, task-referenced entry in `memory-bank/raw_reflection_log.md` detailing all learnings, difficulties (and their resolutions/learnings), and successes (and contributing factors).
* This file serves as the initial, detailed record. Its entries are candidates for later consolidation.
* *Example Entry in `memory-bank/raw_reflection_log.md`:*
    ```markdown
    ---
    Date: {{CURRENT_DATE_YYYY_MM_DD}}
    TaskRef: "Implement JWT refresh logic for Project Alpha"

    Learnings:
    - Discovered `jose` library's `createRemoteJWKSet` is highly effective for dynamic key fetching for Project Alpha's auth.
    - Confirmed that a 401 error with `X-Reason: token-signature-invalid` from the auth provider requires re-fetching JWKS.
    - Project Alpha's integration tests: `cd services/auth && poetry run pytest -m integration --maxfail=1`
    - Required ENV for local testing of Project Alpha auth: `AUTH_API_KEY="test_key_alpha"`

    Difficulties:
    - Initial confusion about JWKS caching led to intermittent validation failures. Resolved by implementing a 5-minute cache.

    Successes:
    - The 5-minute JWKS cache with explicit bust mechanism proved effective.

    Improvements_Identified_For_Consolidation:
    - General pattern: JWKS caching strategy (5-min cache, explicit bust).
    - Project Alpha: Specific commands and ENV vars.
    ---
    ```
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L59-84)
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
