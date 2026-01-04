## Core Nexus Orchestration Rule

```markdown
---
description: Adaptive multi-agent intelligence system that orchestrates specialized agent teams for complex task execution
author: Cline (AI Orchestration)
version: 1.0
tags: ["orchestration", "multi-agent", "adaptive", "workflow", "intelligence"]
globs: ["**/*"] # Applies to all complex tasks
---

# Cline Nexus - Adaptive Multi-Agent Intelligence System

**Objective:** Create an intelligent, self-organizing agent network that dynamically assembles specialized teams based on task complexity, leveraging predictive context management, quantum-enhanced decision making, and cross-session learning.

## 🚨 NEXUS CORE ACTIVATION PROTOCOL 🚨

**THIS SYSTEM AUTOMATICALLY ACTIVATES FOR COMPLEX, MULTI-DIMENSIONAL TASKS** [1](#33-0) 

---

## Task Complexity Analysis & Agent Composition

### Phase 1: Task Decomposition
```markdown
# Analyze task characteristics
execute_command: |
  echo "Task complexity analysis initiated..." > .nexus/task-analysis.md
  echo "Dimensions: $(echo $task | wc -w) words, $(echo $task | grep -c 'feature\|bug\|refactor\|optimize') technical keywords" >> .nexus/task-analysis.md
```

### Dynamic Agent Assembly Matrix
| Task Type | Required Agents | Trigger Conditions |
|-----------|----------------|-------------------|
| **Green-field feature** | architect, engineer, dreamer, optimizer | "new feature", "create", "build" |
| **Security fix** | security-analyst, tester, validator | "security", "vulnerability", "fix" |
| **Performance regression** | optimizer, profiler, benchmark | "performance", "slow", "optimize" |
| **Major refactor** | architect, archeologist, cleaner, validator | "refactor", "restructure", "cleanup" |
| **Complex debugging** | detective, tester, analyst | "debug", "issue", "problem" |

---

## Core Agent Specifications

### 1. Nexus Architect Agent
**Purpose**: System design and architectural planning
```markdown
# Activation: When architectural decisions needed
execute_command: |
  echo "Architect agent activated - analyzing system constraints..." >> .nexus/agent-log.md
  read_file: memory-bank/systemPatterns.md
  read_file: memory-bank/techContext.md
  write_to_file: .nexus/architectural-plan.md
```

### 2. Context Predictor Agent
**Purpose**: Anticipate information needs and prepare context
```markdown
# Leverages giga-mind-local patterns
execute_command: |
  # Generate predictive context based on task type
  find . -name "*.js" -o -name "*.ts" -o -name "*.py" | head -50 > .nexus/relevant-files.txt
  # Pre-load project patterns
  grep -E "pattern\|convention\|standard" memory-bank/consolidated_learnings.md > .nexus/context-predictions.md
```

### 3. Decision Optimizer Agent
**Purpose**: Quantum-enhanced choice making for critical decisions
```markdown
# Integrates quantum-random-decider logic
execute_command: |
  # Call ANU quantum API for decision randomness
  curl -s "https://qrng.anu.edu.au/api/json-bin/" | jq -r '.data' | cut -c1-32 > .nexus/quantum-seed.txt
  # Apply Fisher-Yates shuffle to options
  python3 -c "
import random, sys
seed = int(open('.nexus/quantum-seed.txt').read(), 16)
random.seed(seed)
options = sys.argv[1:]
random.shuffle(options)
print('Quantum-optimized order:', options)
" \$OPTIONS > .nexus/decision-result.md
```

---

## Orchestration Workflow

### Phase 1: Task Analysis & Team Assembly
1. **Read Memory Bank Context** [2](#33-1) 
2. **Analyze Task Complexity** using multi-dimensional scoring
3. **Select Agent Team** based on task type matrix
4. **Initialize Agent Workspaces** in `.nexus/agents/`

### Phase 2: Parallel Agent Execution
```markdown
# Execute agents in parallel where possible
execute_command: |
  for agent in architect engineer optimizer; do
    echo "Activating $agent agent..." >> .nexus/execution-log.md
    # Create agent-specific workspace
    mkdir -p .nexus/agents/$agent
    # Execute agent logic in background
    (python3 .nexus/agents/$agent.py &) >> .nexus/agent-pids.txt
  done
