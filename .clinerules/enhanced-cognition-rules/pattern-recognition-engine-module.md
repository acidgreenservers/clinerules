---  
description: "Pattern Recognition Engine - Automated pattern detection and extraction from raw reflection logs for reusable solution identification"  
author: "Devin AI + https://github.com/acidgreenservers" 
version: 1.0  
globs: ["memory-bank/raw_reflection_log.md"]  
tags: ["pattern-recognition", "automation", "continuous-learning", "companion-module"]  
---  
  
# Pattern Recognition Engine Module  
  
**Objective:** Automatically detect and extract reusable patterns from `memory-bank/raw_reflection_log.md` to transform manual consolidation into automated insight discovery.   
  
## Core Pattern Detection Requirements  
  
**MUST** scan `raw_reflection_log.md` for these pattern types:  
- **Solution Patterns**: Repeated problem-solving approaches  
- **Configuration Patterns**: Common setup requirements  
- **API Interaction Patterns**: Consistent external service usage  
- **Error Resolution Patterns**: Recurring issue fixes  
- **Performance Patterns**: Optimization strategies  
  
## Automated Pattern Extraction Process  
  
**MUST** execute pattern detection during consolidation phase:  
  
1. **Analyze Raw Entries**: Scan for recurring themes and approaches  
2. **Identify Pattern Candidates**: Mark potential reusable solutions  
3. **Validate Pattern Strength**: Rate based on frequency and success rate  
4. **Extract to Consolidated**: Add to `consolidated_learnings.md` with pattern metadata  
5. **Track Pattern Usage**: Monitor application success rates  
  
## Integration with Existing System  
  
**SHOULD** enhance the consolidation process from `cline-continuous-improvement-protocol.md` :  
  
- Run before manual consolidation review  
- Provide pattern suggestions for human approval  
- Automate obvious pattern transfers  
- Flag complex patterns for manual review  
  
## Pattern Metadata Format  
  
**MUST** include pattern confidence and context:  
```markdown  
## Pattern: [Pattern Name]
**Confidence**: 0.85 | **Occurrences**: 5 | **Success Rate**: 92%  
**Context**: [When this pattern applies]  
- Implementation details  
- Usage examples  
- *Rationale:* Why this works


## Implementation Notes

This companion modules follow the established behavioral rule patterns  and integrate seamlessly with the existing memory bank system. this module:

1. **Enhances without replacing** current memory bank functionality
2. **Follows established file organization** patterns 
3. **Uses directive language** (MUST/SHOULD) for clear implementation guidance
4. **Integrates with continuous improvement** for ongoing optimization

The module can be implemented incrementally based on your specific needs and automatically enhance the memory bank's capabilities while maintaining full backward compatibility.