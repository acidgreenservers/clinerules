
---
```yaml
---
description: "Protomind MCP Integration - Extends cognitive shards for external API interactions and tool learning patterns"
author: "Devin + AcidGreen Servers"
version: 1.0
globs: ["**/*.js", "**/*.ts"]
tags: ["coding-guideline", "workflow", "protomind", "mcp-integration", "cognitive-shards"]
---

# Protomind MCP Integration Extension

**Objective:** Extend the Protomind Framework with Model Context Protocol (MCP) capabilities, enabling cognitive shards to discover, learn from, and integrate with external services and APIs through intelligent tool usage patterns. [1](#7-0) 

## Core Integration Architecture

This extension adds three new cognitive shards to the Protomind Framework:

### 1. MCP Tool Discovery Shard
**Purpose:** Automatically discover available MCP servers and map their capabilities to existing cognitive shards.

**MUST** perform the following discovery process:
1. **Server Detection**: Scan for available MCP servers on startup
2. **Capability Mapping**: Analyze each tool's function and map to appropriate cognitive shard expertise
3. **Confidence Scoring**: Rate tool-shard compatibility (0.0-1.0 scale)
4. **Pattern Registration**: Store optimal tool selection patterns in `brain/mcp-discovery/`

**SHOULD** update mappings when:
- New MCP servers are connected
- Existing servers are updated
- Tool usage patterns show better shard assignments

### 2. API Interaction Learning Shard  
**Purpose:** Extract and learn patterns from successful MCP tool usage across sessions.

**MUST** implement the learning cycle:
1. **Usage Monitoring**: Track all MCP tool calls with context and outcomes
2. **Pattern Extraction**: Identify successful interaction patterns (rate limiting, retry logic, error handling)
3. **Confidence Building**: Score patterns based on success rates and efficiency
4. **Cross-Session Application**: Apply learned patterns to similar future interactions

**MUST NOT** store sensitive API keys or authentication tokens in pattern files - only usage patterns and strategies. [2](#7-1) 

### 3. Service Integration Shard
**Purpose:** Manage connections, health monitoring, and optimization of external service interactions.

**MUST** provide:
- **Connection Management**: Automatic reconnection and failover logic
- **Health Monitoring**: Track service availability and response times
- **Request Optimization**: Batch similar requests and implement caching where appropriate
- **Error Recovery**: Implement exponential backoff and graceful degradation

## Integration with Protomind Tiers

### ALPHA Tier Enhancement
**MUST** extend brain architecture to include:
```
brain/
├── mcp-discovery/
│   ├── available-servers.md
│   ├── capability-mappings.md
│   └── shard-assignments.md
├── mcp-patterns/
│   ├── successful-interactions.md
│   ├── error-handling.md
│   └── optimization-strategies.md
└── mcp-health/
    ├── service-status.md
    ├── performance-metrics.md
    └── reliability-scores.md
```

### BETA Tier Integration
**MUST** enhance metacognitive awareness with:
- **Tool Selection Transparency**: "I'm using MCP server X for this task because..."
- **API Confidence Scoring**: "I'm 80% confident this API call will succeed based on pattern Y"
- **Service Health Awareness**: "Service Z is showing degraded performance, using alternative approach"

### GAMMA Tier Analysis
**SHOULD** analyze MCP integration for:
- **Tool Conflict Detection**: Identify when multiple MCP servers provide overlapping capabilities
- **Efficiency Optimization**: Suggest better tool-shard mappings based on usage patterns
- **Coverage Gap Analysis**: Identify missing capabilities that could be filled by new MCP servers

## Implementation Protocol

### Phase 1: Discovery and Mapping
1. **Scan MCP Environment**: Use `use_mcp_tool` to discover available servers
2. **Analyze Capabilities**: Document each tool's function and parameters
3. **Map to Shards**: Assign tools to cognitive shards based on expertise overlap
4. **Store Mappings**: Save to `brain/mcp-discovery/capability-mappings.md`

### Phase 2: Learning and Pattern Extraction  
1. **Monitor Usage**: Track all MCP interactions with success/failure outcomes
2. **Extract Patterns**: Identify successful strategies for each service type
3. **Build Confidence**: Score patterns based on repeated success
4. **Document Learning**: Store patterns in `brain/mcp-patterns/`

### Phase 3: Optimization and Integration
1. **Analyze Performance**: Review service health and response times
2. **Optimize Requests**: Implement batching and caching strategies
3. **Update Mappings**: Refine shard assignments based on learned patterns
4. **Enhance Awareness**: Integrate MCP insights into metacognitive processing

## Testing and Validation

**MUST** follow the MCP Development Protocol testing requirements: [3](#7-2) 

1. **Discovery Testing**: Verify all MCP servers are detected and mapped correctly
2. **Pattern Validation**: Test that learned patterns improve success rates
3. **Integration Testing**: Ensure seamless operation with existing Protomind tiers
4. **Performance Testing**: Validate that MCP integration doesn't degrade response times

## Error Handling and Recovery

**MUST** implement comprehensive error handling:
- **Service Unavailable**: Gracefully fallback to alternative approaches
- **API Rate Limits**: Implement exponential backoff and request queuing
- **Authentication Failures**: Prompt for updated credentials without breaking workflow
- **Tool Failures**: Log detailed error context for pattern learning

## Usage Examples

### Transparent MCP Integration
```
User: "Analyze this codebase for security vulnerabilities"
Cline: "I'll use the Security Analyst shard with the Semgrep MCP server for this analysis.