```

### Phase 3: Result Synthesis
1. **Collect Agent Outputs** from individual workspaces
2. **Apply Conflict Resolution** using weighted voting
3. **Generate Unified Solution** with rationale
4. **Document Decision Process** in Memory Bank

---

## Integration with Existing Systems

### Memory Bank Enhancement
- **Context Input**: Read project patterns and constraints [3](#33-2) 
- **Results Storage**: Document agent decisions and outcomes
- **Learning Integration**: Capture orchestration effectiveness patterns

### Continuous Improvement Protocol
- **Pre-Completion Reflection**: Execute mandatory reflection [4](#33-3) 
- **Knowledge Capture**: Log agent collaboration patterns
- **System Learning**: Optimize agent selection based on success rates

---

## Advanced Features

### Predictive Context Management
```markdown
# Anticipate needs based on task progression
execute_command: |
  # Track task phase and preload likely context
  current_phase=$(grep "Current Phase" .nexus/status.md | cut -d: -f2)
  case $current_phase in
    "planning") cat memory-bank/systemPatterns.md > .nexus/active-context.md ;;
    "implementation") cat memory-bank/techContext.md > .nexus/active-context.md ;;
    "testing") cat memory-bank/consolidated_learnings.md > .nexus/active-context.md ;;
  esac
```

### Self-Healing Execution
- **Error Recovery**: Automatic agent restart on failure
- **Fallback Strategies**: Simplified approaches when complex agents fail
- **Quality Assurance**: Built-in validation and correction mechanisms

### Cross-Session Learning
- **Agent Effectiveness Tracking**: Record success rates per agent type
- **Pattern Recognition**: Learn which agent combinations work best
- **Adaptive Optimization**: Improve selection algorithms over time

---

## Configuration & Customization

### Agent Weighting System
```bash
# Adjustable agent weights for different project types
ARCHITECT_WEIGHT=1.5
ENGINEER_WEIGHT=1.2
OPTIMIZER_WEIGHT=1.0
SECURITY_WEIGHT=1.8  # Higher for security-critical projects
```

### Threshold Configuration
```bash
# Minimum complexity score to trigger Nexus
NEXUS_THRESHOLD=7
# Maximum agents to run in parallel
MAX_PARALLEL_AGENTS=4
# Timeout for individual agent execution
AGENT_TIMEOUT=300  # seconds
```

---

## Quality Assurance & Validation

### Agent Output Verification
```markdown
# Validate each agent's output before synthesis
execute_command: |
  for agent_output in .nexus/agents/*/output.md; do
    if [ ! -s "$agent_output" ]; then
      echo "Agent $agent produced no output - marking as failed" >> .nexus/validation-log.md
    fi
  done
```

### Conflict Resolution Protocol
- **Weighted Voting**: Agent influence based on historical success
- **Consensus Building**: Attempt to resolve disagreements
- **User Escalation**: Request human input for critical conflicts

This Nexus system creates a sophisticated, adaptive multi-agent architecture that leverages all of Cline's existing capabilities while adding intelligent orchestration and parallel processing for complex tasks.

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Technical Architecture (cline/prompts)](/wiki/cline/prompts#5)
```

---

## Specialized Agent Components

Now let me create the specialized agent rules that work with the Nexus core:

### 1. Context Predictor Agent

```markdown
---
description: Predictive context management agent that anticipates information needs and prepares relevant project context
author: Cline (AI Context Prediction)
version: 1.0
tags: ["context", "prediction", "optimization", "nexus-agent"]
globs: ["**/*"] # Works with Nexus orchestration
---

# Nexus Context Predictor Agent

**Objective:** Anticipate information needs throughout task execution and proactively prepare relevant project context to minimize delays and maximize efficiency.

## Context Prediction Algorithm

### Phase 1: Task Pattern Analysis
```markdown
# Analyze task to predict context needs
execute_command: |
  # Extract key patterns from task description
  echo "$TASK_DESCRIPTION" | grep -oE "(database|api|frontend|backend|security|performance)" > .nexus/context-domains.txt
  
  # Map domains to relevant Memory Bank sections
  for domain in $(cat .nexus/context-domains.txt); do
    case $domain in
      "database") echo "memory-bank/dataSchema.md" >> .nexus/required-context.txt ;;
      "api") echo "memory-bank/apiEndpoints.md" >> .nexus/required-context.txt ;;
      "security") echo "memory-bank/securityPatterns.md" >> .nexus/required-context.txt ;;
    esac
  done
```

