
---

```markdown
---
description: Systematic codebase maintenance workflow for identifying redundant code, unused functions, optimization opportunities, and potential errors
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["maintenance", "code-quality", "automation", "workflow", "analysis"]
globs: ["**/*"] # Applies to entire codebase
---

# Maintenance-Time Workflow Rule

**Objective:** Systematically crawl the codebase to identify redundant code, unused functions, optimization opportunities, and potential errors. Document all findings and actions in the Maintenance page while integrating with Cline's Memory Bank and Continuous Improvement systems.

## When to Run Maintenance

### Scheduled Maintenance
- After major feature additions
- Before version releases
- Monthly routine maintenance
- When performance degrades
- After significant refactoring

### Trigger Phrases
Activate when user says any of:
- "Run maintenance"
- "Code cleanup time"
- "Scan for issues"
- "Maintenance check"
- "Audit the code"

## Pre-Maintenance Checklist

Before starting ANY maintenance session:

### 1. Read Current Maintenance Page
- Location: `src/pages/maintenance.html` (or wherever located)
- Note current version number
- Review existing todos and known issues
- Check last maintenance date

### 2. Read Memory Bank for Context
Read Memory Bank files to understand project state [1](#9-0) :
- **`activeContext.md`**: Current work focus and recent changes
- **`systemPatterns.md`**: Architecture and design patterns
- **`techContext.md`**: Technology stack and constraints
- **`progress.md`**: Current status and known issues

### 3. Update CONTEXT.md
```markdown
[YYYY-MM-DD HH:MM:SS] SESSION START - MAINTENANCE
Type: [Scheduled / User-Requested / Pre-Release]
Current Version: [e.g., v0.8.0.1]
Last Maintenance: [date from maintenance page]
Scope: [Full codebase / Specific component]
```

### 4. Create Maintenance Session Log
Start structured log for maintenance page:
```markdown
📅 [Date] - [Maintenance Type] Code Review
Assessed: [What was scanned]
Findings: [Summary of issues found]
Actions: [What was fixed/added to todos]
```

## Maintenance Crawl Procedure

### Phase 1: File Inventory & Structure Analysis

#### Step 1.1: Map the Codebase
```markdown
Scan directories:
- src/pages/ → List all HTML files
- src/assets/js/ → List all JS files  
- src/css/ → List all CSS files
- src/utils/ → List all utility files
- Root files → Check for config files, manifests, service workers

Document in session log:
- Total file count per directory
- New files since last maintenance
- Files that might be obsolete
- Any unnecessary debugging code (ask user if unsure)
```

#### Step 1.2: Check File Relationships
```markdown
For each HTML file, verify:
- Which CSS files are linked
- Which JS files are loaded
- Which utils are imported
- Are all linked files actually present?

