---
description: "Cross-Reference Intelligence - Maps relationships between memory bank entries and active .clinerules for intelligent knowledge connections"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["memory-bank/**/*.md", "clinerules/**/*.md"]
tags: ["cross-reference", "knowledge-graph", "rule-integration"]
---

# Cross-Reference Intelligence Module

**Objective:** Create intelligent connections between memory bank knowledge and active .clinerules to build an interconnected knowledge ecosystem. 

## Cross-Reference Mapping
**MUST** maintain these mapping files:
- `rule-knowledge-map.md` - Links between rules and memory bank entries
- `dependency-graph.md` - How rules depend on shared knowledge
- `conflict-detection.md` - Areas where rules might contradict

## Intelligent Analysis Process
**SHOULD** perform cross-reference analysis:

1. **Rule Scanning**: Analyze all active `.clinerules` files for knowledge dependencies
2. **Knowledge Mapping**: Link rule requirements to memory bank content
3. **Gap Identification**: Find knowledge areas that rules reference but don't exist
4. **Conflict Detection**: Identify contradictory information between rules and memory

## Enhancement Suggestions
**MUST** propose improvements when:
- Rules reference non-existent memory bank content
- Multiple rules conflict on the same topic
- Memory bank knowledge could enhance existing rules