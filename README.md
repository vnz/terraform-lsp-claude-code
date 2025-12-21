# Terraform LSP for Claude Code

[![Claude Code](https://img.shields.io/badge/Claude%20Code-Plugin-blueviolet)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Claude Code plugin that adds **Terraform language server** support for infrastructure as code development.

## Features

- **Go to Definition** - Navigate to resource, variable, and module definitions
- **Find References** - Find all usages across your Terraform codebase
- **Hover Documentation** - View inline documentation for resources and attributes
- **Real-time Diagnostics** - Validation and error checking as you work

## Prerequisites

Install [terraform-ls](https://github.com/hashicorp/terraform-ls) (HashiCorp's official Terraform Language Server):

```bash
# Using Go
go install github.com/hashicorp/terraform-ls@latest

# macOS with Homebrew
brew install hashicorp/tap/terraform-ls

# Verify installation
which terraform-ls
```

## Installation

### 1. Add the marketplace

```
/plugin marketplace add vnz/terraform-lsp-claude-code
```

### 2. Install the plugin

```
/plugin install terraform-lsp@terraform-lsp-claude-code
```

### 3. Enable LSP (if not already enabled)

Add to your `~/.claude/settings.json`:

```json
{
  "env": {
    "ENABLE_LSP_TOOL": "1"
  }
}
```

## Usage

Once installed, Claude Code will automatically use the Terraform LSP for `.tf` and `.tfvars` files.

Ask Claude to use LSP features:

```
"use LSP to find all references to the aws_instance resource"
"go-to-definition for the vpc_id variable"
"what are the hover docs for this resource?"
```

## Supported File Types

| Extension | Language |
|-----------|----------|
| `.tf` | Terraform |
| `.tfvars` | Terraform Variables |

## Troubleshooting

### Plugin not showing up?

1. Make sure `ENABLE_LSP_TOOL=1` is set in your settings
2. Restart Claude Code after installing
3. Check `/plugin` to verify it's enabled

### LSP not working?

1. Verify `terraform-ls` is installed: `which terraform-ls`
2. Check it's in your PATH
3. Try running `terraform-ls serve` manually to test

## License

MIT License - see [LICENSE](LICENSE) for details.

## Contributing

Issues and PRs welcome at [github.com/vnz/terraform-lsp-claude-code](https://github.com/vnz/terraform-lsp-claude-code)

## See Also

- [terraform-ls](https://github.com/hashicorp/terraform-ls) - HashiCorp's official Terraform Language Server
- [Claude Code Plugins](https://docs.anthropic.com/en/docs/claude-code/plugins) - Official plugin documentation
