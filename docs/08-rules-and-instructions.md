# Rules and Instructions

## Overview

Rules and instructions guide Kilo Code's behavior and ensure consistent output across your project.

## Types of Rules

### Project Rules
Apply to all operations within a project.

```json
{
  "rules": [
    "Use TypeScript for all new files",
    "Follow the existing code style",
    "Write tests for all new features",
    "Use camelCase for variable names",
    "Maximum line length: 100 characters"
  ]
}
```

### File-Specific Rules
Apply to specific files or file patterns.

```json
{
  "fileRules": {
    "src/**/*.ts": "Use strict typing",
    "tests/**/*.test.ts": "Use descriptive test names",
    "docs/*.md": "Use American English spelling"
  }
}
```

### Agent-Specific Rules
Apply to specific agents.

```json
{
  "agentRules": {
    "review": "Focus on code quality and best practices",
    "test": "Ensure comprehensive test coverage",
    "docs": "Write clear and concise documentation"
  }
}
```

## Instruction Categories

### Code Style Instructions

```json
{
  "instructions": {
    "codeStyle": {
      "indentation": "2 spaces",
      "quotes": "single",
      "semicolons": true,
      "lineEnding": "lf"
    }
  }
}
```

### Naming Conventions

```json
{
  "instructions": {
    "naming": {
      "variables": "camelCase",
      "functions": "camelCase",
      "classes": "PascalCase",
      "constants": "UPPER_SNAKE_CASE",
      "files": "kebab-case"
    }
  }
}
```

### Documentation Standards

```json
{
  "instructions": {
    "documentation": {
      "functionComments": "JSDoc",
      "fileHeader": "Include author and date",
      "readmeFormat": "Standard Markdown"
    }
  }
}
```

## Creating Rules

### Syntax

Rules are written in natural language with optional modifiers:

```
[Priority] [Context] Action
```

### Examples

```
High: Use TypeScript for all new files
Medium: Follow existing code style in src/
Low: Add comments for complex algorithms
```

### Priority Levels

- `High` - Must follow
- `Medium` - Should follow
- `Low` - Nice to have

## Best Practices

### Be Specific

```text
Good: Use async/await for asynchronous operations
Bad: Handle async correctly
```

### Provide Context

```text
Good: In the auth module, use JWT tokens for authentication
Bad: Use JWT for auth
```

### Include Examples

```text
Good: Use descriptive variable names like `userEmail` instead of `x`
Bad: Use good variable names
```

### Keep It Maintainable

- Avoid overly complex rules
- Regularly review and update
- Remove obsolete rules
- Group related rules together

## Rule Templates

### Frontend Rules

```json
{
  "rules": [
    "Use functional components",
    "Use hooks for state management",
    "Implement proper error boundaries",
    "Optimize renders with React.memo"
  ]
}
```

### Backend Rules

```json
{
  "rules": [
    "Use async/await for database operations",
    "Validate all input data",
    "Use parameterized queries",
    "Implement proper error handling"
  ]
}
```

### Testing Rules

```json
{
  "rules": [
    "Test all public functions",
    "Include edge cases in tests",
    "Use descriptive test names",
    "Mock external dependencies"
  ]
}
```

## Managing Rules

### Add Rules

```bash
kilo rules add "Use TypeScript for all new files"
```

### Remove Rules

```bash
kilo rules remove "Old rule text"
```

### List Rules

```bash
kilo rules list
```

### Edit Rules

```bash
kilo rules edit
```

### Import/Export

```bash
kilo rules export > rules.json
kilo rules import < rules.json
```

## Validation

Rules are validated on each operation. Invalid rules are:
- Too vague or ambiguous
- Contradictory with other rules
- Technically impossible to follow
- Outdated for current project state

Use `kilo rules validate` to check your rules.
