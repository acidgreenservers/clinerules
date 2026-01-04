
---
description: Persistent undo stack system that shadows file operations and commands, enabling time-travel functionality across chat sessions with branching capabilities
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["undo", "state-management", "snapshots", "workflow", "persistence"]
globs: ["**/*"] # Applies to all file operations
---

# Reversible Time Machine Rule

**Objective:** Give Cline an undo stack that works even after chat sessions are closed by shadowing file operations, creating snapshots, and providing time-travel commands with branching capabilities.

## Core Workflow

### 1. Operation Shadowing
- Intercept every `write_to_file` or `execute_command` that mutates state
- Read Memory Bank for project context and snapshot preferences 
- Create pre-action snapshot and record inverse operation

### 2. Snapshot Management
- Copy files to `.cline-snapshots/` with timestamp naming
- Record inverse commands in `undo-stack.json`
- Maintain tree-structured undo history (not just linear)

### 3. Command Interface
- `/rewind <N>` - Walk back N steps in the undo stack
- `/branch <name>` - Fork undo stack to explore alternate paths
- Garbage collection after 30 days or repo tag movement

## Implementation Details

### Snapshot Creation Process
```javascript
// Before any state-mutating operation
function createSnapshot(operation) {
  const timestamp = Date.now();
  const snapshotDir = `.cline-snapshots/${timestamp}`;
  
  // Copy affected files
  if (operation.type === 'write_to_file') {
    fs.copyFileSync(operation.filePath, `${snapshotDir}/${operation.filePath}`);
  }
  
  // Record inverse operation
  const inverse = generateInverseCommand(operation);
  undoStack.push({
    timestamp,
    operation,
    inverse,
    snapshot: snapshotDir
  });
  
  saveUndoStack();
}
```

### Inverse Command Generation
```javascript
function generateInverseCommand(operation) {
  switch (operation.type) {
    case 'write_to_file':
      return {
        type: 'restore_file',
        path: operation.filePath,
        fromSnapshot: operation.timestamp
      };
    case 'execute_command':
      return {
        type: 'revert_command',
        command: generateRevertCommand(operation.command)
      };
    case 'delete_file':
      return {
        type: 'restore_file',
        path: operation.filePath,
        fromSnapshot: operation.timestamp
      };
  }
}
```

### Slash Command Implementation

#### /rewind <N> Command
```bash
# Walk back N steps in undo stack
function rewind(steps) {
  for (let i = 0; i < steps; i++) {
    const operation = undoStack.pop();
    if (operation) {
      executeInverse(operation.inverse);
    }
  }
  saveUndoStack();
}
```

#### /branch <name> Command
```bash
# Fork undo stack for alternate exploration
function branch(name) {
  const branchStack = {
    name,
    parent: currentBranch,
    stack: [...undoStack],
    createdAt: Date.now()
  };
  
  branches[name] = branchStack;
  saveBranches();
}
```

## Memory Bank Integration

### Context Input
Read Memory Bank files to configure snapshot behavior:

- **`systemPatterns.md`**: Understand which files are critical to snapshot
- **`techContext.md`**: Configure snapshot strategies for different file types
- **`activeContext.md`**: Focus on current work priorities for selective snapshotting
- **`projectbrief.md`**: Respect project-specific snapshot requirements

### Results Storage
Store time machine operations in Memory Bank structure:

- **`progress.md`**: Log major state changes and branch points
- **`consolidated_learnings.md`**: Document effective snapshot strategies
- **`activeContext.md`**: Update with current branch and state information

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log time machine insights:

- Record which operations benefit most from snapshotting
- Document effective inverse command patterns
- Note storage efficiency and performance patterns
- Log branching behavior and usage patterns

### Rule Enhancement
Propose improvements based on usage patterns:

- Refine snapshot strategies based on project types
- Adjust garbage collection timing based on storage patterns
- Optimize inverse command generation for different operation types

## Data Structures

### Undo Stack Format
```json
{
  "currentBranch": "main",
  "branches": {
    "main": {
      "stack": [
        {
          "timestamp": 1698765432100,
          "operation": {
            "type": "write_to_file",
            "path": "src/app.js",
            "content": "..."
          },
          "inverse": {
            "type": "restore_file",
            "path": "src/app.js",
            "fromSnapshot": 1698765432000
          },
          "snapshot": ".cline-snapshots/1698765432000"
        }
      ],
      "createdAt": 1698765432000
    }
  }
}
```

### Snapshot Directory Structure

