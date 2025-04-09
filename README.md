# GitHub Action Templates for Terragrunt

This repository contains reusable GitHub Actions workflows for managing Terragrunt operations.

## Available Workflows

1. **Terragrunt Plan** (`terragrunt-plan.yml`): Runs `terragrunt plan` to preview infrastructure changes.
2. **Terragrunt Format** (`terragrunt-format.yml`): Runs `terragrunt hclfmt` to format Terragrunt configuration files.
3. **Terragrunt Apply** (`terragrunt-apply.yml`): Runs `terragrunt apply` to apply infrastructure changes.

## Secrets

- `GITHUB_TOKEN`: GitHub token for managing repositories and teams.
- `GCP_SERVICE_ACCOUNT_KEY` (optional): GCP service account key for Terragrunt operations requiring GCP authentication.

## Usage

To use these workflows in your repository, reference them in your GitHub Actions workflow file:

```yaml
jobs:
  terragrunt-plan:
    uses: org-name/github-action-templates/.github/workflows/terragrunt-plan.yml@main
    with:
      working-directory: path/to/your/terragrunt/code
    secrets:
      GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      GCP_SERVICE_ACCOUNT_KEY: ${{ secrets.GCP_SERVICE_ACCOUNT_KEY }}
```

Replace `org-name` with your GitHub organization or username, and adjust the `working-directory` to point to your Terragrunt configuration files.