Look for:
❌ Dead links (404 references)
❌ Unused CSS/JS files (not linked anywhere)
❌ Duplicate imports
```

### Phase 2: Code Quality Scan

#### Step 2.1: JavaScript Analysis
Scan EACH .js file for:

**🔴 Critical Issues (Fix Immediately)**
- ❌ Syntax errors
- ❌ Undefined variables used
- ❌ Functions called but not defined
- ❌ Missing dependencies (utils not loaded)
- ❌ Race conditions in async code
- ❌ Unhandled promise rejections
- ❌ Console errors in browser testing

**🟡 High Priority (Add to Todos)**
- ⚠️ Unused functions (defined but never called)
- ⚠️ Duplicate code across files
- ⚠️ Hard-coded values that should be constants
- ⚠️ Missing error handling (try-catch)
- ⚠️ Functions longer than 50 lines (refactor candidates)
- ⚠️ Complex nested logic (>3 levels deep)
- ⚠️ TODO/FIXME comments in code

**🟢 Medium Priority (Optimization Opportunities)**
- 💡 Inefficient loops (O(n²) when O(n) possible)
- 💡 Repeated DOM queries (cache selectors)
- 💡 Large functions that could be split
- 💡 Magic numbers without explanation
- 💡 Inconsistent naming conventions
- 💡 Missing JSDoc comments
- 💡 console.log statements left in production code

#### Step 2.2: CSS Analysis
Scan CSS files for:

**🔴 Critical Issues**
- ❌ Syntax errors
- ❌ Invalid properties
- ❌ Broken @import statements

**🟡 High Priority**
- ⚠️ Unused CSS classes (defined but never used in HTML)
- ⚠️ Duplicate selectors
- ⚠️ !important overuse
- ⚠️ Inline styles in HTML (should be in CSS)
- ⚠️ Non-responsive units (px instead of rem/em where appropriate)

**🟢 Medium Priority**
- 💡 CSS that could use variables (--var-name)
- 💡 Repeated color/spacing values (create theme variables)
- 💡 Long selector chains (>4 levels)
- 💡 Overly specific selectors

#### Step 2.3: HTML Analysis
Scan HTML files for:

**🔴 Critical Issues**
- ❌ Syntax errors
- ❌ Missing required attributes (alt text on images, etc.)
- ❌ Broken internal links
- ❌ Invalid HTML structure

**🟡 High Priority**
- ⚠️ Accessibility issues (missing ARIA labels, semantic HTML)
- ⚠️ Duplicate IDs
- ⚠️ Unused elements (display:none with no JS toggling)
- ⚠️ Inline event handlers (use addEventListener instead)

**🟢 Medium Priority**
- 💡 Missing meta tags
- 💡 Non-semantic HTML (too many divs)
- 💡 Images without width/height (causes layout shift)

### Phase 3: Utility & Module Analysis

#### Step 3.1: Utils Audit
For each file in `src/utils/`:
```markdown
Check:
1. Is this util actually used? (Search codebase for imports/usage)
2. Are all functions in this util used?
3. Is there duplicate functionality across utils?
4. Are utils properly documented?
5. Do utils have error handling?

Document:
- Unused utils → Candidate for removal
- Unused functions within utils → Candidate for removal  
- Missing documentation → Add to todos
```

#### Step 3.2: Dependency Check
```markdown
Verify external dependencies:
- Are all CDN links working?
- Are versions specified (not using 'latest')?
- Are there unused library imports?
- Any security vulnerabilities in versions?

Check for:
- Gun.js version and configuration
- IndexedDB wrapper libraries
- Chart libraries
- Any other external scripts
```

### Phase 4: Performance Analysis

#### Step 4.1: Asset Size Check
```markdown
Check file sizes:
- Large JS files (>100KB) → Optimization candidate
- Large CSS files (>50KB) → Optimization candidate  
- Uncompressed images → Should be optimized
- Duplicate images → Should be deduplicated

Tools to use:
- File system ls -lh
- Browser DevTools Network tab
- Lighthouse audit
```

#### Step 4.2: Load Performance
```markdown
Test each page:
1. Open in browser with DevTools
2. Check Network tab for load times
3. Run Lighthouse audit
4. Note any performance warnings

Look for:
- Render-blocking resources
- Unused CSS/JS being loaded
- Missing lazy loading on images
- Inefficient resource loading order
```

### Phase 5: Security & Best Practices

#### Step 5.1: Security Scan
```markdown
Check for:
❌ Exposed API keys or credentials
❌ Insecure localStorage usage (sensitive data)
❌ Missing input validation
❌ XSS vulnerabilities (innerHTML with user input)
❌ eval() usage
❌ document.write() usage

Verify:
✅ All user inputs are validated/sanitized
✅ Authentication is properly implemented
✅ Sessions are secure
✅ HTTPS is enforced (if applicable)
```

#### Step 5.2: Best Practices Check
```markdown
Verify:
- Consistent code style across files
- Proper error handling everywhere
- All promises have .catch() or try-catch
- No blocking synchronous operations
- Proper use of async/await
- Event listeners are cleaned up
- No memory leaks (event listener accumulation)
```

## Memory Bank Integration

### Context Input
Read Memory Bank files to inform maintenance decisions [2](#9-1) :

- **`systemPatterns.md`**: Understand architectural patterns for analysis
- **`techContext.md`**: Configure language-specific analysis tools
- **`activeContext.md`**: Focus on current priorities and recent changes
- **`projectbrief.md`**: Respect project requirements and constraints

### Results Storage
Store maintenance outcomes in Memory Bank structure:

- **`progress.md`**: Log maintenance results and code quality metrics
- **`consolidated_learnings.md`**: Document effective maintenance patterns
- **`activeContext.md`**: Update with current code quality status

## Continuous Improvement Integration

### Knowledge Capture
Execute pre-completion reflection to log maintenance insights [3](#9-2) :

- Record which types of issues are most prevalent
- Document effective analysis strategies
- Note patterns in code quality degradation
- Log successful optimization techniques

### Rule Enhancement
Propose improvements based on usage patterns [4](#9-3) :

- Refine analysis criteria based on project-specific patterns
- Adjust maintenance frequency based on code quality trends
- Update scanning tools and techniques for better coverage

## Maintenance Session Log Template

As you scan, maintain this structured log:
```markdown
📅 [Date] - [Maintenance Type] Code Review
Version: v0.X.X.X
Assessed: [List what was scanned]

