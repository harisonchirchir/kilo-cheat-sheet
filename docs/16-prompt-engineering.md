# Prompt Engineering

## Overview

Effective prompts are key to getting the most out of Kilo Code. This guide covers techniques for crafting better prompts.

## Basic Prompt Structure

### Components

1. **Context** - What the code does
2. **Task** - What you want to achieve
3. **Requirements** - Specific constraints
4. **Format** - How the output should look

### Example

```text
Context: I have a React component for user registration
Task: Add form validation
Requirements: Validate email format, password strength, and required fields
Format: Return the updated component code with validation logic
```

## Prompt Techniques

### Specificity

```text
Good: "Create a TypeScript function that calculates the Fibonacci sequence iteratively"
Bad: "Create a Fibonacci function"
```

### Examples

```text
"Create a function like this:
function double(x) { return x * 2; }
Now create a similar function for tripling numbers"
```

### Step-by-Step

```text
"First, define the interface. Then, implement the logic. Finally, add error handling"
```

## Advanced Techniques

### Chain of Thought

```text
"Let's think step by step:
1. What data do we need?
2. How should we process it?
3. What should the output look like?
Now implement based on these steps"
```

### Role Playing

```text
"Act as a senior backend developer. Review this code from the perspective of scalability and security"
```

### Constraints

```text
"Implement this feature using only functional programming concepts, no classes"
```

## Domain-Specific Prompts

### Frontend

```text
"Create a responsive navigation component that works on mobile and desktop"
```

### Backend

```text
"Design a REST API endpoint for user authentication with JWT tokens"
```

### Database

```text
"Optimize this SQL query for better performance on large datasets"
```

### Testing

```text
"Generate comprehensive unit tests for this function including edge cases"
```

## Prompt Patterns

### Debugging

```text
"This code is producing X error. Analyze the stack trace and identify the root cause"
```

### Refactoring

```text
"Refactor this code to use the repository pattern while maintaining the same interface"
```

### Documentation

```text
"Generate JSDoc comments for this function explaining parameters, returns, and throws"
```

### Optimization

```text
"Optimize this algorithm for better time complexity. Current complexity is O(n²)"
```

## Common Mistakes

### Too Vague

```text
Bad: "Improve this code"
Good: "Refactor this function to reduce cyclomatic complexity from 15 to below 5"
```

### Missing Context

```text
Bad: "Fix the bug"
Good: "Fix the authentication bug where users can bypass login with empty credentials"
```

### Unclear Requirements

```text
Bad: "Make it faster"
Good: "Reduce the API response time from 2 seconds to under 500 milliseconds"
```

## Prompt Optimization Checklist

- [ ] Is the context clear?
- [ ] Is the specific task defined?
- [ ] Are requirements specified?
- [ ] Is the desired format mentioned?
- [ ] Are there any constraints?
- [ ] Are examples provided if needed?
- [ ] Is the prompt focused on one task?

## Best Practices

### Be Specific

- Use technical terms correctly
- Specify file names and locations
- Mention specific technologies
- Include version numbers when relevant

### Provide Context

- Explain the project structure
- Mention existing patterns
- Describe user requirements
- Include business logic

### Iterate

- Start with basic prompts
- Refine based on results
- Build on successful outputs
- Learn from failures

### Test Different Approaches

- Try different phrasings
- Experiment with detail levels
- Use various prompting techniques
- Combine multiple approaches
