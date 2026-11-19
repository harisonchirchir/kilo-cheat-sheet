# MCP Servers

## What are MCP Servers?

MCP (Model Context Protocol) servers extend Kilo Code's capabilities by providing additional tools, data sources, and integrations.

## Getting Started

### Install an MCP Server

```bash
# Using npm
kilo mcp add my-server https://github.com/example/mcp-server

# From local path
kilo mcp add local-server ./path/to/mcp-server

# From registry
kilo mcp install filesystem
```

### List Installed Servers

```bash
kilo mcp list
```

### Remove a Server

```bash
kilo mcp remove my-server
```

## Available MCP Servers

### Filesystem Server
Provides file system access and manipulation.

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

### Database Server
Provides database access and query capabilities.

```json
{
  "mcpServers": {
    "database": {
      "command": "node",
      "args": ["mcp-server-db.js"],
      "env": {
        "DATABASE_URL": "postgresql://..."
      }
    }
  }
}
```

### Git Server
Provides Git repository operations.

```json
{
  "mcpServers": {
    "git": {
      "command": "node",
      "args": ["mcp-server-git.js"],
      "env": {
        "REPO_PATH": "/path/to/repo"
      }
    }
  }
}
```

### API Server
Provides API integration capabilities.

```json
{
  "mcpServers": {
    "api": {
      "command": "node",
      "args": ["mcp-server-api.js"],
      "env": {
        "API_BASE_URL": "https://api.example.com"
      }
    }
  }
}
```

### Browser Server
Provides web browsing capabilities.

```json
{
  "mcpServers": {
    "browser": {
      "command": "node",
      "args": ["mcp-server-browser.js"]
    }
  }
}
```

## Creating Custom MCP Servers

### Basic Structure

```javascript
// mcp-server-example.js
import { MCPServer } from '@kilocode/mcp';

const server = new MCPServer({
  name: 'my-server',
  version: '1.0.0'
});

// Register tools
server.tool('greet', {
  description: 'Greet a user',
  parameters: {
    name: {
      type: 'string',
      required: true
    }
  }
}, async ({ name }) => {
  return `Hello, ${name}!`;
});

// Start the server
server.start();
```

### Tool Definition

```javascript
server.tool('createFile', {
  description: 'Create a new file',
  parameters: {
    path: {
      type: 'string',
      required: true,
      description: 'File path'
    },
    content: {
      type: 'string',
      required: true,
      description: 'File content'
    }
  }
}, async ({ path, content }) => {
  // Implementation
  return { success: true, path };
});
```

### Resource Definition

```javascript
server.resource('config', {
  type: 'file',
  path: './config.json'
}, async () => {
  // Read and return file content
  return await fs.readFile('./config.json', 'utf8');
});
```

## Configuration

### MCP Server Configuration

```json
{
  "mcpServers": {
    "my-server": {
      "command": "node",
      "args": ["./mcp-server.js"],
      "env": {
        "DEBUG": "true"
      },
      "autoRestart": true,
      "timeout": 30000
    }
  }
}
```

### Configuration Options

| Option | Description | Default |
|--------|-------------|---------|
| `command` | Command to run the server | required |
| `args` | Arguments for the command | [] |
| `env` | Environment variables | {} |
| `autoRestart` | Auto-restart on failure | true |
| `timeout` | Request timeout in ms | 30000 |
| `enabled` | Enable/disable server | true |

## Security Considerations

### Permissions

MCP servers can access:
- File system (within project directory)
- Network (if configured)
- Environment variables
- System commands

### Best Practices

- Use minimal permissions
- Validate all inputs
- Sanitize outputs
- Use sandboxing when possible
- Regularly update dependencies
- Monitor server activity

### Security Configuration

```json
{
  "mcpServers": {
    "secure-server": {
      "command": "node",
      "args": ["mcp-server.js"],
      "security": {
        "allowFileAccess": false,
        "allowNetworkAccess": false,
        "allowedPaths": ["./data"],
        "allowedDomains": []
      }
    }
  }
}
```

## Troubleshooting

### Common Issues

**Server won't start**
- Check command and arguments
- Verify file permissions
- Check environment variables
- Test command manually

**Connection errors**
- Verify server is running
- Check network connectivity
- Validate configuration
- Check firewall settings

**Performance issues**
- Monitor resource usage
- Adjust timeout settings
- Optimize server code
- Use connection pooling

### Debug Mode

```bash
kilo mcp debug my-server
```

### Logs

```bash
kilo mcp logs my-server
```

### Health Check

```bash
kilo mcp health my-server
```
