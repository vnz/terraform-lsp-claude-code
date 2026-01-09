---
trigger: PreToolUse
match_tools:
  - Bash
---

# Terraform Format Reminder Hook

When the user is about to run a git commit that includes Terraform files (.tf, .tfvars, .tftest.hcl), check if `terraform fmt` should be run first.

## Detection

Look for git commit commands that may include Terraform files:
- `git commit` (check staged files for .tf/.tfvars/.tftest.hcl)
- `git add . && git commit` patterns

## Action

If Terraform files are being committed, suggest:

```
Before committing, consider running `terraform fmt -recursive` to ensure consistent formatting.
```

## Note

This is a suggestion only - do not block the commit. Formatting is a code style preference and some teams may have different conventions.
