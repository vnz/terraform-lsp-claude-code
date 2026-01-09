---
description: Explain Terraform resources, data sources, modules, and HCL syntax with provider-specific context. Use when user asks "what does this resource do", "explain this terraform", or needs help understanding infrastructure code.
---

# Terraform Explanation Skill

When explaining Terraform code:

## 1. Identify the Context

- **Provider**: Determine from resource prefix (aws_, azurerm_, google_, kubernetes_, etc.)
- **Resource Type**: Resource, data source, module, variable, output, or local
- **Purpose**: Infrastructure component being managed

## 2. Use LSP for Documentation

Use the LSP hover operation to retrieve official documentation for the resource or attribute in question. This provides accurate, up-to-date information from the provider.

## 3. Explain with Structure

Provide explanations covering:

1. **Purpose** - What this resource creates/manages in the cloud
2. **Key Attributes** - Important configuration options and their effects
3. **Dependencies** - What this resource typically depends on or provides to others
4. **Security Considerations** - IAM, networking, encryption, and access control implications
5. **Common Patterns** - Typical usage patterns and best practices

## 4. Provider-Specific Guidance

### AWS (aws_*)
- Highlight IAM implications
- Note VPC/networking requirements
- Mention encryption options (KMS, S3 SSE)

### Azure (azurerm_*)
- Note resource group requirements
- Highlight managed identity options
- Mention Azure Policy considerations

### Google Cloud (google_*)
- Note project/organization hierarchy
- Highlight service account requirements
- Mention IAM binding patterns

### Kubernetes (kubernetes_*)
- Note namespace considerations
- Highlight RBAC implications
- Mention resource limits/requests

### Terraform Cloud / Enterprise (tfe_*)
- Note workspace and organization structure
- Highlight remote state and run implications
- Mention Sentinel policies and run triggers
- Consider variable sets and workspace variables

## Example Interaction

User: "What does this aws_security_group resource do?"

Response should cover:
- Purpose: Network firewall rules for EC2/VPC resources
- Ingress/egress rule structure
- Security implications of 0.0.0.0/0 CIDR
- Best practice: least privilege, specific ports only
