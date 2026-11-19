# Git and GitHub

## Overview

Kilo Code provides seamless integration with Git and GitHub to enhance your version control workflow.

## Git Commands

### Status and Diff

```bash
# Check git status with AI insights
kilo git status

# Show diff with AI analysis
kilo git diff

# Show recent commits
kilo git log --oneline -10
```

### Commit Workflow

```bash
# Generate commit message
kilo git commit

# Commit with custom message
kilo git commit -m "Fix authentication bug"

# Commit with AI-generated message
kilo git commit --ai
```

### Branch Management

```bash
# Create new branch
kilo git branch feature/new-feature

# Switch branch
kilo git checkout feature/new-feature

# List branches
kilo git branch -a
```

## GitHub Integration

### Pull Requests

```bash
# Create pull request
kilo git pr create

# Create PR with template
kilo git pr create --template=feature

# Review PR
kilo git pr review 123
```

### Issues

```bash
# Create issue
kilo git issue create "Bug in authentication"

# List issues
kilo git issue list

# Close issue
kilo git issue close 123
```

### Releases

```bash
# Create release
kilo git release create v1.0.0

# Generate changelog
kilo git changelog
```

## AI-Powered Git Workflows

### Smart Commit Messages

```text
/commit
# AI analyzes changes and generates appropriate commit message
```

### Code Review Automation

```text
/review --target=pr
# Reviews pull request changes with AI assistance
```

### Conflict Resolution

```bash
kilo git merge feature-branch
# AI helps resolve conflicts automatically
```

## Git Configuration

### Git Config

```json
{
  "git": {
    "user": {
      "name": "Your Name",
      "email": "your@email.com"
    },
    "defaultBranch": "main",
    "commitTemplate": ".kilo/commit-template.md"
  }
}
```

### Git Hooks

```json
{
  "gitHooks": {
    "pre-commit": "kilo workflow run pre-commit-checks",
    "post-commit": "kilo workflow run post-commit-tasks"
  }
}
```

## GitHub Actions Integration

### Workflow Files

```yaml
# .github/workflows/kilo-code.yml
name: Kilo Code CI
on: [push, pull_request]

jobs:
  ai-review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Kilo Code Review
        run: kilo git pr review ${{ github.event.pull_request.number }}
```

### Automated Workflows

```yaml
name: Automated Testing
on: [push]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run Tests
        run: kilo workflow run test-all
```

## Best Practices

### Commit Messages

- Use imperative mood
- Keep subject line under 50 characters
- Explain what and why, not how
- Reference issues when relevant

### Branch Strategy

- Use descriptive branch names
- Keep branches focused
- Regular merge/rebase
- Delete branches after merge

### Pull Request Process

- Small, focused PRs
- Clear description
- Automated checks
- Required reviews
