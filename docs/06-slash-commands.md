# Slash Commands

Slash commands are special commands you can use in the chat interface to perform actions quickly.

## Code Generation Commands

### `/generate`
Generate code from a description.

```text
/generate Create a React component for a user profile card
```

### `/implement`
Implement a feature based on requirements.

```text
/implement User authentication with JWT tokens
```

### `/complete`
Complete the current code.

```text
/complete
```

## Code Analysis Commands

### `/explain`
Explain how code works.

```text
/explain src/auth.js
```

### `/review`
Review code for quality and issues.

```text
/review src/api.js
```

### `/analyze`
Analyze code complexity and metrics.

```text
/analyze src/complex.js
```

## Code Transformation Commands

### `/refactor`
Refactor code to improve structure.

```text
/refactor src/old-code.js --target=modern
```

### `/convert`
Convert code between languages or frameworks.

```text
/convert src/app.js --from=js --to=ts
```

### `/optimize`
Optimize code for performance.

```text
/optimize src/query.js
```

## Testing Commands

### `/test`
Generate tests for code.

```text
/test src/utils.js
```

### `/coverage`
Check test coverage.

```text
/coverage
```

### `/debug`
Debug and fix issues.

```text
/debug src/app.js
```

## Documentation Commands

### `/docs`
Generate documentation.

```text
/docs src/api.js
```

### `/readme`
Generate README for project.

```text
/readme
```

### `/comment`
Add comments to code.

```text
/comment src/functions.js
```

## Git Commands

### `/commit`
Generate commit message.

```text
/commit
```

### `/pr`
Create pull request description.

```text
/pr
```

### `/changelog`
Update changelog.

```text
/changelog
```

## Configuration Commands

### `/config`
Show or update configuration.

```text
/config show
/config set model gpt-4
```

### `/agent`
Switch agents.

```text
/agent use review
/agent list
```

### `/mode`
Switch modes.

```text
/mode interactive
/mode batch
```

## Workflow Commands

### `/workflow`
Manage workflows.

```text
/workflow list
/workflow run deploy
```

### `/schedule`
Schedule tasks.

```text
/schedule test --cron="0 0 * * *"
```

## Utility Commands

### `/help`
Show help for commands.

```text
/help generate
```

### `/history`
Show command history.

```text
/history
```

### `/clear`
Clear the chat.

```text
/clear
```

### `/save`
Save the current session.

```text
/save my-session
```

## Command Options

Most slash commands support these options:

- `--file <path>` - Specify output file
- `--output <format>` - Output format (json, markdown, etc.)
- `--verbose` - Show detailed output
- `--dry-run` - Preview without executing
