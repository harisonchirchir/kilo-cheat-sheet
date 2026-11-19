# Custom Agents and Skills

## Overview

Create custom agents and skills to extend Kilo Code's capabilities for your specific needs.

## Custom Agents

### Creating an Agent

```bash
kilo agent create my-agent
```

This creates a configuration file for your custom agent.

### Agent Configuration

```json
{
  "name": "backend-specialist",
  "description": "Specialized in backend development",
  "systemPrompt": "You are a backend development expert with 10+ years of experience. You specialize in API design, database optimization, and scalable architecture.",
  "capabilities": [
    "api-design",
    "database-optimization",
    "performance-tuning",
    "security-review"
  ],
  "model": "gpt-4",
  "temperature": 0.3,
  "maxTokens": 2000
}
```

### Agent Properties

| Property | Description | Required |
|----------|-------------|----------|
| `name` | Unique agent name | Yes |
| `description` | Agent description | Yes |
| `systemPrompt` | System prompt for the AI | Yes |
| `capabilities` | List of capabilities | No |
| `model` | AI model to use | No |
| `temperature` | Sampling temperature | No |
| `maxTokens` | Maximum tokens | No |

### Agent Examples

#### Frontend Specialist

```json
{
  "name": "frontend-specialist",
  "description": "Frontend development expert",
  "systemPrompt": "You are a frontend development expert specializing in React, Vue, and modern CSS frameworks.",
  "capabilities": ["react", "vue", "css", "performance"],
  "model": "gpt-4",
  "temperature": 0.4
}
```

#### Data Scientist

```json
{
  "name": "data-scientist",
  "description": "Data science and ML expert",
  "systemPrompt": "You are a data science expert with experience in Python, pandas, scikit-learn, and deep learning.",
  "capabilities": ["python", "pandas", "scikit-learn", "tensorflow"],
  "model": "gpt-4",
  "temperature": 0.3
}
```

## Skills

### Understanding Skills

Skills are reusable capabilities that agents can use. They are modular and can be combined.

### Creating a Skill

```bash
kilo skill create my-skill
```

### Skill Configuration

```json
{
  "name": "code-review",
  "description": "Code review skill",
  "version": "1.0.0",
  "triggers": [
    "review",
    "check",
    "audit"
  ],
  "actions": [
    {
      "name": "analyze",
      "description": "Analyze code for issues",
      "parameters": {
        "code": "string",
        "language": "string"
      }
    }
  ]
}
```

### Built-in Skills

#### Code Analysis
- Analyze code complexity
- Check for bugs
- Suggest improvements

#### Testing
- Generate test cases
- Check coverage
- Validate test quality

#### Documentation
- Generate API docs
- Create README files
- Add code comments

#### Refactoring
- Improve code structure
- Apply design patterns
- Optimize performance

### Custom Skill Examples

#### API Generator

```json
{
  "name": "api-generator",
  "description": "Generate REST API endpoints",
  "triggers": ["api", "endpoint", "route"],
  "actions": [
    {
      "name": "generate",
      "description": "Generate API endpoint",
      "parameters": {
        "method": "string",
        "path": "string",
        "model": "string"
      }
    }
  ]
}
```

#### Database Migrator

```json
{
  "name": "db-migrator",
  "description": "Database migration helper",
  "triggers": ["migration", "db", "database"],
  "actions": [
    {
      "name": "create",
      "description": "Create migration file",
      "parameters": {
        "name": "string",
        "changes": "object"
      }
    }
  ]
}
```

## Combining Agents and Skills

### Agent with Skills

```json
{
  "name": "fullstack-developer",
  "description": "Full-stack development expert",
  "systemPrompt": "You are a full-stack developer with expertise in both frontend and backend technologies.",
  "capabilities": ["react", "nodejs", "database", "api"],
  "skills": ["code-review", "testing", "documentation"],
  "model": "gpt-4",
  "temperature": 0.4
}
```

### Skill Dependencies

```json
{
  "name": "deploy",
  "description": "Deployment automation",
  "dependencies": ["docker", "kubernetes", "ci-cd"],
  "actions": [
    {
      "name": "dockerize",
      "description": "Create Docker image",
      "parameters": {
        "app": "string",
        "port": "number"
      }
    }
  ]
}
```

## Testing Custom Agents and Skills

### Test Agent

```bash
kilo agent test my-agent
```

### Test Skill

```bash
kilo skill test my-skill
```

### Validate Configuration

```bash
kilo agent validate
kilo skill validate
```

## Publishing Agents and Skills

### Share with Team

```bash
kilo agent share my-agent --team=my-team
kilo skill share my-skill --team=my-team
```

### Export/Import

```bash
# Export
kilo agent export my-agent > agent.json
kilo skill export my-skill > skill.json

# Import
kilo agent import < agent.json
kilo skill import < skill.json
```

### Public Registry

```bash
# Publish to registry
kilo agent publish my-agent
kilo skill publish my-skill

# Install from registry
kilo agent install community-agent
kilo skill install community-skill
```

## Best Practices

### Agent Design

- Keep system prompts focused
- Define clear capabilities
- Use appropriate temperature values
- Test with various inputs

### Skill Design

- Make skills reusable
- Keep actions atomic
- Document parameters clearly
- Handle errors gracefully

### Maintenance

- Regularly update agents and skills
- Monitor performance
- Gather user feedback
- Deprecate unused features
