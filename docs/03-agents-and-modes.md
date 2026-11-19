# Agents and Modes

## Understanding Agents

Agents are specialized AI instances configured for specific tasks or roles. Each agent has unique capabilities, knowledge bases, and behaviors.

## Available Agents

### Code  Agent
- **Purpose**: General-purpose code generation and editing
- **Best for**: Feature development, bug fixes, refactoring
- **Capabilities**: Write, edit, debug, optimize code

### Review Agent
- **Purpose**: Code review and quality assessment
- **Best for**: Pull requests, code reviews, quality checks
- **Capabilities**: Identify issues, suggest improvements, check standards

### Test Agent
- **Purpose**: Test generation and validation
- **Best for**: Creating unit tests, integration tests, test plans
- **Capabilities**: Generate test cases, validate coverage, identify edge cases

### Debug Agent
- **Purpose**: Bug identification and resolution
- **Best for**: Debugging sessions, error analysis, performance issues
- **Capabilities**: Stack trace analysis, root cause identification, fix suggestions

### Docs Agent
- **Purpose**: Documentation generation
- **Best for**: API docs, README files, code comments
- **Capabilities**: Generate documentation from code, explain functionality

### Architect Agent
- **Purpose**: System design and architecture
- **Best for**: System design, technology selection, scalability planning
- **Capabilities**: Design patterns, architecture diagrams, technology recommendations

## Modes

Modes define how agents interact with your project and respond to your requests.

### Interactive Mode
- Real-time conversation with the AI
- Step-by-step problem solving
- Immediate feedback and clarification

### Batch Mode
- Process multiple requests at once
- Automated workflows
- Scheduled operations

### Autonomous Mode
- AI makes decisions independently
- Minimal human intervention
- Best for well-defined tasks

## Switching Between Agents

### CLI
```bash
# Use specific agent
kilo agent use code

# List available agents
kilo agent list

# Show agent info
kilo agent info review
```

### VS Code Extension
- Click the agent selector in the status bar
- Choose from available agents
- Switch anytime

## Custom Agents

Create your own agents:

```json
{
  "name": "backend-specialist",
  "description": "Specialized in backend development",
  "systemPrompt": "You are a backend development expert...",
  "capabilities": ["api-design", "database", "performance"],
  "model": "gpt-4"
}
```

## Agent Configuration

See [Configuration](docs/07-configuration.md) for detailed agent setup.
See [Custom Agents](docs/10-custom-agents-and-skills.md) for creating custom agents.