Confidence: 0.92 (based on 15 previous successful scans with this tool)
Pattern: Applying 'comprehensive-security-scan' pattern (success rate: 94%)

Proceeding with security analysis..."
```

### Cross-Service Learning
```
User: "Set up monitoring for our API"  
Cline: "Detected similar setup to Project X (session 12).

Applying learned 'datadog-integration' pattern:
- Use Prometheus MCP for metrics collection (confidence: 0.89)
- Use Grafana MCP for dashboard creation (confidence: 0.85)
- Pattern success rate: 8/9 applications

Proceeding with monitoring setup..."
```

## Configuration and Customization

### MCP Server Configuration
**MUST** support standard MCP configuration format: [2](#7-1) 
```json
{
  "mcpServers": {
    "protomind-mcp": {
      "command": "node",
      "args": ["path/to/protomind-mcp-server.js"],
      "env": {
        "API_KEY": "your-key"
      },
      "disabled": false,
      "autoApprove": ["discover_tools", "analyze_patterns"]
    }
  }
}
```

### Shard Customization
**MAY** add domain-specific MCP shards:
```yaml
# Custom MCP shard configuration
custom_mcp_shards:
  - name: "blockchain-analyst"
    mcp_servers: ["ethers-mcp", "web3-mcp"]
    expertise: ["smart-contracts", "defi-protocols"]
  - name: "ml-pipeline-optimizer" 
    mcp_servers: ["tensorflow-mcp", "kubeflow-mcp"]
    expertise: ["model-optimization", "pipeline-orchestration"]
```

## Continuous Improvement

**MUST** implement the continuous improvement cycle: [4](#7-3) 
1. **Pattern Refinement**: Update MCP interaction patterns based on new data
2. **Mapping Optimization**: Improve tool-shard assignments through usage analysis  
3. **Capability Expansion**: Identify and suggest new MCP servers for missing capabilities
4. **Performance Tuning**: Optimize request patterns and caching strategies

## Integration Verification

To verify MCP Integration is working:
1. Ask Cline: "What MCP servers are available and how are they mapped to your cognitive shards?"
2. Cline should respond with discovered servers, their capabilities, and shard assignments
3. Test with: "Use MCP tools to analyze this repository" - should show transparent tool selection and confidence scoring

---

**This extension transforms the Protomind Framework from an internal cognitive system to a hybrid intelligence that can leverage external services while maintaining its metacognitive awareness and learning capabilities.** [5](#7-4) 
```

