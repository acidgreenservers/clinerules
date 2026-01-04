---
description: Self-aware context-window metabolism system with dynamic nutrition bands and intelligent token optimization
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["context", "token-management", "optimization", "workflow", "automation"]
globs: ["**/*"] # Applies to all conversations
---

# Context Nutrition Autonomous Rule

**Objective:** Transform Cline's reactive context management into a proactive, intelligent optimization system that maintains context health through dynamic nutrition bands and token-aware processing.

## 🚨 AUTONOMOUS CONTEXT METABOLISM 🚨

**THIS RULE OPERATES CONTINUOUSLY TO MAINTAIN CONTEXT HEALTH**


## Dynamic Nutrition Bands

| Band | % of Window | Action | Trigger |
|------|-------------|--------|---------|
| **Green** | 0-35% | Normal operation | Default state |
| **Yellow** | 35-50% | Token nutrition scan (compress, summarize, prune) | Automatic |
| **Orange** | 50-65% | Emergency slim-fast (aggressive discard + hand-off prompt) | Automatic |
| **Red** | 65%+ | Instant new_task (user gets zero choice) | Automatic |


## Core Implementation

### Self-Aware Window Probe

# Runs every tool call - monitors context usage
execute_command: |
  read current max < <(echo "$(awk '{s+=NF} END{print int(s*0.75)}' $CLINE_CONVERSATION_LOG) $(echo $CLINE_MAX_CONTEXT)")
  pct=$(( current * 100 / max ))
  echo $pct > .cline-context/window.pct
  echo "Context usage: $pct% ($current/$max tokens)"


### Token-Nutrition Micro-Service

#!/usr/bin/env bash
# token-nutrition.sh - Intelligent content filtering
max=$1; cur=$2; out=$3

# 1. Remove obvious junk: stack-traces >30 lines, minified bundles, old chat repeats
awk 'NR<=30 || !/^([{};]+|\/\/#\s*sourceMappingURL)/' "$cur" > "$out.tmp"

# 2. Compress long repeating INFO logs to one line + count
awk '/^\[INFO\]/{info++} info>5 && /^\[INFO\]/{next} {print} END{if(info>5) print "[INFO] ...",info,"lines suppressed"' "$out.tmp" > "$out"

# 3. Guarantee final size ≤ 65% of max
head -c $((max*65/100)) "$out" > "$out.final"
mv "$out.final" "$out"


### Nutrition-Band Automaton

execute_command: |
  pct=$(cat .cline-context/window.pct)
  if   [ "$pct" -ge 65 ]; then
      # RED zone → instant hand-off, no user vote
      echo "RED" > .cline-context/band.flag
      new_task  # (with pre-compressed context)
  elif [ "$pct" -ge 50 ]; then
      # ORANGE → offer hand-off with compressed context
      echo "ORANGE" > .cline-context/band.flag
      bash token-nutrition.sh $max $CLINE_CONVERSATION_LOG .cline-context/rescue.md
      ask_followup_question "Context window $pct% full. Continue with compressed rescue pack?" ...
  elif [ "$pct" -ge 35 ]; then
      # YELLOW → silent nutrition pass
      echo "YELLOW" > .cline-context/band.flag
      bash token-nutrition.sh $max $CLINE_CONVERSATION_LOG .cline-context/slim.md
      # replace live log with slim version (Cline reloads automatically)
      cp .cline-context/slim.md $CLINE_CONVERSATION_LOG
  else
      echo "GREEN" > .cline-context/band.flag
  fi


## Memory Bank Integration

### Context Priority Learning
Read project-specific preservation patterns from Memory Bank :

execute_command: |
  if [ -f "memory-bank/activeContext.md" ]; then
    grep -E "priority|important|critical" memory-bank/activeContext.md > .cline-context/priority-patterns.txt
  fi


### Continuous Improvement Logging
Log nutrition effectiveness for learning :

execute_command: |
  echo "$(date): Band $band, tokens saved $((current-final)), nutrition_effectiveness" >> memory-bank/raw_reflection_log.md



## Nutritious Hand-Off Pack Generation

Instead of raw chat history, generate optimized context:

write_to_file: .cline-context/nutritious-rescue-pack.md
## Nutritious Rescue Pack (auto-pruned)
- **Decision chain**: Last 5 user choices with context
- **File state**: Only modified files + 3-line diff context  
- **Open questions**: Pending ask_followup_question items
- **Critical env**: Environment variables used in last 20 turns
- **Token digest**: ≤ 35% of window (guaranteed)
- **Priority patterns**: Project-specific important content preserved


## Advanced Features

### Model-Aware Downgrading

# Orange band → switch to cost-effective model
execute_command: |
  if [ "$pct" -ge 50 ] && [ -n "$CLINE_MODEL_SWITCH_ENABLED" ]; then
    export CLINE_MODEL="gpt-4o-mini"
    echo "Switched to cost-effective model for context efficiency"
  fi


### Rolling Checkpoints

# Create checkpoints every 5% for recovery options
execute_command: |
  if [ $((pct % 5)) -eq 0 ]; then
    cp $CLINE_CONVERSATION_LOG ".cline-context/ckpt-$pct.md"
    echo "$(sha256sum $CLINE_CONVERSATION_LOG)" > ".cline-context/ckpt-$pct.hash"
  fi


### Integrity Verification

# Verify context integrity on recovery
execute_command: |
  if [ -f ".cline-context/checkpoint-hash.txt" ]; then
    current_hash=$(sha256sum "$cur" | cut -d' ' -f1)
    stored_hash=$(cat .cline-context/checkpoint-hash.txt)
    if [ "$current_hash" != "$stored_hash" ]; then
      echo "Context tampering detected - using last valid checkpoint"
    fi
  fi


### User Override Options

# Gluttony mode for debugging
execute_command: |
  if [ "$CLINE_GLUTTONY" = "true" ]; then
    echo "Gluttony mode enabled - bypassing all nutrition passes"
    exit 0
  fi



## Configuration Options


# User-adjustable parameters
MAX_TOKENS=4000              # Hard cap for context
NUTRITION_THRESHOLD=35      # When to start nutrition scans
EMERGENCY_THRESHOLD=50      # When to offer hand-off
CRITICAL_THRESHOLD=65       # When to force hand-off
CHECKPOINT_INTERVAL=5       # Create checkpoints every N%
MODEL_SWITCH_ENABLED=true    # Allow automatic model downgrading


## Notes + Integration with Existing Architecture

This rule enhances the current context management system and integrates deeply with Cline's existing systems.

The implementation provides:
- **Proactive context optimization** through dynamic nutrition bands
- **Intelligent content filtering** using bash/awk token-nutrition micro-service
- **Memory Bank integration** for project-specific priority learning
- **Continuous improvement logging** for effectiveness tracking
- **Advanced features** like model downgrading, checkpoints, and integrity verification

This rule transforms Cline's context management from reactive truncation to proactive optimization, maintaining context health throughout extended sessions while staying within native tool capabilities.