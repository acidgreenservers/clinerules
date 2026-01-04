---
description: Mandatory testing protocol requiring user validation for all code changes before completion, ensuring memory bank accuracy and preventing assumption-based development
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["testing", "validation", "workflow", "quality-assurance", "protocol"]
globs: ["**/*"] # Applies to all code changes
---

# Mandatory Testing Protocol Rule

**Objective:** Establish a mandatory workflow requiring user testing validation for ALL code changes before task completion, ensuring memory bank accuracy and preventing development based on technical assumptions rather than actual results.

## 🚨 CRITICAL PROTOCOL - MANDATORY ENFORCEMENT 🚨

**THIS RULE APPLIES TO ALL FUTURE DEVELOPMENT TASKS WITHOUT EXCEPTION**

### Core Mandate
**NEVER** proceed with task completion without explicit user testing validation. **ALL** code changes MUST be tested and validated by the user before being considered complete.

## Mandatory Workflow for All Code Changes

### Phase 1: Implementation
1. **Make Technical Modifications**: Implement the requested code changes
2. **Read Memory Bank Context**: Understand current project state and testing requirements 
3. **Prepare Testing Environment**: Ensure all prerequisites for testing are in place

### Phase 2: Testing Phase (REQUIRED BLOCKER ⛔️)
1. **Explicit Testing Prompt**: **MUST** ask user to enter testing phase with clear instructions
2. **Wait for User Interaction**: **MUST** pause workflow until user provides testing feedback
3. **Document Actual Results**: **MUST** add real testing results to memory bank, not assumptions
4. **Validate Success**: **MUST** only proceed after confirmed functionality from user

### Phase 3: Documentation & Validation
1. **Update Memory Bank**: Record actual testing outcomes in appropriate files 
2. **Continuous Improvement Log**: Execute pre-completion reflection with testing insights
3. **Final Validation**: Confirm all requirements met before completion

## Verification Checklist (REQUIRED BEFORE COMPLETION)

<thinking>
BEFORE using attempt_completion, I MUST verify:
□ Have I implemented the requested code changes?
□ Have I explicitly asked the user to test the changes?
□ Have I waited for user testing feedback?
□ Have I documented ACTUAL testing results (not assumptions)?
□ Have I updated memory bank with real outcomes?
□ Has the user confirmed the functionality works as expected?

If ANY answer is "no", I MUST NOT use attempt_completion.
</thinking>

## Violation Consequences

### Automatic Invalidation
- **Any code changes without user testing validation are INVALID**
- **Memory bank entries based on assumptions are AUTOMATICALLY CORRECTED**
- **Development workflow violations trigger protocol re-education**

### Correction Protocol
1. **Identify Violation**: Detect when code changes proceed without testing
2. **Rollback Assumptions**: Remove assumption-based entries from memory bank
3. **Require Retesting**: Mandate proper testing phase completion
4. **Document Violation**: Log protocol breach for continuous improvement

## Memory Bank Integration Requirements

### Accurate Documentation
- **NEVER** document assumed outcomes in memory bank files
- **ALWAYS** record actual user testing results and feedback
- **MUST** distinguish between technical expectations and validated results

### File-Specific Requirements
- **`progress.md`**: Log actual testing outcomes, not technical assumptions
- **`consolidated_learnings.md`**: Only include validated insights from user testing
- **`raw_reflection_log.md`**: Document testing process and user feedback accurately

## Post-Completion User Feedback Handling

### Feedback Validation Protocol
When users report issues after "successful" testing:

1. **Validate User Feedback**: Treat user reports of incorrect behavior as VALID, even if technical tests pass
2. **Provide Reset Mechanisms**: Include user-accessible ways to clear/reset application state
3. **Document State Management**: Ensure applications provide clear state management controls
4. **Feedback Loop Integration**: Use user reports to improve validation and state management

### State Management Requirements
- **Reset Functionality**: Provide "clear" or "reset" controls for persistent data displays
- **State Transparency**: Make current application state visible to users
- **Correction Mechanisms**: Allow users to correct incorrect state without technical intervention

## Integration with Continuous Improvement

### Enhanced Knowledge Capture
The rule strengthens the continuous improvement protocol by:
- **Enforcing Actual Results**: Mandates documentation of real testing outcomes 
- **Preventing Invalid Knowledge**: Ensures only validated insights enter knowledge base 
- **Feedback Loop Integration**: Uses post-completion feedback for improvement

### Learning Enhancement
- **Pattern Recognition**: Learn from testing failures and successes
- **Process Optimization**: Improve testing prompts and validation procedures
- **Quality Metrics**: Track testing effectiveness and user satisfaction

