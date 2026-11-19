# CLI Commands

## General Commands

### `kilo --version`
Display the installed version.

```bash
kilo --version
# Output: 1.0.0
```

### `kilo --help`
Show help information.

```bash
kilo --help
```

### `kilo health check`
Check system health and connectivity.

```bash
kilo health check
```

## Authentication Commands

### `kilo auth login`
Authenticate with your AI provider.

```bash
kilo auth login
```

### `kilo auth logout`
Log out from the current account.

```bash
kilo auth logout
```

### `kilo auth status`
Check authentication status.

```bash
kilo auth status
```

## Project Commands

### `kilo init`
Initialize a new Kilo Code project.

```bash
kilo init
```

### `kilo status`
Show project status.

```bash
kilo status
```

### `kilo config`
Manage configuration.

```bash
# Show current config
kilo config show

# Set config value
kilo config set model gpt-4

# Edit config file
kilo config edit
```

## Agent Commands

### `kilo agent list`
List available agents.

```bash
kilo agent list
```

### `kilo agent use`
Switch to a specific agent.

```bash
kilo agent use code
```

### `kilo agent info`
Show agent information.

```bash
kilo agent info review
```

### `kilo agent create`
Create a custom agent.

```bash
kilo agent create my-agent
```

## Code Commands

### `kilo generate`
Generate code from a prompt.

```bash
kilo generate "Create a function to calculate fibonacci numbers"
```

### `kilo explain`
Explain code.

```bash
kilo explain src/utils.py
```

### `kilo refactor`
Refactor code.

```bash
kilo refactor src/main.js --target=es6
```

### `kilo test`
Generate tests.

```bash
kilo test src/utils.js
```

### `kilo debug`
Debug code.

```bash
kilo debug --file=app.js --line=42
```

## MCP Commands

### `kilo mcp list`
List MCP servers.

```bash
kilo mcp list
```

### `kilo mcp add`
Add an MCP server.

```bash
kilo mcp add my-server http://localhost:3000
```

### `kilo mcp remove`
Remove an MCP server.

```bash
kilo mcp remove my-server
```

## Git Commands

### `kilo git status`
Show git status with AI insights.

```bash
kilo git status
```

### `kilo git commit`
Generate commit message.

```bash
kilo git commit
```

### `kilo git review`
Review changes.

```bash
kilo git review
```

### `kilo git pr`
Create pull request.

```bash
kilo git pr create
```

## Workflow Commands

### `kilo workflow list`
List available workflows.

```bash
kilo workflow list
```

### `kilo workflow run`
Run a workflow.

```bash
kilo workflow run deploy
```

### `kilo workflow create`
Create a custom workflow.

```bash
kilo workflow create my-workflow
```

## Output Options

### `--output, -o`
Specify output format.

```bash
kilo generate "Hello world" --output=json
```

### `--file, -f`
Output to file.

```bash
kilo generate "API endpoint" --file=api.js
```

### `--verbose, -v`
Show detailed output.

```bash
kilo generate "Complex task" --verbose
```

### `--dry-run`
Preview without executing.

```bash
kilo refactor file.js --dry-run
```