.cline-snapshots/
├── 1698765432000/
│   ├── src/
│   │   ├── app.js
│   │   └── utils.js
│   └── package.json
├── 1698765432500/
│   └── src/
│       └── app.js
└── undo-stack.json


## Configuration Options

### Snapshot Behavior
- **Snapshot Scope**: Full project vs selective file snapshotting
- **Compression**: Enable/disable snapshot compression for storage efficiency
- **Frequency**: Snapshot every operation vs batch operations
- **Exclusions**: Files/directories to exclude from snapshotting

### Branch Management
- **Auto-branch**: Create branches automatically for major experiments
- **Branch Naming**: Convention for automatic branch names
- **Merge Strategy**: How to handle merging branches back to main

### Garbage Collection
- **Retention Period**: Default 30 days, configurable per project
- **Size Limits**: Maximum storage usage before cleanup
- **Tag-based Cleanup**: Clean snapshots when repo tags are moved

## Error Handling

### Snapshot Failures
- **Disk Space**: Graceful degradation when storage is full
- **Permission Issues**: Skip files that can't be snapshot and log warnings
- **Large Files**: Implement size limits and alternative strategies

### Undo Failures
- **Missing Snapshots**: Detect and report corrupted or missing snapshots
- **Conflicts**: Handle conflicts when current state differs from expected
- **Partial Rollbacks**: Allow partial undo when some operations fail

## Performance Considerations

### Optimization Strategies
- **Incremental Snapshots**: Only snapshot changed files
- **Compression**: Use compression for large text files
- **Async Operations**: Perform snapshotting asynchronously to avoid blocking
- **Selective Tracking**: Track only critical files based on project patterns

### Storage Management
- **Deduplication**: Avoid storing duplicate file versions
- **Cleanup Policies**: Aggressive cleanup for temporary files
- **Monitoring**: Track storage usage and alert when thresholds are exceeded

## Usage Examples

### Basic Rewind

User: /rewind 3
System: Restored to state from 3 operations ago
- Restored src/app.js from snapshot 1698765432000
- Reverted command "npm install new-package"
- Deleted file src/temp.js


### Branch Creation

User: /branch experiment-api
System: Created branch "experiment-api" from current state
- Current branch: experiment-api
- Parent branch: main
- Stack preserved: 12 operations


### Branch Switching

User: /branch main
System: Switched to branch "main"
- Restored to main branch state
- Current operations: 8
- Experiment branch preserved for later


## Integration with Other Rules

### Cross-Functional Workflows
- **Genetic Code Evolution**: Create branches for each evolution experiment
- **Git Workflow**: Sync time machine branches with git branches
- **Maintenance**: Use snapshots before major maintenance operations

### Tool Chain Integration
- Connect with VSCode's version control for visual diffing
- Integrate with git for commit-based checkpointing
- Sync with cloud storage for backup and collaboration

## Security Considerations

### Snapshot Security
- **Sensitive Data**: Exclude sensitive files from snapshots (API keys, passwords)
- **Encryption**: Optional encryption for snapshot storage
- **Access Control**: Restrict access to snapshot directory

### Cleanup Security
- **Secure Deletion**: Ensure sensitive data is properly deleted
- **Backup Policies**: Handle sensitive data in backup procedures
- **Audit Trail**: Maintain audit log of time machine operations

## Notes

This rule transforms Cline's state management from linear, session-bound operations to a sophisticated tree-structured system that persists across sessions. The integration with Memory Bank provides context-aware snapshotting, while Continuous Improvement learns from usage patterns to optimize the time machine's behavior.

The reversible time machine is particularly valuable for:
- Experimentation with different approaches without losing work
- Safe exploration of major refactoring or architectural changes
- Teaching and learning by stepping through complex operations
- Recovery from mistakes or unwanted changes
- Creating reproducible development workflows

All time machine operations should be documented and the system should provide clear feedback about current state, available branches, and storage usage.

The rule is designed to work as a sophisticated state management system that provides persistent undo capabilities beyond VSCode's limitations while integrating seamlessly with Cline's existing ecosystem.

The workflow provides comprehensive state management through operation shadowing, snapshot creation, inverse command generation, and branching capabilities. It includes sophisticated features like garbage collection, performance optimization, and security considerations while maintaining the tree-structured undo history that goes beyond VSCode's linear, session-bound limitations.

This rule represents a significant advancement in Cline's state management capabilities, enabling safe experimentation, easy recovery from mistakes, and sophisticated development workflows that persist across sessions.