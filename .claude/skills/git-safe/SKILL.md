# Git Safe Push

## Instructions

### Step 1: Check Status
Run `git status` to check for uncommitted changes.

### Step 2: Commit if Needed
If there are uncommitted changes:
1. Run `git add -A`
2. Create commit with message provided by user or auto-generated meaningful message

### Step 3: Push
Run `git push` to push commits to remote.

### Step 4: Verify Success
- If push succeeds: Report "Push successful"
- If push fails with timeout:
  1. Wait briefly and retry once
  2. If retry fails, report failure with error details
- If push fails with other error, report and suggest solutions

## When to Use
Whenever user requests git push or commit operations. Ensures verification before reporting completion.
