
---
description: Genetic algorithm for automated code evolution using AST mutations, integrated with Memory Bank and Continuous Improvement systems
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["automation", "genetic-algorithm", "ast", "code-evolution", "workflow"]
globs: ["**/*.{js,ts,jsx,tsx,py,java,cpp,c}"] # Languages with AST support
---

# Genetic Code Evolution Rule

**Objective:** Treat the AST as DNA—mutate, breed, and select the fittest code version without human keystrokes, while leveraging Cline's Memory Bank and Continuous Improvement systems for context-aware evolution and organizational learning.

## Core Workflow

### 1. Initialization
- Read Memory Bank files to understand project context and constraints
- Parse current codebase using appropriate AST parser (babel for JS/TS, tree-sitter for other languages)
- Establish fitness criteria based on project requirements

### 2. Evolution Process
1. **AST Snapshot**: Capture current AST structure
2. **Mutation Generation**: Create 10 random mutations:
   - Delete node
   - Swap siblings
   - Inline variable
   - Extract function
   - Rename identifier
   - Merge statements
   - Split expression
   - Remove dead code
   - Optimize imports
   - Simplify logic
3. **Fitness Evaluation**: Auto-run test suite and calculate score:

   fitness_score = (passing_tests * 10) - line_count
   
4. **Selection**: Keep top 3 performers
5. **Crossover**: Combine successful mutations
6. **Repeat** for N generations or until score plateaus

### 3. Results Presentation
- Present winning diff to user
- Provide one-line explanation of fitness improvement
- Store results in Memory Bank

## Memory Bank Integration

### Context Input
Read Memory Bank files to guide evolution strategy:

- **`systemPatterns.md`**: Align mutations with architectural decisions
- **`techContext.md`**: Configure language-specific parser settings
- **`activeContext.md`**: Focus evolution on current work priorities
- **`projectbrief.md`**: Respect core requirements and constraints

### Results Storage
Store evolution outcomes in Memory Bank structure:

- **`progress.md`**: Add fitness improvements as measurable achievements
- **`consolidated_learnings.md`**: Document successful mutation patterns
- **`activeContext.md`**: Update with effective evolution parameters

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log learnings:

- Record most effective mutations
- Document fitness score patterns
- Note project-specific optimization insights
- Log convergence behaviors

### Rule Enhancement
Propose improvements to itself based on results:

- Adjust mutation probabilities based on success rates
- Refine fitness scoring formulas
- Update language-specific handling patterns

## Research Assistant Integration

- Use Research Assistant to investigate optimal genetic algorithm parameters for specific codebases
- Store research findings about effective mutation strategies in Memory Bank
- Leverage discovered techniques to improve evolution effectiveness

## Implementation Requirements

### Prerequisites
1. **AST Parser Support**: Language must have compatible parser (babel, tree-sitter, etc.)
2. **Test Suite**: Project must have automated tests for fitness evaluation
3. **Memory Bank**: Must be initialized with project context

### Execution Protocol
1. **Read Memory Bank** at start like other functional rules 
2. **Execute pre-completion reflection** to log learnings 
3. **Store results** in appropriate Memory Bank files
4. **Propose rule improvements** when significant patterns emerge

### Configuration Options
- **Generations**: Number of evolution cycles (default: 10)
- **Population Size**: Mutations per generation (default: 10)
- **Selection Size**: Survivors per generation (default: 3)
- **Fitness Weight**: Test score multiplier (default: 10)
- **Language**: Target language for AST parsing

## Cross-Functional Workflows

### Context-Aware Evolution
Memory Bank provides project context → Genetic evolution applies domain-aware mutations → Results improve future context

### Learning Loop
Evolution runs → Continuous improvement captures learnings → Rules are refined → Future evolutions are more effective

### Research Pipeline
Research discovers techniques → Evolution applies them → Memory Bank preserves knowledge

## Error Handling

- **Parse Failures**: Skip files with syntax errors, log to Memory Bank
- **Test Failures**: Handle test suite crashes gracefully
- **Memory Bank Issues**: Continue evolution without context if Memory Bank unavailable
- **AST Limitations**: Fall back to text-based mutations for unsupported languages



## Notes

This rule represents a specialized automation tool that benefits significantly from the contextual awareness of Memory Bank and the learning mechanisms of Continuous Improvement. These integrations create a symbiotic relationship where each system enhances the others' effectiveness while maintaining their core functionalities.

The genetic evolution approach is particularly effective for:
- Code optimization and refactoring
- Performance improvements
- Dead code elimination
- Test coverage enhancement
- Code size reduction

Results should always be reviewed by humans before application to production codebases.