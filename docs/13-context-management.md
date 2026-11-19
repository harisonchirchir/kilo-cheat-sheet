# Context Management

## Overview

Context management controls how Kilo Code understands and uses information from your project. Proper context management is crucial for effective AI assistance.

## Context Sources

### File System Context

```json
{
  "context": {
    "files": {
      "enabled": true,
      "maxFiles": 20,
      "includePatterns": ["src/**/*.ts", "tests/**/*.test.ts"],
      "excludePatterns": ["node_modules/**", "dist/**"]
    }
  }
}
```

### Git Context

```json
{
  "context": {
    "git": {
      "enabled": true,
      "includeBranch": true,
      "includeStatus": true,
      "includeRecentCommits": 10
    }
  }
}
```

### Project Context

```json
{
  "context": {
    "project": {
      "enabled": true,
      "includePackageJson": true,
      "includeReadme": true,
      "includeConfigFiles": true
    }
  }
}
```

## Context Window Management

### Window Size

```json
{
  "context": {
    "window": {
      "maxSize": 8000,
      "strategy": "smart", // smart, recent, important
      "reserveForResponse": 1000
    }
  }
}
```

### Prioritization

```json
{
  "context": {
    "priority": {
      "currentFile": 10,
      "relatedFiles": 8,
      "recentFiles": 6,
      "projectFiles": 4,
      "history": 2
    }
  }
}
```

## Context Optimization

### Smart Context

Kilo Code automatically:
- Prioritizes relevant files
- Truncates large files
- Compresses repetitive content
- Caches frequently accessed data

### Manual Context Control

```json
{
  "context": {
    "manual": {
      "include": ["./src/main.ts", "./README.md"],
      "exclude": ["./node_modules/**"],
      "maxFileSize": 100000 // bytes
    }
  }
}
```

## Conversation History

### History Management

```json
{
  "history": {
    "enabled": true,
    "maxMessages": 10,
    "strategy": "sliding", // sliding, summary, none
    "summarizeAfter": 20
  }
}
```

### History Strategies

- **sliding** - Keep recent messages
- **summary** - Summarize older messages
- **none** - No history

## Performance Optimization

### Caching

```json
{
  "cache": {
    "enabled": true,
    "ttl": 3600000, // 1 hour
    "maxSize": 100 // MB
  }
}
```

### Indexing

```json
{
  "index": {
    "enabled": true,
    "indexCode": true,
    "indexDocs": true,
    "updateInterval": 300000 // 5 minutes
  }
}
```

## Context Analysis

### Context Usage

```bash
kilo context show
kilo context stats
kilo context analyze
```

### Context Export

```bash
kilo context export > context.json
```

## Best Practices

### For Large Projects

- Use exclude patterns
- Limit context window
- Use manual includes for critical files
- Regularly clean up old context

### For Small Projects

- Include more files in context
- Use larger context window
- Enable comprehensive indexing

### For Specific Tasks

- **Debugging**: Include error logs and stack traces
- **Feature Development**: Include related modules and tests
- **Refactoring**: Include entire affected area
- **Documentation**: Include code and existing docs
