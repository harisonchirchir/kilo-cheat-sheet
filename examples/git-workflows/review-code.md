# Code Review Workflow

## Overview

This example demonstrates how to use Kilo Code for automated code review.

## Setup

### Configuration

```json
{
  "workflows": {
    "code-review": {
      "description": "Automated code review",
      "triggers": ["review", "pr"],
      "steps": [
        {
          "name": "analyze",
          "action": "analyzeCode",
          "config": {
            "focus": ["security", "performance", "maintainability"]
          }
        },
        {
          "name": "checkTests",
          "action": "checkTestCoverage",
          "config": {
            "minCoverage": 80
          }
        },
        {
          "name": "generateReport",
          "action": "generateReviewReport"
        }
      ]
    }
  }
}
```

## Usage

### Review Pull Request

```bash
kilo git pr review 123
```

### Review Specific Files

```text
/review src/api.js --focus=security
```

### Review with Custom Rules

```text
/review src/ --rules=backend-best-practices
```

## Review Process

### Automated Analysis

1. **Security Scan**
   - Check for vulnerabilities
   - Validate authentication
   - Review data handling

2. **Code Quality**
   - Analyze complexity
   - Check style compliance
   - Review naming conventions

3. **Performance**
   - Identify bottlenecks
   - Check database queries
   - Review API calls

4. **Testing**
   - Verify test coverage
   - Check test quality
   - Validate test cases

### Manual Review

After automated analysis, review:
- Architecture decisions
- Business logic
- Edge cases
- Documentation

## Review Commands

```bash
# Review specific commit
kilo git review --commit=abc123

# Review branch changes
kilo git review --branch=feature/new-feature

# Review with focus areas
kilo git review --focus=security,performance
```

## Example Review Output

```text
## Code Review Report

### Security Issues
- Found: Potential SQL injection in src/queries.js:42
- Recommendation: Use parameterized queries

### Performance Issues
- Found: N+1 query problem in src/api/users.js
- Recommendation: Use eager loading

### Code Quality
- Cyclomatic complexity too high in src/utils.js (15)
- Recommendation: Extract helper functions

### Test Coverage
- Current: 65%
- Target: 80%
- Missing: Edge cases in validation
```

## Best Practices

- Review small, focused changes
- Provide constructive feedback
- Use automated tools for consistency
- Focus on important issues first
- Don't review style preferences
- Be respectful and specific