🔴 CRITICAL ISSUES FOUND & FIXED:
1. [Issue description] → [Fix applied] → [File: location]
2. [Issue description] → [Fix applied] → [File: location]
Total Critical: [X] (All Fixed ✅)

🟡 HIGH PRIORITY ISSUES (Added to Todos):
1. [Issue description] → [Action needed] → [File: location]
2. [Issue description] → [Action needed] → [File: location]  
Total High Priority: [X]

🟢 OPTIMIZATION OPPORTUNITIES (Added to Todos):
1. [Optimization description] → [Potential benefit] → [File: location]
2. [Optimization description] → [Potential benefit] → [File: location]
Total Optimizations: [X]

📊 CODE HEALTH METRICS:
- Files Scanned: [X]
- Lines of Code: [~X] (estimated)
- Unused Code Removed: [X lines/functions]
- Duplicate Code Found: [X instances]
- Performance Score: [X/100] (Lighthouse average)

✅ IMPROVEMENTS MADE:
- Removed [X] unused functions
- Cleaned up [X] dead code blocks
- Fixed [X] accessibility issues
- Optimized [X] performance bottlenecks
- Updated [X] outdated dependencies

📈 SCORE ASSESSMENT:
Overall Code Quality: [X/100] - [Grade: Excellent/Good/Needs Work]
Assessment: [Brief summary of codebase health]

🔄 NEXT MAINTENANCE:
Recommended: [Date/timeframe]
Focus Areas: [What to prioritize next time]
```

## CONTEXT.md Logging

Throughout maintenance session, log in CONTEXT.md:

### During Maintenance
```markdown
[YYYY-MM-DD HH:MM:SS] MAINTENANCE SESSION - PHASE 1
Action: File inventory and structure analysis
Files: Scanning src/pages/, src/assets/js/, src/css/, src/utils/
Status: IN PROGRESS

[YYYY-MM-DD HH:MM:SS] MAINTENANCE FINDING
Type: 🔴 CRITICAL
Issue: [Description of issue found]
File: [File path]
Impact: [Effect on system]
Action: [Immediate fix or todo addition]

[YYYY-MM-DD HH:MM:SS] MAINTENANCE FIX APPLIED
Issue: [Description of issue fixed]
Fix: [What was done]
Result: [Outcome of fix]
Test: [How fix was verified]

[YYYY-MM-DD HH:MM:SS] SESSION END - MAINTENANCE
Duration: [X hours/minutes]
Results:
  - Critical Issues: [X] found, [X] fixed ✅
  - High Priority Todos: [X] added
  - Optimizations Identified: [X]
  - Code Quality Score: [X/100] (improved from [Y])
  - Maintenance Page: Updated with assessment
Next Maintenance: [Recommended date/timeframe]
```

## Updating the Maintenance Page

### Step 1: Determine Update Type

**New Assessment Section (Major Maintenance)**
Add new dated section under "Enterprise Architecture & Audit History":
```html
📅 [Date] - [Maintenance Type] Code Review
Version: v0.X.X.X
Assessed: [What was scanned]
Findings: [Summary]
Actions: [What was done]
```

**Update Existing Todos (Routine Maintenance)**
Modify the appropriate priority section:
- 🔴 High Priority
- 🟡 Medium Priority  
- 🟢 Low Priority

### Step 2: Add or Remove Todos

**Adding New Todos:**
```html
🔴 High Priority

    [Todo Title]
    [Description of issue and why it matters]
    Location: [File path]
    Estimated Effort: [Small/Medium/Large]

