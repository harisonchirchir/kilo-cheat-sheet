# Quick Reference

## Essential Commands

### CLI Basics
```bash
kilo --version          # Check version
kilo --help             # Show help
kilo auth login         # Authenticate
kilo init               # Initialize project
kilo config show        # Show configuration
```

### Code Operations
```bash
kilo generate "prompt"   # Generate code
kilo explain file.js    # Explain code
kilo refactor file.js   # Refactor code
kilo test file.js       # Generate tests
kilo debug file.js      # Debug code
```

### Agent Management
```bash
kilo agent list         # List agents
kilo agent use code     # Switch agent
kilo agent info code    # Agent info
```

### Git Operations
```bash
kilo git status         # Git status
kilo git commit         # Commit changes
kilo git pr create      # Create PR
```

## Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Open panel | Ctrl+Shift+K |
| Command palette | Ctrl+Shift+P |
| Generate code | Ctrl+Alt+G |
| Refactor | Ctrl+Alt+R |
| Debug | Ctrl+Alt+D |
| Explain | Ctrl+Alt+E |
| Test | Ctrl+Alt+T |

## Slash Commands

| Command | Description |
|---------|-------------|
| /generate | Generate code |
| /explain | Explain code |
| /review | Review code |
| /refactor | Refactor code |
| /test | Generate tests |
| /debug | Debug code |
| /docs | Generate documentation |
| /commit | Commit changes |
| /pr | Create pull request |

## Configuration Basics

```json
{
  "aiProvider": "openai",
  "model": "gpt-4",
  "temperature": 0.7,
  "maxTokens": 2000
}
```

## Common Options

```bash
--output, -o     Output format
--file, -f       Output to file
--verbose, -v    Detailed output
--dry-run         Preview only
```

## Agents

- **code** - General code generation
- **review** - Code review
- **test** - Test generation
- **debug** - Debugging
- **docs** - Documentation
- **architect** - System design

## Modes

- **interactive** - Real-time conversation
- **batch** - Process multiple requests
- **autonomous** - Independent operation

## Quick Tips

- Use specific prompts for better results
- Provide context when asking questions
- Use rules to maintain consistency
- Regularly update your configuration
- Use MCP servers for extended capabilities
- Enable audit logging for security
- Use workflows to automate tasks
- Keep context window manageable