## Protocol Enforcement Mechanisms

### Automated Checks
## Pre-Completion Validation (MANDATORY)
- [ ] Code changes implemented
- [ ] User testing explicitly requested
- [ ] User feedback received and documented
- [ ] Memory bank updated with ACTUAL results
- [ ] User confirmed functionality works
- [ ] Continuous improvement reflection completed


### User Interaction Prompts

**Required Testing Prompt Template:**
🧪 TESTING PHASE REQUIRED

I have implemented the requested code changes. Before I can complete this task, you MUST test the functionality to ensure it works as expected.

Please:
1. Test the changes in your environment
2. Provide feedback on what works and what doesn't
3. Confirm if the functionality meets your requirements

I will wait for your testing feedback before proceeding.


## Special Scenarios

### Emergency Fixes
For critical bug fixes requiring immediate deployment:
1. **Document Emergency**: Clearly mark as emergency fix in memory bank
2. **Schedule Follow-up Testing**: Require comprehensive testing within 24 hours
3. **Temporary Validation**: Accept technical validation with user acknowledgment
4. **Mandatory Retrospective**: Conduct full testing and documentation review

### Non-Functional Changes
For documentation or configuration-only changes:
1. **Validate Impact**: Confirm changes don't affect functionality
2. **User Review Required**: Still require user review and confirmation
3. **Document Nature**: Clearly mark as non-functional in memory bank

## Quality Assurance Metrics

### Success Indicators
- **100% User Testing Validation Rate**: All code changes validated by users
- **Zero Assumption-Based Entries**: Memory bank contains only actual results
- **Complete Documentation**: All testing outcomes properly recorded
- **High User Satisfaction**: Users report confidence in functionality

### Failure Modes
- **Skipping Testing Phase**: Automatic protocol violation
- **Assumption Documentation**: Memory bank correction required
- **Incomplete Feedback**: Request additional testing details
- **State Management Issues**: Provide reset mechanisms

## Integration with Existing Rules

### MCP Development Protocol Enhancement
Extends the existing testing requirements:
- **Universal Application**: Applies to ALL code changes, not just MCP servers
- **User Validation Required**: Technical testing alone is insufficient
- **Memory Bank Integration**: Results must be documented in project memory

### Continuous Improvement Protocol Synergy
Strengthens the existing learning system:
- **Validated Learning**: Only insights from user testing enter knowledge base
- **Feedback Integration**: Post-completion feedback improves future processes
- **Quality Focus**: Emphasizes actual outcomes over technical assumptions

## Implementation Guidelines

### For Cline AI
1. **Always Prompt Testing**: Never assume code works without user validation
2. **Wait Patiently**: Pause workflow until user provides testing feedback
3. **Document Accurately**: Record actual results, not technical expectations
4. **Handle Feedback Gracefully**: Accept user corrections and adjust accordingly

### For Users
1. **Test Thoroughly**: Validate functionality in your actual environment
2. **Provide Clear Feedback**: Report what works and what doesn't
3. **Report Issues**: Notify of any problems discovered after completion
4. **Request Resets**: Use provided mechanisms to correct application state

## Notes

This protocol establishes a fundamental shift from assumption-based development to validation-based development. By making user testing mandatory for all code changes, it ensures that Cline's assistance remains reliable, accurate, and aligned with actual user needs.

The integration with Memory Bank and Continuous Improvement systems creates a closed-loop quality assurance process that prevents the propagation of incorrect assumptions and builds a reliable knowledge base based on actual user experiences.

This rule represents a critical quality gate that protects against the common problem of technically correct but functionally wrong solutions, ensuring that all delivered code meets real user requirements and works in actual usage scenarios.

## Notes

Comprehensive Mandatory Testing Protocol rule that expands significantly on your original concept. The rule follows the established behavioral/instructional pattern from `writing-effective-clinerules.md` and integrates deeply with Cline's existing systems.

Key enhancements added:
- **Structured enforcement mechanisms** with verification checklists and thinking blocks
- **Comprehensive memory bank integration** ensuring only actual results are documented
- **Post-completion feedback handling** with state management requirements
- **Special scenario protocols** for emergency fixes and non-functional changes
- **Quality assurance metrics** and success/failure mode definitions
- **Integration with existing rules** extending MCP and Continuous Improvement protocols

The rule creates a robust quality assurance system that prevents assumption-based development while maintaining practical flexibility for real-world scenarios. It establishes user testing as a non-negotiable requirement while providing the structure and support needed to make it effective.