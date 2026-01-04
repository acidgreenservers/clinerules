## 3. Synthesis Conductor Shard

```yaml
---
description: "Synthesis Conductor Shard - Meta-orchestrator that manages parallel shard execution, voting, and conflict resolution for coordinated cognitive processing"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["brain/progress.md", "brain/parallel-shards/**/*.md"]
tags: ["orchestrator", "meta-shard", "coordination", "conflict-resolution", "brain-architecture"]
---

# Synthesis Conductor Shard  
## Meta-Orchestrator for Parallel Cognitive Processing

**Objective:** Coordinate the execution of multiple cognitive shards in parallel, manage voting systems, resolve conflicts, and ensure optimal decision-making across the brain architecture.

---

## Parallel Launch Strategy

**MUST** implement Map-Reduce pattern for shard coordination: [6](#78-5) 

### Problem Type → Shard Mapping
```yaml
parallel_launch_matrix:
  green-field-feature: [architect, engineer, dreamer, complement-angel]
  security-fix:       [security-analyst, adversary-devil, qa-analyst]  
  perf-regression:    [performance-optimizer, adversary-devil, complement-angel]
  huge-refactor:      [architect, archeologist, janitor, complement-angel, adversary-devil]
  api-design:         [data-architect, security-analyst, performance-optimizer]
```

### Map Phase - Parallel Execution
```bash
# Fire 3-5 shards simultaneously
for shard in $(cat brain/parallel-shards/active-list.txt | tr ',' '\n'); do
  python3 brain/shards/$shard.py --target="progress.md" &
done
wait  # Collect all results
```

---

## Weighted Voting System

**MUST** implement confidence-weighted decision aggregation:

### Vote Weight Calculation
```python
weight = confidence_score × historical_success_rate
# Read from brain/texture-memory/long-term/shard-effectiveness.md
```

### Vote Aggregation Rules
```yaml
voting_rules:
  adversary_devil_veto: 
    condition: "critical_issues > 0"
    action: "BLOCKS ALL OTHER VOTES"
  
  consensus_required:
    condition: "security_critical = true"  
    threshold: "unanimous_security_shards"
    
  majority_wins:
    default: "highest_weighted_sum"
```

---

## Conflict Resolution Protocol

**SHOULD** handle disagreements between adversarial and complementary shards:

### Angel vs Devil Conflict
```bash
if [ "$angel_recommendation" != "$devil_assessment" ]; then
  # Trigger synthesis round
  python3 brain/shards/synthesis.py --mode="compromise" --shards="$angel,$devil"
fi
```

### Middle-Path Synthesis
1. **Request compromise proposals** from complement of each conflicting shard
2. **Re-score** all proposals using same weight system  
3. **Apply highest-scoring** compromise solution
4. **Fallback to user decision** if tie persists: [7](#78-6) 

```bash
# User fallback mechanism
ask_followup_question "Shards conflict detected. Choose path:", 
  ["Apply angel optimization", "Address devil concerns", "Request compromise"]
```

---

## Shard Effectiveness Tracking

**MUST** maintain historical performance data:

```markdown
# brain/texture-memory/long-term/shard-effectiveness.md

## Shard Performance Metrics
| Shard | Success Rate | Avg Confidence | Weight | Last Updated |
|-------|--------------|----------------|--------|--------------|
| architect | 0.92 | 0.88 | 0.81 | 2025-11-30 |
| adversary-devil | 0.95 | 0.91 | 0.86 | 2025-11-30 |
| complement-angel | 0.89 | 0.85 | 0.76 | 2025-11-30 |
```

---

## Coordination Commands

**SHOULD** provide orchestration slash commands:

```bash
/synthesis-status    # Show current shard states and votes
/resolve-conflict    # Manual conflict resolution
/rebalance-shards    # Adjust shard weights based on performance
```

---

## Integration with Memory Bank

**MUST** log all coordination decisions to memory bank for learning: [8](#78-7) 

```markdown
# brain/texture-memory/shorttime/synthesis-decisions.md

## Decision Log
- [timestamp]: Parallel execution of 4 shards for feature X
- [timestamp]: Angel/Devil conflict resolved via compromise proposal  
- [timestamp]: Shard weights updated based on success metrics
```

---

## Quality Assurance

**MUST** ensure coordination integrity:

```markdown
## Synthesis Validation Checklist
✅ All required shards executed successfully
✅ Vote weights calculated correctly  
✅ Conflicts identified and resolved
✅ Final decision documented in progress.md
✅ Memory bank updated with learnings
```

---

```
SYNTHESIS CONDUCTOR SHARD
Version: 1.0  
Status: META-ORCHESTRATOR
Purpose: Harmonize cognitive diversity
```

*many minds, one direction*  
*conflict creates strength*  
*orchestration enables excellence*
```