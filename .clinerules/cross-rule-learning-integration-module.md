---  
description: "Cross-Rule Learning Integration - Analyzes rule interactions and suggests improvements to active .clinerules files based on usage patterns"  
author: "Devin AI + https://github.com/acidgreenservers"  
version: 1.0  
globs: ["clinerules/**/*.md"]  
tags: ["rule-improvement", "cross-reference", "learning-integration", "companion-module"]  
---  
  
# Cross-Rule Learning Integration Module  
  
**Objective:** Enable rule-level self-improvement by analyzing rule interactions, conflicts, and usage patterns to suggest enhancements to active `.clinerules` files.   
  
## Rule Analysis Requirements  
  
**MUST** analyze all active `.clinerules` files for:  
- **Rule Dependencies**: How rules reference and depend on each other  
- **Conflict Detection**: Contradictory directives between rules  
- **Coverage Gaps**: Missing guidance for common scenarios  
- **Usage Patterns**: Which rules are most/least effective  
- **Integration Issues**: Problems with rule combinations  
  
## Cross-Reference Learning Process  
  
**MUST** build and maintain rule relationship maps:  
  
1. **Semantic Analysis**: Extract core concepts from each rule  
2. **Dependency Mapping**: Identify rule relationships and hierarchies  
3. **Conflict Detection**: Find contradictory requirements  
4. **Effectiveness Tracking**: Monitor rule success rates  
5. **Improvement Suggestions**: Generate specific rule enhancement proposals  
  
## Rule Enhancement Proposal Format  
  
**MUST** follow structured improvement suggestions:  

## Rule Enhancement Proposal  
**Target Rule**: [rule-name.md]  
**Issue Type**: Conflict | Gap | Optimization | Clarification  
**Confidence**: 0.78 | **Impact**: HIGH | **Evidence**: 3 instances  
  
### Current Issue  
[Description of problem or opportunity]  
  
### Suggested Improvement  
[Specific, actionable change recommendation]  
  
### Expected Benefits 
- Improved clarity/reduced conflicts/better coverage  
- Measurable impact on task success rates  

## Notes
Drop in module for enhancing the memory bank.