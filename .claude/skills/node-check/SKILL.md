# Node Version Check

## Instructions

### Step 1: Check Node.js Version
Run `node --version` to determine the current Node.js version.

### Step 2: Evaluate Version
- If version >= 18.0.0: Node.js is compatible. Proceed with operations.
- If version < 18.0.0:
  - Inform user: "Node.js version is {current}, which is too old. Recommended: 18+"
  - Offer to upgrade: run `nvm install 18 && nvm use 18`
  - After upgrade, verify with `node --version` again

### Step 3: Verify npm
- Run `npm --version` to confirm npm is available
- Report status summary

## When to Use
Before any npm install, Node.js tool setup, or plugin installation.
