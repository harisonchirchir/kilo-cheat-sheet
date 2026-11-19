# Prepare Pull Request Workflow

## Overview

This example demonstrates how to use Kilo Code to prepare a pull request.

## Setup

### Configuration

```json
{
  "workflows": {
    "prepare-pr": {
      "description": "Prepare pull request",
      "triggers": ["pr", "pull-request"],
      "steps": [
        {
          "name": "updateBranch",
          "action": "gitPull",
          "config": {
            "branch": "main"
          }
        },
        {
          "name": "runTests",
          "action": "runTests",
          "config": {
            "coverage": true
          }
        },
        {
          "name": "generateChangelog",
          "action": "generateChangelog"
        },
        {
          "name": "createPR",
          "action": "createPullRequest",
          "config": {
            "template": ".github/PULL_REQUEST_TEMPLATE.md"
          }
        }
      ]
    }
  }
}
```

## Usage

### Prepare PR from CLI

```bash
kilo git pr create
```

### Prepare PR with Custom Template

```bash
kilo git pr create --template=feature
```

### Update and Prepare

```bash
kilo git pr update 123
```

## PR Preparation Process

### Step 1: Update Branch

```bash
git pull origin main
```

### Step 2: Run Tests

```bash
kilo workflow run test-all
```

### Step 3: Generate Changelog

```text
/changelog --since=last-release
```

### Step 4: Create PR

```text
/pr --title="Add user authentication" --body="Implements JWT-based authentication"
```

## PR Template

### Feature Template

```markdown
## Summary
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Comments added where needed
- [ ] Documentation updated
- [ ] No sensitive data exposed
```

## Example PR Creation

```text
User: /pr --type=feature

Kilo: I'll help you create a pull request. Let me analyze your changes...

User: What should the title be?

Kilo: Based on your changes, I suggest:
"Implement user authentication with JWT tokens"

User: /pr --title="Implement user authentication with JWT tokens"

Kilo: I've created the pull request with:
- Title: Implement user authentication with JWT tokens
- Description: Includes changes to auth module, new middleware, and tests
- Checklist items completed
- Linked issues: #123, #456
```

## Best Practices

- Keep PRs small and focused
- Write clear titles and descriptions
- Include screenshots for UI changes
- Link related issues
- Request specific reviewers
- Use templates for consistency
- Update PR description as changes evolve
