# terraform-lsp

Terraform language server for Claude Code, providing code intelligence for infrastructure as code.

## Features

- **Go to Definition** - Jump to resource, variable, and module definitions
- **Find References** - Find all usages of resources and variables
- **Hover Documentation** - See resource documentation inline
- **Code Diagnostics** - Real-time validation and error checking

## Supported Extensions

- `.tf` - Terraform configuration files
- `.tfvars` - Terraform variable files

## Prerequisites

Install terraform-ls (HashiCorp's official Terraform Language Server):

```bash
# Using Go
go install github.com/hashicorp/terraform-ls@latest

# Or on macOS with Homebrew
brew install hashicorp/tap/terraform-ls
```

Make sure `terraform-ls` is in your PATH:
```bash
which terraform-ls
```

## More Information

- [terraform-ls Documentation](https://github.com/hashicorp/terraform-ls)
- [HashiCorp Terraform](https://www.terraform.io/)
- [Terraform Language Server Usage](https://github.com/hashicorp/terraform-ls/blob/main/docs/USAGE.md)
