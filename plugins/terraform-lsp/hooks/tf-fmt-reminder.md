---
trigger: PreToolUse
match_tools:
  - Bash
---

# Terraform Format Reminder Hook

When the user is about to run a git commit that includes Terraform files (.tf, .tfvars, .tftest.hcl), check if `terraform fmt` should be run first.

## Detection

This hook triggers on Bash tool calls. Look for git commit patterns:
- Commands containing `git commit` (not `git checkout`, `git config`, etc.)
- `git add . && git commit` or `git add -A && git commit` chains

When detected, check if Terraform files are staged:
- Run `git diff --cached --name-only` to list staged files
- Look for files matching `.tf`, `.tfvars`, or `.tftest.hcl` extensions

## Action

If Terraform files are being committed, suggest:

```
Before committing, consider running `terraform fmt -recursive` to ensure consistent formatting.
```

## Note

This is a suggestion only - do not block the commit. Formatting is a code style preference and some teams may have different conventions.