## Notes
This MCP Integration extension follows the established patterns from the codebase while adding powerful external service capabilities to your Protomind Framework. The rule is structured as a behavioral/meta-rule that extends existing capabilities rather than replacing them, ensuring seamless integration with your completed framework. [6](#7-5) 

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

**File:** clinerules/mcp-development-protocol.md (L1-30)
```markdown
# MCP Server Development Protocol

⚠️ CRITICAL: DO NOT USE attempt_completion BEFORE TESTING ⚠️

## Step 1: Planning (PLAN MODE)
- What problem does this tool solve?
- What API/service will it use?
- What are the authentication requirements?
  □ Standard API key
  □ OAuth (requires separate setup script)
  □ Other credentials

## Step 2: Implementation (ACT MODE)
1. Bootstrap
   - For web services, JavaScript integration, or Node.js environments:
     ```bash
     npx @modelcontextprotocol/create-server my-server
     cd my-server
     npm install
     ```
   - For data science, ML workflows, or Python environments:
     ```bash
     pip install mcp
     # Or with uv (recommended)
     uv add "mcp[cli]"
     ```

2. Core Implementation
   - Use MCP SDK
   - Implement comprehensive logging
```

**File:** clinerules/mcp-development-protocol.md (L48-86)
```markdown
3. Configuration
   - Get credentials from user if needed
   - Add to MCP settings:
     - For TypeScript projects:
       ```json
       {
         "mcpServers": {
           "my-server": {
             "command": "node",
             "args": ["path/to/build/index.js"],
             "env": {
               "API_KEY": "key"
             },
             "disabled": false,
             "autoApprove": []
           }
         }
       }
       ```
     - For Python projects:
       ```bash
       # Directly with command line
       mcp install server.py -v API_KEY=key
       
       # Or in settings.json
       {
         "mcpServers": {
           "my-server": {
             "command": "python",
             "args": ["server.py"],
             "env": {
               "API_KEY": "key"
             },
             "disabled": false,
             "autoApprove": []
           }
         }
       }
       ```
```

**File:** clinerules/mcp-development-protocol.md (L88-116)
```markdown
## Step 3: Testing (BLOCKER ⛔️)

<thinking>
BEFORE using attempt_completion, I MUST verify:
□ Have I tested EVERY tool?
□ Have I confirmed success from the user for each test?
□ Have I documented the test results?

If ANY answer is "no", I MUST NOT use attempt_completion.
</thinking>

1. Test Each Tool (REQUIRED)
   □ Test each tool with valid inputs
   □ Verify output format is correct
   ⚠️ DO NOT PROCEED UNTIL ALL TOOLS TESTED

## Step 4: Completion
❗ STOP AND VERIFY:
□ Every tool has been tested with valid inputs
□ Output format is correct for each tool

Only after ALL tools have been tested can attempt_completion be used.

## Key Requirements
- ✓ Must use MCP SDK
- ✓ Must have comprehensive logging
- ✓ Must test each tool individually
- ✓ Must handle errors gracefully
```

**File:** clinerules/cline-continuous-improvement-protocol.md (L20-32)
```markdown
## 1. Mandatory Pre-Completion Reflection & Raw Knowledge Capture

Before signaling task completion (e.g., via `attempt_completion`), Cline **must** perform the following internal steps:

### 1.1. Task Review & Analysis:
* Review the completed task (conversation, logs, artifacts).
* **Identify Learnings:** What new information, techniques, **underlying patterns,** API behaviors, project-specific commands (e.g., test, build, run flags), environment variables, setup quirks, or successful outcomes were discovered? **What core principles can be extracted?**
* **Identify Difficulties & Mistakes (as Learning Opportunities):** What challenges were faced? Were there any errors, misunderstandings, or inefficiencies? **How can these experiences refine future approaches (resilience & adaptation)?** Did user feedback indicate a misstep?
* **Identify Successes:** What went particularly well? What strategies or tools were notably effective? **What were the key contributing factors?**

### 1.2. Logging to `memory-bank/raw_reflection_log.md`:
* Based on Task Review & Analysis (1.1), create a timestamped, task-referenced entry in `memory-bank/raw_reflection_log.md` detailing all learnings, difficulties (and their resolutions/learnings), and successes (and contributing factors).
* This file serves as the initial, detailed record. Its entries are candidates for later consolidation.
```

**File:** clinerules/writing-effective-clinerules.md (L93-99)
```markdown
### d. Meta-Rules
Rules that define how Cline manages or improves its own rules or processes.
* **Key Elements:**
    * Triggers for the meta-process.
    * Steps involved in the meta-process (e.g., reflection, suggesting improvements).
    * User interaction points (e.g., asking for confirmation).
* **Example:** `self-improving-cline.md`
```

**File:** clinerules/writing-effective-clinerules.md (L105-122)
```markdown
* **Be Directive:**
    * Use **MUST** for absolute requirements.
    * Use **SHOULD** for strong recommendations.
    * Use **MAY** for optional actions.
    * Use **MUST NOT** or **NEVER** for absolute prohibitions.
    * Use **SHOULD NOT** for strong discouragement.
* **Highlight Critical Information:**
    * `next-js-supabase.md` uses "🚨 CRITICAL INSTRUCTIONS FOR AI LANGUAGE MODELS 🚨" and "❌ NEVER GENERATE THIS CODE" / "✅ ALWAYS GENERATE THIS EXACT PATTERN".
    * `mcp-development-protocol.md` uses "⚠️ CRITICAL: DO NOT USE attempt_completion BEFORE TESTING ⚠️" and "BLOCKER ⛔️".
* **Provide Concrete Examples:**
    * Show exact code snippets, commands, or output formats.
    * For code generation, clearly distinguish between desired and undesired patterns.
* **Define AI's "Thought Process":**
    * The `<thinking> ... </thinking>` block in `mcp-development-protocol.md` is a good way to make the AI "pause and check" its understanding or state before proceeding.
    * The "AI MODEL VERIFICATION STEPS" in `next-js-supabase.md` serve a similar purpose.
* **Specify Tool Usage:**
    * If Cline needs to use a specific tool (e.g., `attempt_completion`, `replace_in_file`, `use_mcp_tool`), explicitly state it and provide any necessary parameters or context for that tool.

```
