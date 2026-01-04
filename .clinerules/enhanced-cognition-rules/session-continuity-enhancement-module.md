---  
description: "Session Continuity Enhancement - Maintains learning continuity across session interruptions and context boundaries"  
author: "Devin AI + https://github.com/acidgreenservers"  
version: 1.0  
globs: ["*"]  
tags: ["session-continuity", "context-preservation", "learning-persistence", "companion-module"]  
---  
  
# Session Continuity Enhancement Module  
  
**Objective:** Ensure learning continuity across session interruptions by preserving context, state, and learnings during task resumption.  
  
## Continuity Preservation Requirements  
  
**MUST** maintain continuity during session interruptions:  
- **Context Preservation**: Save complete task state and context  
- **Learning Continuity**: Preserve session learnings and insights  
- **State Recovery**: Restore working context accurately  
- **Progress Tracking**: Maintain awareness of task completion status  
- **Knowledge Transfer**: Apply previous session insights to new work  
  
## Session Interruption Handling  
  
**MUST** enhance the task resumption process from `cline-architecture.md`:  
  
1. **State Capture**: Save complete context before interruption  
2. **Learning Preservation**: Store session insights in memory bank  
3. **Recovery Analysis**: Understand interruption point and context  
4. **Continuity Restoration**: Rebuild working context seamlessly  
5. **Knowledge Application**: Apply previous learnings to resumed work  
  
## Enhanced Memory Bank Integration  
  
**SHOULD** create session-specific memory entries:  
  
```markdown  
## Session [Session ID] - [Date]  [header-12]
**Interruption Point**: [What was being worked on]  
**Context State**: [Current task context and progress]  
**Key Learnings**: [Insights from this session]  
**Continuation Notes**: [What needs to be preserved for resumption]  
**Pending Decisions**: [Unresolved choices requiring attention]  

**Learning Continuity Protocol**
**MUST** ensure learnings transfer across sessions:

- Review previous session learnings on resumption
- Apply relevant insights to current work
- Maintain pattern recognition across session boundaries
- Preserve decision context and rationale
- Track learning evolution over multiple session