# Configuration

## Configuration File

Kilo Code uses a `kilo.json` file for configuration. This file is typically located in your project root.

## Basic Configuration

```json
{
  "project": "my-app",
  "aiProvider": "openai",
  "model": "gpt-4",
  "temperature": 0.7,
  "maxTokens": 2000,
  "streaming": true,
  "contextWindow": 8000
}
```

## Configuration Options

### AI Provider Settings

| Option | Description | Default |
|--------|-------------|---------|
| `aiProvider` | AI provider (openai, anthropic, etc.) | openai |
| `model` | Model to use | gpt-4 |
| `temperature` | Sampling temperature (0-2) | 0.7 |
| `maxTokens` | Maximum tokens in response | 2000 |
| `topP` | Nucleus sampling parameter | 1.0 |
| `frequencyPenalty` | Frequency penalty | 0.0 |
| `presencePenalty` | Presence penalty | 0.0 |

### Context Settings

| Option | Description | Default |
|--------|-------------|---------|
| `contextWindow` | Context window size | 8000 |
| `maxContextFiles` | Max files in context | 20 |
| `includeHistory` | Include conversation history | true |
| `historyLimit` | Number of messages to include | 10 |

### Agent Settings

| Option | Description | Default |
|--------|-------------|---------|
| `defaultAgent` | Default agent to use | code |
| `agents` | Custom agent configurations | {} |
| `autoSwitch` | Auto-switch agents based on task | false |

### Behavior Settings

| Option | Description | Default |
|--------|-------------|---------|
| `autoSave` | Auto-save sessions | true |
| `confirmActions` | Confirm before destructive actions | true |
| `streaming` | Stream responses in real-time | true |
| `verbose` | Show detailed output | false |

### Security Settings

| Option | Description | Default |
|--------|-------------|---------|
| `allowFileAccess` | Allow file system access | true |
| `allowNetworkAccess` | Allow network requests | false |
| `allowedDomains` | Domains allowed for network access | [] |
| `sandboxMode` | Run in sandboxed environment | false |

## Environment Variables

You can also configure Kilo Code using environment variables:

```bash
# .env file
KILO_AI_PROVIDER=openai
KILO_MODEL=gpt-4
KILO_TEMPERATURE=0.7
KILO_MAX_TOKENS=2000
KILO_CONTEXT_WINDOW=8000
```

## Multiple Configurations

You can have different configurations for different environments:

```json
{
  "dev": {
    "model": "gpt-3.5-turbo",
    "temperature": 0.5
  },
  "prod": {
    "model": "gpt-4",
    "temperature": 0.7
  }
}
```

Use with: `kilo config use dev`

## Advanced Configuration

### Custom Agents

```json
{
  "agents": {
    "backend-specialist": {
      "description": "Backend development expert",
      "systemPrompt": "You are a backend development expert...",
      "capabilities": ["api-design", "database", "performance"],
      "model": "gpt-4",
      "temperature": 0.3
    }
  }
}
```

### MCP Servers

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "node",
      "args": ["mcp-server-fs.js"],
      "env": {
        "ROOT_DIR": "/path/to/project"
      }
    }
  }
}
```

### Rules and Instructions

```json
{
  "rules": [
    "Use TypeScript for all new files",
    "Follow the existing code style",
    "Write tests for all new features"
  ],
  "instructions": {
    "codeStyle": "Use 2 spaces for indentation",
    "namingConvention": "camelCase for variables",
    "commentStyle": "Use JSDoc for functions"
  }
}
```

## Configuration Management

### Show Current Configuration

```bash
kilo config show
```

### Set Configuration Value

```bash
kilo config set temperature 0.5
```

### Edit Configuration File

```bash
kilo config edit
```

### Reset to Defaults

```bash
kilo config reset
```

### Export Configuration

```bash
kilo config export > config.json
```

### Import Configuration

```bash
kilo config import < config.json
```

## Validation

Kilo Code validates your configuration on startup. Common issues:

- Invalid JSON syntax
- Unknown configuration options
- Invalid values (e.g., temperature > 2)
- Missing required fields

Use `kilo config validate` to check your configuration.
