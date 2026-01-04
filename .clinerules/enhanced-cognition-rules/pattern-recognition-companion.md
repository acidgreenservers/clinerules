---
description: "Pattern Recognition Companion - Identifies and extracts reusable patterns from memory bank entries for cross-project application"
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
globs: ["memory-bank/**/*.md"]
tags: ["pattern-recognition", "memory-companion", "cross-reference"]
---

# Pattern Recognition Companion Module

**Objective:** Extend the memory bank with intelligent pattern detection that identifies reusable solutions across different contexts and projects. 

## New Memory Files
**MUST** create these additional files in the memory-bank directory:
- `pattern-library.md` - Catalog of discovered patterns
- `pattern-applications.md` - Where patterns have been successfully applied
- `pattern-failures.md` - Anti-patterns and what to avoid

## Pattern Detection Process
**MUST** execute pattern detection during memory bank updates:

1. **Scan for Repetition**: Identify recurring solutions in `raw_reflection_log.md`
2. **Extract Generalization**: Convert specific solutions to reusable patterns
3. **Validate Pattern**: Check pattern applicability across different contexts
4. **Store in Library**: Add validated patterns to `pattern-library.md`

## Integration with Existing System
**SHOULD** enhance without replacing current memory bank workflows:
- Pattern detection runs during standard memory bank updates
- New files complement the existing 6-core-file structure 
- Patterns feed into `consolidated_learnings.md` for broader distribution
