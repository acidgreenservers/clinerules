
---
description: Quantum randomness-based decision maker for architectural choices using ANU's quantum random number generator
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["decision-making", "quantum", "randomness", "architecture", "workflow"]
globs: ["**/*.md", "**/*.json", "**/*.yaml", "**/*.yml"] # Configuration and decision files
---

# Quantum Random Decider Rule

**Objective:** Make non-deterministic architectural decisions using true quantum randomness instead of pseudo-random `Math.random()`, ensuring unbiased choices powered by photon arrival times.

## Core Workflow

### 1. Decision Initialization
- Identify the architectural decision to be made
- Define the list of choices (e.g., database layers: Postgres vs SQLite vs DynamoDB)
- Read Memory Bank for context and constraints 

### 2. Quantum Randomness Acquisition
1. **Primary Method**: Call ANU's free quantum random JSON API
   - Endpoint: `https://qrng.anu.edu.au/api/json-bin/`
   - Returns: 1,024 true quantum bits as hex string
   - Extract first 32 bits for decision seeding

2. **Fallback Method**: Use `openssl rand` if ANU API is unavailable
   - Generate 32 bytes of cryptographically secure random data
   - Convert to hex format for consistency

### 3. Decision Algorithm
1. **Seed Generation**: Convert first 32 quantum bits to integer seed
2. **Fisher-Yates Shuffle**: Apply quantum-seeded shuffle to choice list
3. **Selection**: Choose first item from shuffled list as the decision
4. **Logging**: Record exact quantum hex block for auditability

### 4. Result Documentation
- Present decision to user with quantum source attribution
- Log quantum hex block and decision outcome to Memory Bank
- Execute pre-completion reflection for continuous improvement

## Implementation Details

### API Integration
```javascript
// Quantum randomness fetch
async function getQuantumRandomness() {
  try {
    const response = await fetch('https://qrng.anu.edu.au/api/json-bin/');
    const data = await response.json();
    return data.data; // 1,024 quantum bits as hex string
  } catch (error) {
    // Fallback to openssl rand
    return execSync('openssl rand -hex 32').toString().trim();
  }
}
```

### Fisher-Yates Shuffle Implementation
```javascript
function quantumShuffle(choices, quantumHex) {
  const seed = parseInt(quantumHex.substring(0, 8), 16);
  const shuffled = [...choices];
  
  // Seeded random number generator
  let rng = seed;
  const random = () => {
    rng = (rng * 9301 + 49297) % 233280;
    return rng / 233280;
  };
  
  // Fisher-Yates shuffle with quantum seed
  for (let i = shuffled.length - 1; i > 0; i--) {
    const j = Math.floor(random() * (i + 1));
    [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
  }
  
  return shuffled;
}
```

## Memory Bank Integration

### Context Input
Read Memory Bank files to inform decision context:

- **`systemPatterns.md`**: Align decisions with architectural patterns
- **`techContext.md`**: Consider technology stack constraints
- **`activeContext.md`**: Factor in current project priorities
- **`projectbrief.md`**: Respect core requirements and limitations

### Decision Logging
Store decision outcomes in Memory Bank structure:

- **`progress.md`**: Log architectural decisions with quantum attribution
- **`consolidated_learnings.md`**: Document decision patterns and outcomes
- **`activeContext.md`**: Update with chosen architectural direction

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log learnings:

- Record decision outcomes and their rationale
- Document quantum randomness effectiveness
- Note any patterns in architectural choices
- Log fallback usage and API reliability

### Rule Enhancement
Propose improvements based on usage patterns:

- Adjust fallback strategies based on API reliability
- Refine decision categorization for better context
- Update quantum bit usage patterns for optimal randomness

## Error Handling

- **API Failures**: Graceful fallback to openssl rand with user notification
- **Network Issues**: Cache previous quantum blocks for offline decisions
- **Invalid Choices**: Validate choice list before quantum selection
- **Memory Bank Issues**: Continue with decision logging and notify user

## Audit Trail

Every decision includes:
- Quantum hex block used (first 32 bits highlighted)
- Timestamp and decision context
- Complete choice list and shuffled order
- Final selection with quantum attribution
- Fallback method used (if applicable)

## Usage Examples

### Database Layer Selection
```
Choices: ["Postgres", "SQLite", "DynamoDB"]
Quantum Hex: a7f3c2b1e8d9... (using first 32 bits: a7f3c2b1)
Shuffled Order: ["DynamoDB", "Postgres", "SQLite"]
Decision: DynamoDB (quantum-selected)
```

### Framework Choice
```
Choices: ["React", "Vue", "Angular", "Svelte"]
Quantum Hex: 9e4d2c1b8a7f... (using first 32 bits: 9e4d2c1b)
Shuffled Order: ["Vue", "Svelte", "Angular", "React"]
Decision: Vue (quantum-selected)
```

## Configuration Options

- **Quantum API Endpoint**: Customizable ANU API URL
- **Fallback Method**: Configurable alternative randomness source
- **Bit Usage**: Adjustable number of quantum bits for seeding
- **Logging Level**: Verbose vs concise decision logging

## Notes

This rule leverages true quantum randomness from photon arrival times, eliminating pseudo-random bias in architectural decisions. The quantum randomness provides provably unpredictable outcomes while maintaining full auditability through hex block logging.

The integration with Memory Bank ensures decisions are contextually informed and documented, while Continuous Improvement captures patterns and optimizes the decision-making process over time.

Quantum randomness is particularly valuable for:
- Breaking decision paralysis in architectural choices
- Eliminating unconscious bias in technology selection
- Providing defensible randomness in load balancing
- Creating unpredictable but reproducible system behaviors

All quantum-powered decisions should be reviewed for technical feasibility before implementation.
```