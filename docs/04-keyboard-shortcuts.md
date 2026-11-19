# Keyboard Shortcuts

## Global Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Shift + K` | Open Kilo Code panel |
| `Ctrl + Shift + P` | Open command palette |
| `Ctrl + /` | Quick help |
| `Ctrl + .` | Show suggestions |
| `Esc` | Cancel current operation |

## Editor Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Alt + G` | Generate code |
| `Ctrl + Alt + R` | Refactor selection |
| `Ctrl + Alt + D` | Debug selection |
| `Ctrl + Alt + T` | Generate tests |
| `Ctrl + Alt + E` | Explain code |
| `Ctrl + Alt + F` | Fix issues |

## Navigation Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + P` | Quick file open |
| `Ctrl + G` | Go to line |
| `Ctrl + Shift + F` | Find in files |
| `Ctrl + Shift + R` | Go to symbol |

## Agent Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Alt + 1` | Switch to Code agent |
| `Ctrl + Alt + 2` | Switch to Review agent |
| `Ctrl + Alt + 3` | Switch to Test agent |
| `Ctrl + Alt + 4` | Switch to Debug agent |
| `Ctrl + Alt + 5` | Switch to Docs agent |

## Mode Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Alt + I` | Toggle Interactive mode |
| `Ctrl + Alt + B` | Toggle Batch mode |
| `Ctrl + Alt + A` | Toggle Autonomous mode |

## Custom Shortcuts

You can customize shortcuts in your editor settings:

```json
{
  "keybindings": [
    {
      "command": "kilo.generate",
      "key": "ctrl+alt+g",
      "mac": "cmd+alt+g"
    }
  ]
}
```

## Terminal Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + C` | Cancel operation |
| `Ctrl + D` | Exit CLI |
| `Tab` | Autocomplete |
| `↑ / ↓` | Command history |
