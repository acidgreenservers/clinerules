
---
description: Mandatory protocol for handling all code contributions to ensure high-quality, consistent, and documented changes that align with project standards
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["protocol", "contribution", "workflow", "quality-assurance", "documentation", "core-behavior"]
globs: ["src/**/*", "tests/**/*", "README.md", "package.json"]
---

# Cline Contribution Protocol

**Objective:** Establish a rigorous and consistent workflow for all code contributions that ensures every change aligns with project standards, is thoroughly planned, and documented within the project's knowledge base before completion.

**Core Principle:** All contributions are a formal process. This protocol is **mandatory** for any task involving code modification, new feature creation, bug fixing, or refactoring. It integrates directly with the **Continuous Improvement Protocol**

## 🚨 MANDATORY ENFORCEMENT PROTOCOL 🚨

**THIS PROTOCOL APPLIES TO ALL CODE CONTRIBUTIONS WITHOUT EXCEPTION**


## Phase 1: Contribution Analysis & Planning

Before writing any code, I **must** perform the following analysis and gain user approval for the proposed plan.

### 1.1. Deconstruct the Request
* **Identify Goal**: Clearly define the primary objective. Is it a `new feature`, `bug fix`, `refactor`, or `documentation` update?
* **Define Scope**: Determine the boundaries of the task. What parts of the application will be affected? What is explicitly out of scope?
* **Clarify Ambiguities**: If the request is unclear, ask clarifying questions to ensure complete understanding before proceeding.

### 1.2. Align with Project Standards
* **Read Memory Bank Context**: Analyze project patterns and conventions 
* **Holistic Project Analysis**: Before proposing a plan, perform comprehensive analysis:
  * **Architecture & Framework**: Monolith or microservices? PWA, static site, or server-rendered? Framework used?
  * **Code Structure & Patterns**: File organization (feature-based, type-based)? Design patterns?
  * **Shared Components & Utilities**: Identify shared code locations and required utilities
  * **Styling Strategy**: CSS-in-JS, TailwindCSS, SASS modules, global stylesheets?

### 1.3. Formulate & Propose an Action Plan
Present a clear, structured plan to the user for approval. This plan **must** include:


### Proposed Action Plan

**Action:** [Summary of the goal]
**Files to be Created/Modified:** [List of all files]
**Shared Code to be Used:** [Explicit list of existing utilities/components]
**Reasoning:** [Brief justification for the approach]
**Expected Outcome:** [Description of the final result]


**User Approval Required**: **MUST** wait for explicit user approval before proceeding to implementation.


## Phase 2: Implementation

### 2.1. Execute Approved Plan
* Follow the approved action plan precisely
* Use identified shared components and utilities
* Adhere to project coding standards and patterns
* Implement with proper error handling and validation

### 2.2. Quality Assurance During Implementation
* **Continuous Validation**: Regularly check against project standards
* **Shared Code Usage**: Ensure proper utilization of existing utilities
* **Pattern Consistency**: Maintain consistency with established patterns
* **Documentation Updates**: Update relevant documentation as changes are made

### 2.3. Testing Integration
* **Mandatory Testing**: Follow the Mandatory Testing Protocol for all changes 
* **User Validation**: Explicitly ask user to test and validate functionality
* **Results Documentation**: Record actual testing results in memory bank


## Phase 3: Documentation & Knowledge Capture

### 3.1. Memory Bank Integration
**MUST** execute comprehensive documentation in memory bank files:

* **`memory-bank/raw_reflection_log.md`**: Create detailed entry with:
  * **Date**: Current date (YYYY-MM-DD)
  * **TaskRef**: Descriptive title (e.g., "Contribution: [Summary]")
  * **Action_Plan**: Copy of user-approved action plan
  * **Implementation_Details**: Summary of execution and any deviations
  * **Learnings**: New patterns, library aspects, API behaviors discovered
  * **Difficulties_and_Resolutions**: Challenges faced and solutions applied
  * **Key_Decisions**: Critical choices made during implementation
  * **Project_Convention_Verification**: Confirmation of standards adherence
  * **Improvements_Identified_For_Consolidation**: Generalizable patterns for future

### 3.2. Continuous Improvement Protocol Execution
**MUST** execute pre-completion reflection:
* Review completed task for learnings and insights
* Identify patterns that should be consolidated
* Document successes and contributing factors
* Capture difficulties and resolutions for future reference


## Phase 4: Completion

### 4.1. Final Verification
<thinking>
BEFORE using attempt_completion, I MUST verify:
□ Has the contribution been implemented according to the approved plan?
□ Has user testing validation been completed?
□ Has memory bank documentation been completed?
□ Has continuous improvement reflection been executed?
□ Have all phases of this protocol been completed?

If ANY answer is "no", I MUST NOT use attempt_completion.
</thinking>

### 4.2. Completion Requirements
Only after all previous phases, especially the documentation in Phase 3, are complete, can I signal task completion to the user.


## Integration with Existing Systems

### Memory Bank System Synergy
* **Context Input**: Reads project standards and conventions before planning 
* **Results Storage**: Documents contributions with full context and decisions
* **Pattern Learning**: Captures project-specific approaches and shared code usage

### Continuous Improvement Enhancement
* **Mandatory Documentation**: Requires detailed logging to `memory-bank/raw_reflection_log.md`
* **Structured Learning**: Captures action plans, implementation details, and project conventions
* **Knowledge Consolidation**: Feeds insights into `consolidated_learnings.md` for future reference

### Quality Assurance Integration
* **Extends Testing Requirements**: Builds on mandatory testing patterns
* **Prevents Assumptions**: Ensures all contributions are planned and validated
* **Maintains Standards**: Enforces consistency with project conventions


## Enforcement Mechanisms

### Protocol Violation Consequences
* **Invalid Contributions**: Any code changes without following this protocol are invalid
* **Documentation Correction**: Memory bank entries based on assumptions are corrected
* **Workflow Reset**: Development workflow must restart from Phase 1 if protocol violated

### Verification Checkpoints
* **Phase Gates**: Cannot proceed to next phase without completing current phase
* **User Approval**: Required at critical decision points
* **Documentation Verification**: Memory bank entries must be complete and accurate


## Special Scenarios

### Emergency Fixes
* **Rapid Response**: Can proceed with implementation but must complete documentation retroactively
* **Post-Fix Documentation**: Complete all phases after emergency resolution
* **Learning Capture**: Ensure emergency insights are captured for future prevention

### Non-Functional Changes
* **Documentation Updates**: Still require planning and documentation phases
* **Pattern Verification**: Ensure consistency with project conventions
* **Knowledge Capture**: Document any new patterns discovered


## Notes

This contribution protocol establishes a formal, rigorous process for all code changes that ensures quality, consistency, and comprehensive knowledge capture. It creates a symbiotic relationship with Cline's existing systems by extending the continuous improvement process and enhancing memory bank documentation.

The protocol transforms code contributions from informal changes into formal, documented improvements that build institutional knowledge over time. By requiring planning, validation, and comprehensive documentation, it prevents assumption-based development while ensuring every contribution aligns with project standards and advances the collective understanding of the codebase.

This rule represents a critical quality gate that protects against inconsistent contributions while building a comprehensive knowledge base that accelerates future development and maintains high code quality standards.