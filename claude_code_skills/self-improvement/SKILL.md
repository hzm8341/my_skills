---
name: self-improvement
description: Captures learnings, errors, and corrections to enable continuous improvement. Use when: (1) A command or operation fails unexpectedly, (2) User corrects Claude ('No, that's wrong...', 'Actually...'), (3) User requests a capability that doesn't exist, (4) An external API or tool fails, (5) Claude realizes its knowledge is outdated or incorrect, (6) A better approach is discovered for a recurring task. Also review learnings before major tasks.
---

# Self-Improvement Skill

Log learnings and errors to markdown files for continuous improvement. Use with `/update-skills` command to promote important learnings to global skills.

## When to Use This Skill

- A command or operation fails unexpectedly
- User corrects Claude ('No, that's wrong...', 'Actually...')
- User requests a capability that doesn't exist
- An external API or tool fails
- Claude realizes its knowledge is outdated or incorrect
- A better approach is discovered for a recurring task
- Before major tasks, review existing learnings

## Core Mechanisms

### 1. Learning Directory Structure

Create `.learnings/` directory in project root:
```
.learnings/
├── ERRORS.md          # Command failures, exceptions
├── LEARNINGS.md       # Corrections, knowledge gaps, best practices
└── FEATURE_REQUESTS.md # User-requested capabilities
```

### 2. Recording Errors

When a command/operation fails:

```markdown
## ERR-[DATE]-[INDEX]: Error Title

**Date**: YYYY-MM-DD
**Source**: conversation | error | user_feedback
**Category**: command_failure | external_api | unexpected_behavior

### Context
Describe what was attempted and the environment.

### Error
Actual error message or unexpected behavior.

### Resolution (if any)
How this was resolved or workaround found.

### Related
- See also: ERR-YYYY-MM-DD-XXX (if recurring)
- See also: LRN-YYYY-MM-DD-XXX (if related learning)
```

### 3. Recording Learnings

When user corrects or knowledge gap discovered:

```markdown
## LRN-[DATE]-[INDEX]: Learning Title

**Date**: YYYY-MM-DD
**Source**: conversation | user_feedback
**Category**: correction | knowledge_gap | best_practice | better_approach

### Context
What was the situation where this learning occurred?

### Original Understanding
What did Claude originally think or do?

### Correct Understanding
What is the correct understanding or approach?

### Implications
When should this new knowledge be applied?
```

### 4. Recording Feature Requests

When user requests missing capability:

```markdown
## FEAT-[DATE]-[INDEX]: Feature Request

**Date**: YYYY-MM-DD
**Requested By**: User

### Capability Desired
What the user wanted Claude to do.

### Current Limitation
Why Claude couldn't fulfill this request.

### Potential Solution
Ideas for how this could be addressed.
```

## Quick Reference

| Situation | Action |
|-----------|--------|
| Command/operation fails | Log to `.learnings/ERRORS.md` |
| User corrects you | Log to `.learnings/LEARNINGS.md` with category `correction` |
| User wants missing feature | Log to `.learnings/FEATURE_REQUESTS.md` |
| API/external tool fails | Log to `.learnings/ERRORS.md` with integration details |
| Knowledge was outdated | Log to `.learnings/LEARNINGS.md` with category `knowledge_gap` |
| Found better approach | Log to `.learnings/LEARNINGS.md` with category `better_approach` |
| Promote to global skill | Use `/update-skills` command |

## OpenCode-Specific Implementation

### Writing to Files

Use `write` tool to create/update learning files:

```bash
# Create .learnings directory
mkdir -p .learnings

# Write entry (use write tool with append mode)
```

### Integration with /update-skills

After recording important learnings:

1. Use `/update-skills` command to review session
2. Select learnings that should be promoted to global skills
3. Claude will update the relevant skill in `/media/hzm/data_disk/claude_global/skills/`

### Session Tools

OpenCode provides built-in session management:

- `session_list` - List all sessions
- `session_read` - Read another session's history
- `session_search` - Search across sessions
- Use these to find relevant past learnings

## Best Practices

1. **Be Specific**: Include exact error messages, commands, and context
2. **Add Index Numbers**: Use LRN-YYYY-MM-DD-XXX format for traceability
3. **Cross-Reference**: Link related errors and learnings
4. **Review Before Major Tasks**: Check `.learnings/` when working in unfamiliar areas
5. **Promote Important Learnings**: Use `/update-skills` to add recurring patterns to global skills

## Common Patterns

### Error Pattern
```
## ERR-20260305-001: npm install failed

**Date**: 2026-03-05
**Category**: command_failure

### Context
Running `npm install` in project /foo/bar

### Error
ENOENT: no such file or directory, open 'package.json'

### Resolution
User explained package.json was missing - needed to run npm init first
```

### Correction Pattern
```
## LRN-20260305-001: Python requirements.txt location

**Date**: 2026-03-05
**Category**: correction

### Context
User asked about Python dependencies

### Original Understanding
Assumed requirements.txt in project root

### Correct Understanding
This project uses pyproject.toml instead (modern Python projects)
```

### Best Practice Pattern
```
## LRN-20260305-002: Efficient file searching

**Date**: 2026-03-05
**Category**: better_approach

### Context
Searching for function definitions across large codebase

### Original Approach
Used read tool on multiple files sequentially

### Better Approach
Use lsp_symbols or ast_grep_search for code pattern matching - much faster
```