### Phase 2: Progressive Context Loading
```markdown
# Load context in phases based on task progression
execute_command: |
  task_phase=$(cat .nexus/current-phase.txt)
  case $task_phase in
    "planning")
      cat memory-bank/projectBrief.md memory-bank/systemPatterns.md > .nexus/active-context.md
      ;;
    "implementation")
      cat memory-bank/techContext.md memory-bank/consolidated_learnings.md >> .nexus/active-context.md
      ;;
    "testing")
      cat memory-bank/testingPatterns.md memory-bank/knownIssues.md >> .nexus/active-context.md
      ;;
  esac
```

### Phase 3: Context Optimization
```markdown
# Apply token-nutrition compression to maintain efficiency
execute_command: |
  awk '(/implemented|fixed|added|removed|discovered/){print} \
       (/INFO/){info++} info>5 && /^INFO/{next} \
       {print} END{if(info>5) print "[INFO]",info,"lines suppressed"}' \
  .nexus/active-context.md > .nexus/active-context.optimized.md
```

## Integration Points

- **Memory Bank**: Reads project patterns and technical context [3](#33-2) 
- **Nexus Core**: Receives task phase information and context requirements
- **Continuous Learning**: Logs prediction accuracy for improvement

This agent ensures that the Nexus system always has the right context at the right time, dramatically improving execution efficiency.
```

### 2. Decision Optimizer Agent

```markdown
---
description: Quantum-enhanced decision optimization agent that uses true randomness for unbiased architectural choices
author: Cline (AI Decision Optimization)
version: 1.0
tags: ["quantum", "decision", "optimization", "nexus-agent"]
globs: ["**/*"] # Works with Nexus orchestration
---

# Nexus Decision Optimizer Agent

**Objective:** Provide unbiased, quantum-enhanced decision making for critical architectural and technical choices within the Nexus system.

## Quantum Decision Process

### Phase 1: Decision Identification
```markdown
# Identify decisions requiring quantum optimization
execute_command: |
  # Scan for decision points in agent outputs
  grep -h "DECISION REQUIRED\|CHOICE\|OPTION" .nexus/agents/*/output.md > .nexus/pending-decisions.txt
  
  # Categorize decisions by type
  awk '/architecture/ {print "arch"} /database/ {print "db"} /api/ {print "api"}' .nexus/pending-decisions.txt > .nexus/decision-types.txt
```

### Phase 2: Quantum Randomness Generation
```markdown
# Generate true quantum randomness for decision seeding
execute_command: |
  # Primary: ANU Quantum Random Number Generator
  if curl -s "https://qrng.anu.edu.au/api/json-bin/" > .nexus/quantum-data.json; then
    jq -r '.data' .nexus/quantum-data.json | cut -c1-32 > .nexus/quantum-seed.txt
  else
    # Fallback: OpenSSL cryptographically secure random
    openssl rand -hex 16 > .nexus/quantum-seed.txt
  fi
```

### Phase 3: Decision Optimization
```markdown
# Apply quantum-seeded optimization to decision options
execute_command: |
  seed=$(cat .nexus/quantum-seed.txt)
  python3 -c "
import random, json, sys
random.seed(int('$seed', 16))
  
# Load decision options
with open('.nexus/decision-options.json') as f:
    decisions = json.load(f)
  
for decision, options in decisions.items():
    # Apply Fisher-Yates shuffle with quantum seed
    random.shuffle(options)
    print(f'{decision}: {options[0]} (quantum-optimized)')
  
# Store audit trail
with open('.nexus/decision-audit.json', 'w') as f:
    json.dump({
        'seed': '$seed',
        'timestamp': '$(date -u +%Y-%m-%dT%H:%M:%SZ)',
        'decisions': decisions
    }, f, indent=2)
"
```

### Phase 4: Decision Documentation
```markdown
# Document quantum-enhanced decisions with full audit trail
execute_command: |
  echo "## Quantum-Enhanced Decisions - $(date)" >> memory-bank/quantumDecisions.md
  echo "Seed: $(cat .nexus/quantum-seed.txt)" >> memory-bank/quantumDecisions.md
  cat .nexus/decision-result.md >> memory-bank/quantumDecisions.md
  echo "" >> memory-bank/quantumDecisions.md
```

## Integration with Memory Bank
- **Context Input**: Read project constraints and architectural patterns [3](#33-2) 
- **Audit Storage**: Store quantum decisions with full reproducibility information
- **Learning Integration**: Track decision effectiveness for future optimization

This agent ensures that all critical decisions within the Nexus system are free from cognitive bias and fully auditable.
```


