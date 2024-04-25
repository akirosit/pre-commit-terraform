# [pre-commit](https://pre-commit.com/) hooks for [Terraform](https://www.terraform.io/)

This repository contains some simple but out-of-the-box hooks for pre-commit when dealing with terraform configurations.

## Using the repository with pre-commit

Add this to your `.pre-commit-config.yaml`

```yaml
-   repo: https://github.com/akirosit/pre-commit-terraform
    rev: latest # Use the ref you want to point at
    hooks:
    - id: terraform_fmt
    - id: ...
```

## Available hooks

|  Hook  |  Description  |  Dependencies  |
|----------|----------|----------|
| [`terraform_fmt`](#terraform_fmt) | Reformat your configuration in the standard style by rewriting all Terraform configuration files to a canonical format. | `terraform` |

## Hooks usage

### `terraform_fmt`

This hook run the `terraform fmt` command on matching files.
By default this hook runs on every "terraform" (`.tf`, `.tfvars`) or "hcl" (`.hcl`) files that are under revision.
You can pass all `terraform fmt` supported options to the hook using the `args` option.

Here is an example that runs the hook with specific options, excluding the `.terraform` directory:

```yaml
    - id: terraform_fmt
      args:
        - -check
        - -diff
      exclude: \.terraform/

```