```

**Marking Todos Complete:**
- Move from todo section to "✅ COMPLETE" in roadmap table
- OR add ✅ checkmark if keeping in history
- Add completion date

## Post-Maintenance Checklist

After completing maintenance session:

- [ ] All critical issues fixed or documented
- [ ] Maintenance page updated with new assessment
- [ ] Todos added/removed appropriately
- [ ] Score updated (if applicable)
- [ ] Roadmap updated (if applicable)
- [ ] Last review date updated
- [ ] Next review date suggested
- [ ] CONTEXT.md fully logged with all findings and fixes
- [ ] All modified files tested
- [ ] Git commit with maintenance summary

### Git Commit Message Format
```
[MAINTENANCE] Code quality review - v0.X.X.X

- Fixed [X] critical issues
- Added [X] high priority todos
- Identified [X] optimization opportunities
- Code quality score: [X/100]

See CONTEXT.md [timestamp] and maintenance.html for details
```

## Quality Standards

### Code Quality Score Criteria

**98-100: 🏆 Enterprise Grade**
- Zero critical issues
- Minimal technical debt
- Excellent documentation
- Optimal performance
- Best practices throughout

**90-97: ✅ Excellent**
- No critical issues
- Minor optimization opportunities
- Good documentation
- Strong performance
- Mostly best practices

**80-89: ⚠️ Good**
- Few critical issues (fixed during maintenance)
- Some technical debt
- Adequate documentation
- Acceptable performance
- Some best practice gaps

**70-79: 🔴 Needs Attention**
- Multiple critical issues
- Significant technical debt
- Poor documentation
- Performance concerns
- Many best practice violations

**Below 70: 🚨 Requires Immediate Action**
- Numerous critical issues
- Heavy technical debt
- Missing documentation
- Poor performance
- Fundamental issues

## Special Maintenance Scenarios

### Pre-Release Maintenance
Before any version release:
1. Full codebase scan (all phases)
2. Fix ALL critical issues
3. Update version number in maintenance page
4. Document release readiness
5. Update roadmap with completed items

### Post-Major-Feature Maintenance
After adding significant features:
1. Focus on new files and dependencies
2. Check integration with existing code
3. Look for duplicate functionality
4. Verify utils are being used properly
5. Update maintenance page with new components

### Emergency Maintenance
If user reports bugs:
1. Scan related files immediately
2. Document bug in maintenance page
3. Fix and test
4. Log in CONTEXT.md
5. Add to maintenance history

## Maintenance Reporting Template

After each maintenance session,

Wiki pages you might want to explore:
- [Continuous Improvement System (cline/prompts)](/wiki/cline/prompts#3)
- [Key Functional Rules (cline/prompts)](/wiki/cline/prompts#4)

### Citations

**File:** clinerules/memory-bank.md (L3-3)
```markdown
I am Cline, an expert software engineer with a unique characteristic: my memory resets completely between sessions. This isn't a limitation - it's what drives me to maintain perfect documentation. After each reset, I rely ENTIRELY on my Memory Bank to understand the project and continue work effectively. I MUST read ALL memory bank files at the start of EVERY task - this is not optional.
```

**File:** clinerules/memory-bank.md (L33-46)
```markdown
3. `activeContext.md`
   - Current work focus
   - Recent changes
   - Next steps
   - Active decisions and considerations
   - Important patterns and preferences
   - Learnings and project insights

4. `systemPatterns.md`
   - System architecture
   - Key technical decisions
   - Design patterns in use
   - Component relationships
   - Critical implementation paths
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

**File:** clinerules/cline-continuous-improvement-protocol.md (L90-93)
```markdown
### 2.4. Proposing `.clinerule` Enhancements (Exceptional):
* The primary focus of this protocol is the maintenance of `raw_reflection_log.md` and `consolidated_learnings.md`.
* If a significant, broadly applicable insight in `consolidated_learnings.md` strongly suggests modifying *another active `.clinerule`* (e.g., core workflow, tech guidance), Cline MAY propose this change after user confirmation. This is exceptional.

```
